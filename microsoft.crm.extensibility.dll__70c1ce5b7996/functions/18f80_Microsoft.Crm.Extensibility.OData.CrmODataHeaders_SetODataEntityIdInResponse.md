# Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse

- ea: `0x18f80`
- end: `0x18fa2`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10ae0`
- `0x1e3b0`
- `0x1e480`
- `0x21a70`
- `0x21ad0`
- `0x21f90`
- `0x22480`

## callees

- `0x19160`
- `0x191e0`
- `0x191f0`

## string_xrefs

- `0x18f89`: `Only 1 entity can be created per request`

## pseudocode

```c

```

## disassembly

```asm
0x18f80  ldarg.0
0x18f81  call     instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataCreateResponseHeadersSet()
0x18f86  ldc.i4.0
0x18f87  ceq
0x18f89  ldstr    aOnly1EntityCan// "Only 1 entity can be created per reques"...
0x18f8e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18f93  ldarg.0
0x18f94  ldc.i4.1
0x18f95  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::set_ODataCreateResponseHeadersSet(bool value)
0x18f9a  ldarg.0
0x18f9b  ldarg.1
0x18f9c  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::set_ODataEntityId(class [System]System.Uri value)
0x18fa1  ret
```
