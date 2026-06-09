# Microsoft.Crm.ObjectModel.DependencyFilter::addAppModuleDependencyForNavSettingDependency

- ea: `0x1aec80`
- end: `0x1aedb6`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::addAppModuleDependencyForNavSettingDependency`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1aeb10`

## callees

- `0x1afdc0`
- `0x1afe60`

## string_xrefs

- `0x1aed13`: `AppConfig`
- `0x1aecd1`: `appconfigid`
- `0x1aed2f`: `appconfigid`
- `0x1aed49`: `appconfigid`
- `0x1aed50`: `appconfigid`
- `0x1aec89`: `requiredcomponentobjectid`
- `0x1aec99`: `requiredcomponenttype`
- `0x1aece9`: `dependentcomponentobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x1aec80  ldarg.2
0x1aec81  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Dependency::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1aec86  stloc.0
0x1aec87  ldarg.0
0x1aec88  ldarg.1
0x1aec89  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1aec8e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aec93  unbox.any [mscorlib]System.Guid
0x1aec98  ldarg.1
0x1aec99  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1aec9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aeca3  unbox.any [mscorlib]System.Int32
0x1aeca8  ldarg.2
0x1aeca9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.DependencyFilter::LoadDependencyNode(valuetype [mscorlib]System.Guid objectId, int32 componentType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1aecae  stloc.1
0x1aecaf  ldstr    aNavigationsett_0// "NavigationSetting"
0x1aecb4  ldarg.2
0x1aecb5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1aecba  stloc.2
0x1aecbb  ldloc.2
0x1aecbc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1aecc1  ldc.i4.2
0x1aecc2  newarr   [mscorlib]System.String
0x1aecc7  dup
0x1aecc8  ldc.i4.0
0x1aecc9  ldstr    aNavigationsett// "navigationsettingid"
0x1aecce  stelem.ref
0x1aeccf  dup
0x1aecd0  ldc.i4.1
0x1aecd1  ldstr    aAppconfigid// "appconfigid"
0x1aecd6  stelem.ref
0x1aecd7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1aecdc  ldloc.2
0x1aecdd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1aece2  ldstr    aNavigationsett// "navigationsettingid"
0x1aece7  ldc.i4.0
0x1aece8  ldarg.1
0x1aece9  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1aecee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aecf3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1aecf8  pop
0x1aecf9  ldloc.2
0x1aecfa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1aecff  ldc.i4.1
0x1aed00  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, bool)
0x1aed05  ldloc.2
0x1aed06  ldarg.2
0x1aed07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1aed0c  ldc.i4.0
0x1aed0d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1aed12  stloc.3
0x1aed13  ldstr    aAppconfig// "AppConfig"
0x1aed18  ldarg.2
0x1aed19  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1aed1e  stloc.s  4
0x1aed20  ldloc.s  4
0x1aed22  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1aed27  ldc.i4.2
0x1aed28  newarr   [mscorlib]System.String
0x1aed2d  dup
0x1aed2e  ldc.i4.0
0x1aed2f  ldstr    aAppconfigid// "appconfigid"
0x1aed34  stelem.ref
0x1aed35  dup
0x1aed36  ldc.i4.1
0x1aed37  ldstr    aAppmoduleid// "appmoduleid"
0x1aed3c  stelem.ref
0x1aed3d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1aed42  ldloc.s  4
0x1aed44  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1aed49  ldstr    aAppconfigid// "appconfigid"
0x1aed4e  ldc.i4.0
0x1aed4f  ldloc.3
0x1aed50  ldstr    aAppconfigid// "appconfigid"
0x1aed55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aed5a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1aed5f  pop
0x1aed60  ldloc.s  4
0x1aed62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1aed67  ldc.i4.1
0x1aed68  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, bool)
0x1aed6d  ldloc.s  4
0x1aed6f  ldarg.2
0x1aed70  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1aed75  ldc.i4.0
0x1aed76  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1aed7b  stloc.s  5
0x1aed7d  ldarg.0
0x1aed7e  ldloc.s  5
0x1aed80  ldstr    aAppmoduleid// "appmoduleid"
0x1aed85  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aed8a  unbox.any [mscorlib]System.Guid
0x1aed8f  ldc.i4.s 0x50
0x1aed91  ldarg.2
0x1aed92  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.DependencyFilter::LoadDependencyNode(valuetype [mscorlib]System.Guid objectId, int32 componentType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1aed97  stloc.s  6
0x1aed99  ldarg.0
0x1aed9a  ldloc.0
0x1aed9b  ldloc.1
0x1aed9c  ldloc.s  6
0x1aed9e  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::SetDependencyValues(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dependency, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity requiredDependencyNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dependentDependencyNode)
0x1aeda3  ldloc.0
0x1aeda4  ldstr    aDependencytype// "dependencytype"
0x1aeda9  ldc.i4.2
0x1aedaa  box      [mscorlib]System.Int32
0x1aedaf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1aedb4  ldloc.0
0x1aedb5  ret
```
