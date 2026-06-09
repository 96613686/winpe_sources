# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::MergeStringToGenericEntity

- ea: `0x13f0`
- end: `0x1455`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::MergeStringToGenericEntity`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x13f0`
- `0x1530`
- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  nop
0x13f1  ldarg.0
0x13f2  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinition()
0x13f7  call     string [System]System.Net.WebUtility::UrlDecode(string)
0x13fc  stloc.0
0x13fd  ldloc.0
0x13fe  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x1403  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x1408  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x140d  stloc.1
0x140e  ldarg.0
0x140f  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinitionSecrets()
0x1414  ldnull
0x1415  cgt.un
0x1417  stloc.3
0x1418  ldloc.3
0x1419  brfalse.s loc_1446
0x141b  nop
0x141c  ldarg.0
0x141d  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinitionSecrets()
0x1422  call     string [System]System.Net.WebUtility::UrlDecode(string)
0x1427  stloc.s  4
0x1429  ldloc.s  4
0x142b  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x1430  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x1435  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x143a  stloc.s  5
0x143c  ldloc.1
0x143d  ldloc.s  5
0x143f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JContainer::Merge(object)
0x1444  nop
0x1445  nop
0x1446  ldloc.1
0x1447  callvirt T0x2B000017
0x144c  stloc.2
0x144d  ldloc.2
0x144e  stloc.s  6
0x1450  br.s     loc_1452
0x1452  ldloc.s  6
0x1454  ret
```
