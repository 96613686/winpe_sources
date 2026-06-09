# Microsoft.Crm.Application.Platform.EntityProxy::InitializeForCreate

- ea: `0x5d120`
- end: `0x5d1b6`
- name: `Microsoft.Crm.Application.Platform.EntityProxy::InitializeForCreate`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xe8d0`
- `0x5bae0`
- `0x5bf80`
- `0x5d120`
- `0x5d5e0`
- `0x5ea60`

## string_xrefs

- `0x5d174`: `service`
- `0x5d1a5`: `istemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5d120  ldarg.0
0x5d121  call     instance void Microsoft.Crm.Application.Platform.EntityBase::InitializeForCreate()
0x5d126  ldarg.0
0x5d127  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5d12c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x5d131  brfalse.s loc_5D16C
0x5d133  ldarg.0
0x5d134  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5d139  ldstr    aCampaignactivi_5// "campaignactivity"
0x5d13e  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5d143  brfalse.s loc_5D16C
0x5d145  ldarg.0
0x5d146  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5d14b  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x5d150  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5d155  brfalse.s loc_5D16C
0x5d157  ldarg.0
0x5d158  ldstr    aActualstart// "actualstart"
0x5d15d  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Security.User::get_LocalDateTime()
0x5d162  box      [mscorlib]System.DateTime
0x5d167  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d16c  ldarg.0
0x5d16d  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5d172  stloc.0
0x5d173  ldloc.0
0x5d174  ldstr    aService// "service"
0x5d179  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d17e  brtrue.s loc_5D18E
0x5d180  ldloc.0
0x5d181  ldstr    aCampaign// "campaign"
0x5d186  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d18b  brtrue.s loc_5D1A4
0x5d18d  ret
0x5d18e  ldarg.0
0x5d18f  ldstr    aStrategyid// "strategyid"
0x5d194  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::DefaultSchedulingStrategyId
0x5d199  box      [mscorlib]System.Guid
0x5d19e  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d1a3  ret
0x5d1a4  ldarg.0
0x5d1a5  ldstr    aIstemplate// "istemplate"
0x5d1aa  ldc.i4.0
0x5d1ab  box      [mscorlib]System.Boolean
0x5d1b0  call     instance void Microsoft.Crm.Application.Platform.EntityProxy::SetPropertyIfNull(string propertyName, object propertyValue)
0x5d1b5  ret
```
