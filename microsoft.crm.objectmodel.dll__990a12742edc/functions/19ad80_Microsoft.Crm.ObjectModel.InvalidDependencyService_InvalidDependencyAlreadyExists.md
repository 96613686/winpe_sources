# Microsoft.Crm.ObjectModel.InvalidDependencyService::InvalidDependencyAlreadyExists

- ea: `0x19ad80`
- end: `0x19ae61`
- name: `Microsoft.Crm.ObjectModel.InvalidDependencyService::InvalidDependencyAlreadyExists`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19aaf0`

## callees

- `0x19aaa0`

## string_xrefs

- `0x19ada4`: `existingcomponentid`
- `0x19adab`: `existingcomponentid`
- `0x19adc1`: `existingcomponenttype`
- `0x19adc8`: `existingcomponenttype`
- `0x19adfb`: `isexistingnoderequiredcomponent`
- `0x19ae02`: `isexistingnoderequiredcomponent`
- `0x19ae18`: `missingcomponenttype`
- `0x19ae1f`: `missingcomponenttype`
- `0x19ae35`: `missingcomponentlookuptype`
- `0x19ae3c`: `missingcomponentlookuptype`

## pseudocode

```c

```

## disassembly

```asm
0x19ad80  ldarg.0
0x19ad81  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x19ad86  ldarg.1
0x19ad87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x19ad8c  ldarg.1
0x19ad8d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x19ad92  stloc.0
0x19ad93  ldloc.0
0x19ad94  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x19ad99  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x19ad9e  ldloc.0
0x19ad9f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19ada4  ldstr    aExistingcompon// "existingcomponentid"
0x19ada9  ldc.i4.0
0x19adaa  ldarg.0
0x19adab  ldstr    aExistingcompon// "existingcomponentid"
0x19adb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19adb5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19adba  pop
0x19adbb  ldloc.0
0x19adbc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19adc1  ldstr    aExistingcompon_0// "existingcomponenttype"
0x19adc6  ldc.i4.0
0x19adc7  ldarg.0
0x19adc8  ldstr    aExistingcompon_0// "existingcomponenttype"
0x19adcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19add2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19add7  pop
0x19add8  ldloc.0
0x19add9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19adde  ldstr    aExistingdepend// "existingdependencytype"
0x19ade3  ldc.i4.0
0x19ade4  ldarg.0
0x19ade5  ldstr    aExistingdepend// "existingdependencytype"
0x19adea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19adef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19adf4  pop
0x19adf5  ldloc.0
0x19adf6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19adfb  ldstr    aIsexistingnode// "isexistingnoderequiredcomponent"
0x19ae00  ldc.i4.0
0x19ae01  ldarg.0
0x19ae02  ldstr    aIsexistingnode// "isexistingnoderequiredcomponent"
0x19ae07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19ae0c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19ae11  pop
0x19ae12  ldloc.0
0x19ae13  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19ae18  ldstr    aMissingcompone// "missingcomponenttype"
0x19ae1d  ldc.i4.0
0x19ae1e  ldarg.0
0x19ae1f  ldstr    aMissingcompone// "missingcomponenttype"
0x19ae24  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19ae29  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19ae2e  pop
0x19ae2f  ldloc.0
0x19ae30  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19ae35  ldstr    aMissingcompone_0// "missingcomponentlookuptype"
0x19ae3a  ldc.i4.0
0x19ae3b  ldarg.0
0x19ae3c  ldstr    aMissingcompone_0// "missingcomponentlookuptype"
0x19ae41  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19ae46  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19ae4b  pop
0x19ae4c  newobj   instance void Microsoft.Crm.ObjectModel.InvalidDependencyService::.ctor()
0x19ae51  ldloc.0
0x19ae52  ldarg.1
0x19ae53  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19ae58  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x19ae5d  ldc.i4.0
0x19ae5e  cgt
0x19ae60  ret
```
