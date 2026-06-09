# Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry

- ea: `0x134d0`
- end: `0x134f3`
- name: `Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x13540`
- `0x13bb0`

## string_xrefs

- `0x134e8`: `TOKEN_EXPIRY`

## pseudocode

```c

```

## disassembly

```asm
0x134d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x134d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x134da  stloc.0
0x134db  ldloca.s 0
0x134dd  constrained. [mscorlib]System.Guid
0x134e3  callvirt instance string [mscorlib]System.Object::ToString()
0x134e8  ldstr    aTokenExpiry// "TOKEN_EXPIRY"
0x134ed  call     string [mscorlib]System.String::Concat(string, string)
0x134f2  ret
```
