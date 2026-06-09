# Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::Find

- ea: `0xa20`
- end: `0xa45`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::Find`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xa20  ldstr    a012// "{0}{1}{2}"
0xa25  ldarg.1
0xa26  ldarg.0
0xa27  ldfld    char Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::delimiter
0xa2c  box      [mscorlib]System.Char
0xa31  ldarg.2
0xa32  call     string [mscorlib]System.String::Format(string, object, object, object)
0xa37  stloc.0
0xa38  ldarg.0
0xa39  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Xrm.Async.Bridges.FromCommon.AppConfigLookup::appSettings
0xa3e  ldloc.0
0xa3f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa44  ret
```
