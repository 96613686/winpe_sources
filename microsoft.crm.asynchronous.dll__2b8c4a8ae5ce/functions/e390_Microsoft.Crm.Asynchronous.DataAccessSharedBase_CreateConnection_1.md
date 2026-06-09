# Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection_1

- ea: `0xe390`
- end: `0xe3c5`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection_1`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe360`
- `0xe380`

## callees

- `0xe170`
- `0xe1a0`
- `0xe390`

## string_xrefs

- `0xe3b0`: `Exception while trying to create database connection for organization {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe390  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::Initialize()
0xe395  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::get_QueryDetails()
0xe39a  ldarg.1
0xe39b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xe3a0  ldarg.1
0xe3a1  ldarg.2
0xe3a2  ldc.i4.0
0xe3a3  ldc.i4.0
0xe3a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe3a9  stloc.0
0xe3aa  leave.s  loc_E3C3
0xe3ac  stloc.1
0xe3ad  ldarg.0
0xe3ae  ldloc.1
0xe3af  ldnull
0xe3b0  ldstr    aExceptionWhile_4// "Exception while trying to create databa"...
0xe3b5  ldarg.1
0xe3b6  ldarg.0
0xe3b7  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe3bc  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xe3c1  rethrow
0xe3c3  ldloc.0
0xe3c4  ret
```
