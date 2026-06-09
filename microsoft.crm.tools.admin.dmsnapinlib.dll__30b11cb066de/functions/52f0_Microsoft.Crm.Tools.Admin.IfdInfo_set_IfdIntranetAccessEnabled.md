# Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdIntranetAccessEnabled

- ea: `0x52f0`
- end: `0x5307`
- name: `Microsoft.Crm.Tools.Admin.IfdInfo::set_IfdIntranetAccessEnabled`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4cf0`

## string_xrefs

- `0x52f6`: `IfdInfo.IfdIntranetAccessEnabledProperty`

## pseudocode

```c

```

## disassembly

```asm
0x52f0  ldarg.0
0x52f1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x52f6  ldstr    aIfdinfoIfdintr// "IfdInfo.IfdIntranetAccessEnabledPropert"...
0x52fb  ldarg.1
0x52fc  box      [mscorlib]System.Boolean
0x5301  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x5306  ret
```
