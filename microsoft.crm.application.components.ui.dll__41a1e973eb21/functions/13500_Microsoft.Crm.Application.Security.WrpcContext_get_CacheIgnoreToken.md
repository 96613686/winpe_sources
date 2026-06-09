# Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken

- ea: `0x13500`
- end: `0x13523`
- name: `Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x13540`
- `0x13bb0`

## string_xrefs

- `0x13518`: `IGNORE_TOKEN`

## pseudocode

```c

```

## disassembly

```asm
0x13500  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13505  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1350a  stloc.0
0x1350b  ldloca.s 0
0x1350d  constrained. [mscorlib]System.Guid
0x13513  callvirt instance string [mscorlib]System.Object::ToString()
0x13518  ldstr    aIgnoreToken// "IGNORE_TOKEN"
0x1351d  call     string [mscorlib]System.String::Concat(string, string)
0x13522  ret
```
