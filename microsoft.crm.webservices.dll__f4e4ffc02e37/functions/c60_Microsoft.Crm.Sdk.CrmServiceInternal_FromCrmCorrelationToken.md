# Microsoft.Crm.Sdk.CrmServiceInternal::FromCrmCorrelationToken

- ea: `0xc60`
- end: `0xcb2`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::FromCrmCorrelationToken`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x990`
- `0x4650`

## callees

- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.0
0xc61  brtrue.s loc_C65
0xc63  ldnull
0xc64  ret
0xc65  ldarg.0
0xc66  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::FromLegacyToken(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken)
0xc6b  stloc.0
0xc6c  ldarg.0
0xc6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationUpdatedTime()
0xc72  brfalse.s loc_C93
0xc74  ldloc.0
0xc75  ldarg.0
0xc76  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationUpdatedTime()
0xc7b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0xc80  stloc.1
0xc81  ldloca.s 1
0xc83  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xc88  ldc.i4.1
0xc89  newobj   instance void [mscorlib]System.DateTime::.ctor(int64, valuetype [mscorlib]System.DateTimeKind)
0xc8e  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_CorrelationUpdatedTime(valuetype [mscorlib]System.DateTime)
0xc93  ldloc.0
0xc94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_CorrelationId()
0xc99  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc9e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xca3  brfalse.s loc_CB0
0xca5  ldloc.0
0xca6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xcab  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_CorrelationId(valuetype [mscorlib]System.Guid)
0xcb0  ldloc.0
0xcb1  ret
```
