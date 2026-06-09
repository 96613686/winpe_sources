# Microsoft.Crm.Service.ObjectModel.SLAService::CheckForOwnerOfSLA

- ea: `0xa340`
- end: `0xa383`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::CheckForOwnerOfSLA`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x9fc0`

## callees

- `0xa340`
- `0xa8e0`

## string_xrefs

- `0xa372`: `This SLA cannot be activated or deactivated by someone who is not its owner or doesn't have impersonate privilege.`

## pseudocode

```c

```

## disassembly

```asm
0xa340  ldarg.0
0xa341  ldarg.1
0xa342  ldarg.2
0xa343  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLARecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa348  ldstr    aOwnerid// "ownerid"
0xa34d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa352  unbox.any [mscorlib]System.Guid
0xa357  ldarg.2
0xa358  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xa35d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa362  brfalse.s loc_A382
0xa364  ldarg.2
0xa365  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xa36a  ldarg.2
0xa36b  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckImpersonatePrivilegeForCaller(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa370  brtrue.s loc_A382
0xa372  ldstr    aThisSlaCannotB// "This SLA cannot be activated or deactiv"...
0xa377  ldc.i4   0x8004F872
0xa37c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa381  throw
0xa382  ret
```
