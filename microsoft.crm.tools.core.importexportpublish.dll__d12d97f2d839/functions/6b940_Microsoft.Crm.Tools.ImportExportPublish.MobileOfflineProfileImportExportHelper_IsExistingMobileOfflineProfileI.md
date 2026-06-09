# Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileImportExportHelper::IsExistingMobileOfflineProfileItemAssociation

- ea: `0x6b940`
- end: `0x6ba30`
- name: `Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileImportExportHelper::IsExistingMobileOfflineProfileItemAssociation`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6c560`

## callees

- `0x6b940`

## string_xrefs

- `0x6b948`: `componentstate`
- `0x6b958`: `componentstate`
- `0x6b96b`: `componentstate`
- `0x6b9e9`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x6b940  ldc.i4.0
0x6b941  stloc.0
0x6b942  ldarg.0
0x6b943  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x6b948  ldstr    aComponentstate_0// "componentstate"
0x6b94d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x6b952  brfalse  loc_6BA2E
0x6b957  ldarg.0
0x6b958  ldstr    aComponentstate_0// "componentstate"
0x6b95d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b962  unbox.any [mscorlib]System.Int32
0x6b967  ldc.i4.3
0x6b968  beq.s    loc_6B980
0x6b96a  ldarg.0
0x6b96b  ldstr    aComponentstate_0// "componentstate"
0x6b970  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b975  unbox.any [mscorlib]System.Int32
0x6b97a  ldc.i4.2
0x6b97b  bne.un   loc_6BA2E
0x6b980  ldstr    aMobileofflinep_13// "MobileOfflineProfileItemAssociation"
0x6b985  ldarg.1
0x6b986  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b98b  stloc.1
0x6b98c  ldstr    aMobileofflinep_13// "MobileOfflineProfileItemAssociation"
0x6b991  ldarg.1
0x6b992  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6b997  stloc.2
0x6b998  ldstr    aMobileofflinep_13// "MobileOfflineProfileItemAssociation"
0x6b99d  ldarg.1
0x6b99e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6b9a3  stloc.3
0x6b9a4  ldloc.3
0x6b9a5  ldstr    aMobileofflinep_5// "mobileofflineprofileitemid"
0x6b9aa  ldc.i4.0
0x6b9ab  ldarg.0
0x6b9ac  ldstr    aMobileofflinep_5// "mobileofflineprofileitemid"
0x6b9b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b9b6  unbox.any [mscorlib]System.Guid
0x6b9bb  box      [mscorlib]System.Guid
0x6b9c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6b9c5  pop
0x6b9c6  ldloc.3
0x6b9c7  ldstr    aRelationshipid// "relationshipid"
0x6b9cc  ldc.i4.0
0x6b9cd  ldarg.0
0x6b9ce  ldstr    aRelationshipid// "relationshipid"
0x6b9d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b9d8  unbox.any [mscorlib]System.Guid
0x6b9dd  box      [mscorlib]System.Guid
0x6b9e2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6b9e7  pop
0x6b9e8  ldloc.3
0x6b9e9  ldstr    aComponentstate_0// "componentstate"
0x6b9ee  ldc.i4.8
0x6b9ef  ldc.i4.2
0x6b9f0  newarr   [mscorlib]System.Int32
0x6b9f5  dup
0x6b9f6  ldc.i4.1
0x6b9f7  ldc.i4.1
0x6b9f8  stelem.i4
0x6b9f9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6b9fe  pop
0x6b9ff  ldloc.2
0x6ba00  ldloc.3
0x6ba01  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x6ba06  ldarg.1
0x6ba07  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ba0c  stloc.s  4
0x6ba0e  ldloc.1
0x6ba0f  ldloc.2
0x6ba10  ldc.i4.1
0x6ba11  ldarg.1
0x6ba12  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6ba17  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6ba1c  ldc.i4.0
0x6ba1d  cgt
0x6ba1f  stloc.0
0x6ba20  leave.s  loc_6BA2E
0x6ba22  ldloc.s  4
0x6ba24  brfalse.s loc_6BA2D
0x6ba26  ldloc.s  4
0x6ba28  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ba2d  endfinally
0x6ba2e  ldloc.0
0x6ba2f  ret
```
