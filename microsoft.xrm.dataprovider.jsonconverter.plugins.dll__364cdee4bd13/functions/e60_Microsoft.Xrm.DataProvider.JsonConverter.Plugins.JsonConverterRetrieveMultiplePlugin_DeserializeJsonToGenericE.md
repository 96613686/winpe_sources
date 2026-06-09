# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::DeserializeJsonToGenericEntity

- ea: `0xe60`
- end: `0xeb0`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::DeserializeJsonToGenericEntity`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xe60`
- `0x1540`
- `0x1560`
- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0xe60  nop
0xe61  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::.ctor()
0xe66  stloc.0
0xe67  ldloc.0
0xe68  ldarg.1
0xe69  ldstr    aConnectiondefi// "connectiondefinition"
0xe6e  callvirt T0x2B000013
0xe73  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinition(string value)
0xe78  nop
0xe79  ldarg.2
0xe7a  ldc.i4.0
0xe7b  ceq
0xe7d  stloc.1
0xe7e  ldloc.1
0xe7f  brfalse.s loc_E97
0xe81  nop
0xe82  ldloc.0
0xe83  ldarg.1
0xe84  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0xe89  callvirt T0x2B000013
0xe8e  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0xe93  nop
0xe94  nop
0xe95  br.s     loc_EA5
0xe97  nop
0xe98  ldloc.0
0xe99  ldsfld   string [mscorlib]System.String::Empty
0xe9e  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0xea3  nop
0xea4  nop
0xea5  ldloc.0
0xea6  call     T0x2B000014
0xeab  stloc.2
0xeac  br.s     loc_EAE
0xeae  ldloc.2
0xeaf  ret
```
