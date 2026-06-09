# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes

- ea: `0x1f940`
- end: `0x1f953`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes`
- size: `19`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a480`
- `0x1f550`
- `0x1f610`
- `0x1f820`
- `0x1f9a0`
- `0x22c60`
- `0x24700`

## callees

- `0x1f960`

## pseudocode

```c

```

## disassembly

```asm
0x1f940  ldarg.0
0x1f941  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f946  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_crmAttributeId
0x1f94b  ldarg.0
0x1f94c  ldarg.1
0x1f94d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::SetLookupTypes(int32[] typesToSet)
0x1f952  ret
```
