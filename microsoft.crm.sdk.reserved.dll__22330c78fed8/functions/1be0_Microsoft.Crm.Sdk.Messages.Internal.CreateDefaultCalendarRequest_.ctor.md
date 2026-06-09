# Microsoft.Crm.Sdk.Messages.Internal.CreateDefaultCalendarRequest::.ctor

- ea: `0x1be0`
- end: `0x1c17`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateDefaultCalendarRequest::.ctor`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1b00`
- `0x1b60`
- `0x1bc0`

## string_xrefs

- `0x1be7`: `CreateDefaultCalendar`

## pseudocode

```c

```

## disassembly

```asm
0x1be0  ldarg.0
0x1be1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x1be6  ldarg.0
0x1be7  ldstr    aCreatedefaultc// "CreateDefaultCalendar"
0x1bec  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x1bf1  ldarg.0
0x1bf2  ldc.i4.0
0x1bf3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateDefaultCalendarRequest::set_TimeZoneCode(int32 value)
0x1bf8  ldarg.0
0x1bf9  ldloca.s 0
0x1bfb  initobj  [mscorlib]System.Guid
0x1c01  ldloc.0
0x1c02  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateDefaultCalendarRequest::set_BusinessUnitId(valuetype [mscorlib]System.Guid value)
0x1c07  ldarg.0
0x1c08  ldloca.s 0
0x1c0a  initobj  [mscorlib]System.Guid
0x1c10  ldloc.0
0x1c11  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateDefaultCalendarRequest::set_PrimaryUserId(valuetype [mscorlib]System.Guid value)
0x1c16  ret
```
