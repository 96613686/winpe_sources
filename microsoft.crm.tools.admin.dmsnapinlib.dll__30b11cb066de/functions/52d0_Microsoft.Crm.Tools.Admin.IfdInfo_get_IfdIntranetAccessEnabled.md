# Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdIntranetAccessEnabled

- ea: `0x52d0`
- end: `0x52e7`
- name: `Microsoft.Crm.Tools.Admin.IfdInfo::get_IfdIntranetAccessEnabled`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4e60`

## string_xrefs

- `0x52d1`: `IfdInfo.IfdIntranetAccessEnabledProperty`

## pseudocode

```c

```

## disassembly

```asm
0x52d0  ldarg.0
0x52d1  ldstr    aIfdinfoIfdintr// "IfdInfo.IfdIntranetAccessEnabledPropert"...
0x52d6  ldc.i4.0
0x52d7  box      [mscorlib]System.Boolean
0x52dc  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x52e1  unbox.any [mscorlib]System.Boolean
0x52e6  ret
```
