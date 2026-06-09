# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::LoadFromFolder

- ea: `0x148e0`
- end: `0x148f2`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::LoadFromFolder`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14830`

## string_xrefs

- `0x148e1`: `OnlinePackageDescriptor.xml`

## pseudocode

```c

```

## disassembly

```asm
0x148e0  ldarg.0
0x148e1  ldstr    aOnlinepackaged// "OnlinePackageDescriptor.xml"
0x148e6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x148eb  ldarg.1
0x148ec  call     class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::LoadFromFile(string filePath, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap tokenMap)
0x148f1  ret
```
