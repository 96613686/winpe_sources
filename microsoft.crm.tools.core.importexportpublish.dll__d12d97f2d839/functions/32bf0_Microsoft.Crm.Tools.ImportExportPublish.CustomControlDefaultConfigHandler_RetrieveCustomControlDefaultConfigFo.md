# Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::RetrieveCustomControlDefaultConfigForExport

- ea: `0x32bf0`
- end: `0x32d03`
- name: `Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::RetrieveCustomControlDefaultConfigForExport`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x32880`

## callees

- `0x32bf0`
- `0x32d10`
- `0x32d80`

## string_xrefs

- `0x32c32`: `componentstate`
- `0x32c03`: `CustomControlDefaultConfig`
- `0x32c7a`: `customcontroldefaultconfigid`
- `0x32cbe`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x32bf0  ldarg.0
0x32bf1  ldarg.1
0x32bf2  ldarg.0
0x32bf3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32bf8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::RetrieveCustomControlDefaultConfig(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x32bfd  stloc.0
0x32bfe  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::.ctor()
0x32c03  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x32c08  ldarg.0
0x32c09  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32c0e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x32c13  stloc.1
0x32c14  ldloc.1
0x32c15  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x32c1a  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x32c1f  ldc.i4.0
0x32c20  ldarg.1
0x32c21  box      [mscorlib]System.Int32
0x32c26  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x32c2b  pop
0x32c2c  ldloc.1
0x32c2d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x32c32  ldstr    aComponentstate_0// "componentstate"
0x32c37  ldc.i4.0
0x32c38  ldc.i4.3
0x32c39  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x32c3e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x32c43  pop
0x32c44  ldloc.1
0x32c45  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x32c4a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x32c4f  ldloc.1
0x32c50  ldc.i4.4
0x32c51  ldarg.0
0x32c52  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32c57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32c5c  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x32c61  stloc.2
0x32c62  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x32c67  stloc.3
0x32c68  br.s     loc_32C8F
0x32c6a  ldloc.3
0x32c6b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32c70  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x32c75  stloc.s  4
0x32c77  ldloc.2
0x32c78  ldloc.s  4
0x32c7a  ldstr    aCustomcontrold_1// "customcontroldefaultconfigid"
0x32c7f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32c84  unbox.any [mscorlib]System.Guid
0x32c89  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x32c8e  pop
0x32c8f  ldloc.3
0x32c90  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32c95  brtrue.s loc_32C6A
0x32c97  leave.s  loc_32CAD
0x32c99  ldloc.3
0x32c9a  isinst   [mscorlib]System.IDisposable
0x32c9f  stloc.s  5
0x32ca1  ldloc.s  5
0x32ca3  brfalse.s loc_32CAC
0x32ca5  ldloc.s  5
0x32ca7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32cac  endfinally
0x32cad  ldc.i4.0
0x32cae  stloc.s  6
0x32cb0  br.s     loc_32CF7
0x32cb2  ldloc.0
0x32cb3  ldloc.s  6
0x32cb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x32cba  stloc.s  7
0x32cbc  ldloc.s  7
0x32cbe  ldstr    aCustomcontrold_1// "customcontroldefaultconfigid"
0x32cc3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32cc8  unbox.any [mscorlib]System.Guid
0x32ccd  stloc.s  8
0x32ccf  ldloc.2
0x32cd0  ldloc.s  8
0x32cd2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x32cd7  brtrue.s loc_32CE3
0x32cd9  ldarg.0
0x32cda  ldloc.s  7
0x32cdc  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::DoesCustomControlDefaultConfigNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x32ce1  brfalse.s loc_32CF1
0x32ce3  ldloc.0
0x32ce4  ldloc.s  6
0x32ce6  callvirt instance void [mscorlib]System.Collections.CollectionBase::RemoveAt(int32)
0x32ceb  ldloc.s  6
0x32ced  ldc.i4.1
0x32cee  sub
0x32cef  stloc.s  6
0x32cf1  ldloc.s  6
0x32cf3  ldc.i4.1
0x32cf4  add
0x32cf5  stloc.s  6
0x32cf7  ldloc.s  6
0x32cf9  ldloc.0
0x32cfa  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x32cff  blt.s    loc_32CB2
0x32d01  ldloc.0
0x32d02  ret
```
