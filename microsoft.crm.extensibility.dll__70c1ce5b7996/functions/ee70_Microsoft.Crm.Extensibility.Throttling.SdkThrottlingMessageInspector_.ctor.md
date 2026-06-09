# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::.ctor

- ea: `0xee70`
- end: `0xeea4`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::.ctor`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xc850`
- `0xee70`
- `0x2af30`

## string_xrefs

- `0xee85`: `configurationFactory`

## pseudocode

```c

```

## disassembly

```asm
0xee70  ldarg.0
0xee71  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine::.ctor()
0xee76  stfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.RequestThrottlingEngine Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::throttlingEngine
0xee7b  ldarg.0
0xee7c  call     instance void [mscorlib]System.Object::.ctor()
0xee81  ldarg.1
0xee82  brtrue.s loc_EE95
0xee84  ldarg.2
0xee85  ldstr    aConfigurationf// "configurationFactory"
0xee8a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xee8f  call     class [mscorlib]System.Exception Microsoft.Crm.Extensibility.OdataTelemetryUtil::EnsureTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger, class [mscorlib]System.Exception exception)
0xee94  throw
0xee95  ldarg.0
0xee96  ldarg.1
0xee97  stfld    class Microsoft.Crm.Extensibility.ODataV4.Throttling.IThrottlingConfigurationFactory Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::configurationFactory
0xee9c  ldarg.0
0xee9d  ldarg.2
0xee9e  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::servicePlatformLogger
0xeea3  ret
```
