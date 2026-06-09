# Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileImportExportHelper::IsExistingMobileOfflineProfileItem

- ea: `0x6b850`
- end: `0x6b940`
- name: `Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileImportExportHelper::IsExistingMobileOfflineProfileItem`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6c330`

## callees

- `0x6b850`

## string_xrefs

- `0x6b858`: `componentstate`
- `0x6b868`: `componentstate`
- `0x6b87b`: `componentstate`
- `0x6b8f9`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x6b850  ldc.i4.0
0x6b851  stloc.0
0x6b852  ldarg.0
0x6b853  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x6b858  ldstr    aComponentstate_0// "componentstate"
0x6b85d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x6b862  brfalse  loc_6B93E
0x6b867  ldarg.0
0x6b868  ldstr    aComponentstate_0// "componentstate"
0x6b86d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b872  unbox.any [mscorlib]System.Int32
0x6b877  ldc.i4.3
0x6b878  beq.s    loc_6B890
0x6b87a  ldarg.0
0x6b87b  ldstr    aComponentstate_0// "componentstate"
0x6b880  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b885  unbox.any [mscorlib]System.Int32
0x6b88a  ldc.i4.2
0x6b88b  bne.un   loc_6B93E
0x6b890  ldstr    aMobileofflinep_12// "MobileOfflineProfileItem"
0x6b895  ldarg.1
0x6b896  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b89b  stloc.1
0x6b89c  ldstr    aMobileofflinep_12// "MobileOfflineProfileItem"
0x6b8a1  ldarg.1
0x6b8a2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6b8a7  stloc.2
0x6b8a8  ldstr    aMobileofflinep_12// "MobileOfflineProfileItem"
0x6b8ad  ldarg.1
0x6b8ae  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6b8b3  stloc.3
0x6b8b4  ldloc.3
0x6b8b5  ldstr    aRegardingobjec_0// "regardingobjectid"
0x6b8ba  ldc.i4.0
0x6b8bb  ldarg.0
0x6b8bc  ldstr    aRegardingobjec_0// "regardingobjectid"
0x6b8c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b8c6  unbox.any [mscorlib]System.Guid
0x6b8cb  box      [mscorlib]System.Guid
0x6b8d0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6b8d5  pop
0x6b8d6  ldloc.3
0x6b8d7  ldstr    aSelectedentity// "selectedentitytypecode"
0x6b8dc  ldc.i4.0
0x6b8dd  ldarg.0
0x6b8de  ldstr    aSelectedentity// "selectedentitytypecode"
0x6b8e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b8e8  unbox.any [mscorlib]System.Int32
0x6b8ed  box      [mscorlib]System.Int32
0x6b8f2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6b8f7  pop
0x6b8f8  ldloc.3
0x6b8f9  ldstr    aComponentstate_0// "componentstate"
0x6b8fe  ldc.i4.8
0x6b8ff  ldc.i4.2
0x6b900  newarr   [mscorlib]System.Int32
0x6b905  dup
0x6b906  ldc.i4.1
0x6b907  ldc.i4.1
0x6b908  stelem.i4
0x6b909  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6b90e  pop
0x6b90f  ldloc.2
0x6b910  ldloc.3
0x6b911  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x6b916  ldarg.1
0x6b917  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6b91c  stloc.s  4
0x6b91e  ldloc.1
0x6b91f  ldloc.2
0x6b920  ldc.i4.1
0x6b921  ldarg.1
0x6b922  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6b927  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6b92c  ldc.i4.0
0x6b92d  cgt
0x6b92f  stloc.0
0x6b930  leave.s  loc_6B93E
0x6b932  ldloc.s  4
0x6b934  brfalse.s loc_6B93D
0x6b936  ldloc.s  4
0x6b938  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b93d  endfinally
0x6b93e  ldloc.0
0x6b93f  ret
```
