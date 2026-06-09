# Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::Find

- ea: `0x770`
- end: `0x7bb`
- name: `Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::Find`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x770`

## pseudocode

```c

```

## disassembly

```asm
0x770  ldarg.0
0x771  ldfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.ICrmLocatorService Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::locatorService
0x776  ldarg.0
0x777  ldfld    string Microsoft.Xrm.Async.Bridges.SiteSettingsConfigLookup::settingName
0x77c  callvirt T0x2B00001A
0x781  stloc.0
0x782  ldloc.0
0x783  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x788  brfalse.s loc_790
0x78a  ldsfld   string [mscorlib]System.String::Empty
0x78f  ret
0x790  ldloc.0
0x791  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Parse(string)
0x796  ldstr    a01// "{0}{1}"
0x79b  ldarg.1
0x79c  ldarg.2
0x79d  call     string [mscorlib]System.String::Format(string, object, object)
0x7a2  stloc.1
0x7a3  ldloc.1
0x7a4  ldc.i4.5
0x7a5  ldloca.s 2
0x7a7  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::TryGetValue(string, valuetype [mscorlib]System.StringComparison, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken&)
0x7ac  brtrue.s loc_7B4
0x7ae  ldsfld   string [mscorlib]System.String::Empty
0x7b3  ret
0x7b4  ldloc.2
0x7b5  callvirt instance string [mscorlib]System.Object::ToString()
0x7ba  ret
```
