# MQTTnet.Extensions.IoTHubAuth

Extensions to MQTTnet to connect to IoTHub

## Connect to IoTHub 

To estabish a secure MQTT Connection to  Azure IoT Hub MQTT Broker you need to follow the authentication scheme, associated with the **api version** `2021-06-30-preview`. 

> Note: Tat the time of writing only avaialble as a [private preview](https://github.com/Azure/IoTHubMQTTBrokerPreviewSamples#private-preview-program-information)

This project includes extension methods to the `IMqttClient` interface to connect with SasKeys or X509 certificates, for device and module identities.

## How to use

The code is available as a NuGet source package that will add 2 files to your existing project.

```cs
var client = new MqttFactory().CreateMqttClient();
var conack = await client.ConnectWithSasAsync("<broker-enabled-hub>","<deviceId","<deviceKey");
```

### Tracing

Diagnostics logs can be enabled by creating the client with:

```cs
var client = IMqttClientExtensions.CreateMqttClientWithLogger(Console.Out);
```

### Thanks to

The csproj to produce NuGet source packages from [this gist](https://gist.github.com/attilah/fd3e71f03fd258c496179e0200c57b0b#file-x-y-z-sources-csproj).



