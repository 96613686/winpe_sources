# Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::ProcessImpersonatingUser

- ea: `0x5ed50`
- end: `0x5ee61`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::ProcessImpersonatingUser`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5eae0`

## callees

- `0x5ed50`
- `0x5ee70`

## string_xrefs

- `0x5ed51`: `impersonatinguseridname`
- `0x5ed6f`: `impersonatinguseridname`
- `0x5ed5e`: `impersonatinguserid`
- `0x5ee32`: `impersonatinguserid`

## pseudocode

```c

```

## disassembly

```asm
0x5ed50  ldarg.1
0x5ed51  ldstr    aImpersonatingu_0// "impersonatinguseridname"
0x5ed56  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ed5b  brtrue.s loc_5ED6E
0x5ed5d  ldarg.1
0x5ed5e  ldstr    aImpersonatingu_2// "impersonatinguserid"
0x5ed63  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5ed68  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5ed6d  ret
0x5ed6e  ldarg.1
0x5ed6f  ldstr    aImpersonatingu_0// "impersonatinguseridname"
0x5ed74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ed79  castclass [mscorlib]System.String
0x5ed7e  stloc.0
0x5ed7f  ldloc.0
0x5ed80  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5ed85  brfalse.s loc_5ED8F
0x5ed87  ldarg.0
0x5ed88  ldloc.0
0x5ed89  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::WarnImpersonatingUserId(string impersonatingUserIdName)
0x5ed8e  ret
0x5ed8f  ldstr    aSystemuser// "SystemUser"
0x5ed94  ldarg.0
0x5ed95  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5ed9a  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ed9f  ldstr    aSystemuser// "SystemUser"
0x5eda4  ldarg.0
0x5eda5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5edaa  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5edaf  stloc.1
0x5edb0  ldloc.1
0x5edb1  ldstr    aFullname_0// "fullname"
0x5edb6  ldc.i4.0
0x5edb7  ldloc.0
0x5edb8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5edbd  pop
0x5edbe  ldstr    aSystemuser// "SystemUser"
0x5edc3  ldarg.0
0x5edc4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5edc9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5edce  stloc.2
0x5edcf  ldloc.1
0x5edd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x5edd5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5edda  ldarg.0
0x5eddb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5ede0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5ede5  stloc.3
0x5ede6  ldloc.3
0x5ede7  ldloc.1
0x5ede8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x5eded  ldloc.2
0x5edee  ldstr    aSystemuserid// "systemuserid"
0x5edf3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5edf8  ldloc.2
0x5edf9  ldstr    aFullname_0// "fullname"
0x5edfe  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5ee03  ldloc.3
0x5ee04  ldloc.2
0x5ee05  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x5ee0a  dup
0x5ee0b  ldloc.3
0x5ee0c  ldarg.0
0x5ee0d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5ee12  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ee17  stloc.s  4
0x5ee19  ldloc.3
0x5ee1a  ldarg.0
0x5ee1b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::_context
0x5ee20  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ee25  stloc.s  4
0x5ee27  ldc.i4.1
0x5ee28  ldloc.s  4
0x5ee2a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5ee2f  bne.un.s loc_5EE59
0x5ee31  ldarg.1
0x5ee32  ldstr    aImpersonatingu_2// "impersonatinguserid"
0x5ee37  ldloc.s  4
0x5ee39  ldc.i4.0
0x5ee3a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5ee3f  ldstr    aSystemuserid// "systemuserid"
0x5ee44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ee49  unbox.any [mscorlib]System.Guid
0x5ee4e  box      [mscorlib]System.Guid
0x5ee53  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5ee58  ret
0x5ee59  ldarg.0
0x5ee5a  ldloc.0
0x5ee5b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSdkMessageProcessingStepHandler::WarnImpersonatingUserId(string impersonatingUserIdName)
0x5ee60  ret
```
