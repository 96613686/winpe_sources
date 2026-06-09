# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::RetrieveBeforeUpdate

- ea: `0x8c40`
- end: `0x8c99`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::RetrieveBeforeUpdate`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8a40`

## callees

- `0x89f0`
- `0x8a00`
- `0x8c40`
- `0x8ca0`

## pseudocode

```c

```

## disassembly

```asm
0x8c40  ldarg.1
0x8c41  ldarg.0
0x8c42  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x8c47  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x8c4c  brfalse.s loc_8C97
0x8c4e  ldarg.1
0x8c4f  ldarg.0
0x8c50  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x8c55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x8c5a  unbox.any [mscorlib]System.Guid
0x8c5f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8c64  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8c69  brfalse.s loc_8C97
0x8c6b  ldarg.1
0x8c6c  ldarg.0
0x8c6d  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x8c72  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x8c77  unbox.any [mscorlib]System.Guid
0x8c7c  ldarg.0
0x8c7d  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_EntityName()
0x8c82  ldarg.2
0x8c83  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8c88  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x8c8d  stloc.0
0x8c8e  ldarg.0
0x8c8f  ldloc.0
0x8c90  ldarg.2
0x8c91  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RuleServiceBase::GetBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c96  ret
0x8c97  ldnull
0x8c98  ret
```
