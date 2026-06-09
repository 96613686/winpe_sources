# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::.cctor

- ea: `0x1600`
- end: `0x161d`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::.cctor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1600  newobj   instance void [mscorlib]System.Object::.ctor()
0x1605  stsfld   object Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::Padlock
0x160a  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::.ctor()
0x160f  dup
0x1610  ldc.i4.0
0x1611  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_TypeNameHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.TypeNameHandling)
0x1616  nop
0x1617  stsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x161c  ret
```
