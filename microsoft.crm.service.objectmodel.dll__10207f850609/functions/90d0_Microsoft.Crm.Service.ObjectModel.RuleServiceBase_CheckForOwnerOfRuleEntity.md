# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::CheckForOwnerOfRuleEntity

- ea: `0x90d0`
- end: `0x9170`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::CheckForOwnerOfRuleEntity`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x8bb0`

## callees

- `0x8ca0`
- `0x90d0`

## string_xrefs

- `0x913f`: `This Record Creation and Update Rule cannot be activated or deactivated by someone who is not its owner or doesn't have impersonate privilege.`
- `0x914d`: `This Routing Rule Set cannot be activated or deactivated by someone who is not its owner or doesn't have impersonate privilege.`
- `0x915b`: `This SLA cannot be activated or deactivated by someone who is not its owner or doesn't have impersonate privilege.`

## pseudocode

```c

```

## disassembly

```asm
0x90d0  ldarg.0
0x90d1  ldarg.1
0x90d2  ldarg.2
0x90d3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RuleServiceBase::GetBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x90d8  ldstr    aOwnerid// "ownerid"
0x90dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x90e2  unbox.any [mscorlib]System.Guid
0x90e7  ldarg.2
0x90e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x90ed  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x90f2  brfalse.s loc_916F
0x90f4  ldarg.2
0x90f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x90fa  ldarg.2
0x90fb  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckImpersonatePrivilegeForCaller(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9100  brtrue.s loc_916F
0x9102  ldsfld   string [mscorlib]System.String::Empty
0x9107  stloc.0
0x9108  ldc.i4.0
0x9109  stloc.1
0x910a  ldarg.1
0x910b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x9110  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x9115  stloc.2
0x9116  ldloc.2
0x9117  ldstr    aConvertrule_0// "convertrule"
0x911c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9121  brtrue.s loc_913F
0x9123  ldloc.2
0x9124  ldstr    aRoutingrule_0// "routingrule"
0x9129  call     bool [mscorlib]System.String::op_Equality(string, string)
0x912e  brtrue.s loc_914D
0x9130  ldloc.2
0x9131  ldstr    aSla// "sla"
0x9136  call     bool [mscorlib]System.String::op_Equality(string, string)
0x913b  brtrue.s loc_915B
0x913d  br.s     loc_9167
0x913f  ldstr    aThisRecordCrea// "This Record Creation and Update Rule ca"...
0x9144  stloc.0
0x9145  ldc.i4   0x8004F886
0x914a  stloc.1
0x914b  br.s     loc_9167
0x914d  ldstr    aThisRoutingRul// "This Routing Rule Set cannot be activat"...
0x9152  stloc.0
0x9153  ldc.i4   0x8004F885
0x9158  stloc.1
0x9159  br.s     loc_9167
0x915b  ldstr    aThisSlaCannotB// "This SLA cannot be activated or deactiv"...
0x9160  stloc.0
0x9161  ldc.i4   0x8004F872
0x9166  stloc.1
0x9167  ldloc.0
0x9168  ldloc.1
0x9169  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x916e  throw
0x916f  ret
```
