# Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureJsonSerializer

- ea: `0x200`
- end: `0x24f`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureJsonSerializer`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldarg.1
0x201  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Serialization.CamelCasePropertyNamesContractResolver::.ctor()
0x206  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_ContractResolver(class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver)
0x20b  ldarg.1
0x20c  ldc.i4.1
0x20d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_DefaultValueHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.DefaultValueHandling)
0x212  ldarg.1
0x213  ldc.i4.1
0x214  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_NullValueHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.NullValueHandling)
0x219  ldarg.1
0x21a  ldc.i4.0
0x21b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_TypeNameHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.TypeNameHandling)
0x220  ldarg.1
0x221  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter> [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::get_Converters()
0x226  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Converters.StringEnumConverter::.ctor()
0x22b  dup
0x22c  ldc.i4.1
0x22d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Converters.StringEnumConverter::set_CamelCaseText(bool)
0x232  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::Add(var<u1>)
0x237  ldarg.1
0x238  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter> [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::get_Converters()
0x23d  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Converters.IsoDateTimeConverter::.ctor()
0x242  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::Add(var<u1>)
0x247  ldarg.1
0x248  ldc.i4.1
0x249  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_DateTimeZoneHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.DateTimeZoneHandling)
0x24e  ret
```
