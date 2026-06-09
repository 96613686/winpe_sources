# Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey

- ea: `0x134a0`
- end: `0x134c3`
- name: `Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x13540`
- `0x13bb0`

## string_xrefs

- `0x134b8`: `TOKEN_KEY`

## pseudocode

```c

```

## disassembly

```asm
0x134a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x134a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x134aa  stloc.0
0x134ab  ldloca.s 0
0x134ad  constrained. [mscorlib]System.Guid
0x134b3  callvirt instance string [mscorlib]System.Object::ToString()
0x134b8  ldstr    aTokenKey// "TOKEN_KEY"
0x134bd  call     string [mscorlib]System.String::Concat(string, string)
0x134c2  ret
```
