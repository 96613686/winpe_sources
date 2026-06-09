# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::GetDefinitionString

- ea: `0x1460`
- end: `0x151e`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::GetDefinitionString`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x880`
- `0xf70`

## callees

- `0x1460`
- `0x1540`
- `0x1560`
- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0x1460  nop
0x1461  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::.ctor()
0x1466  stloc.0
0x1467  ldarg.0
0x1468  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x146d  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x1472  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x1477  stloc.1
0x1478  ldarg.0
0x1479  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x147e  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x1483  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x1488  stloc.2
0x1489  nop
0x148a  ldarg.1
0x148b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[] [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_Attributes()
0x1490  stloc.3
0x1491  ldc.i4.0
0x1492  stloc.s  4
0x1494  br.s     loc_14EB
0x1496  ldloc.3
0x1497  ldloc.s  4
0x1499  ldelem.ref
0x149a  stloc.s  5
0x149c  nop
0x149d  ldloc.s  5
0x149f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsDataSourceSecret()
0x14a4  stloc.s  7
0x14a6  ldc.i4.1
0x14a7  stloc.s  8
0x14a9  ldloca.s 7
0x14ab  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x14b0  ldloc.s  8
0x14b2  ceq
0x14b4  ldloca.s 7
0x14b6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x14bb  and
0x14bc  stloc.s  6
0x14be  ldloc.s  6
0x14c0  brfalse.s loc_14D4
0x14c2  nop
0x14c3  ldloc.1
0x14c4  ldloc.s  5
0x14c6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_ExternalName()
0x14cb  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Remove(string)
0x14d0  pop
0x14d1  nop
0x14d2  br.s     loc_14E4
0x14d4  nop
0x14d5  ldloc.2
0x14d6  ldloc.s  5
0x14d8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_ExternalName()
0x14dd  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Remove(string)
0x14e2  pop
0x14e3  nop
0x14e4  nop
0x14e5  ldloc.s  4
0x14e7  ldc.i4.1
0x14e8  add
0x14e9  stloc.s  4
0x14eb  ldloc.s  4
0x14ed  ldloc.3
0x14ee  ldlen
0x14ef  conv.i4
0x14f0  blt.s    loc_1496
0x14f2  ldloc.0
0x14f3  ldloc.1
0x14f4  callvirt instance string [mscorlib]System.Object::ToString()
0x14f9  call     string [System]System.Net.WebUtility::UrlEncode(string)
0x14fe  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinition(string value)
0x1503  nop
0x1504  ldloc.0
0x1505  ldloc.2
0x1506  callvirt instance string [mscorlib]System.Object::ToString()
0x150b  call     string [System]System.Net.WebUtility::UrlEncode(string)
0x1510  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0x1515  nop
0x1516  ldloc.0
0x1517  stloc.s  9
0x1519  br.s     loc_151B
0x151b  ldloc.s  9
0x151d  ret
```
