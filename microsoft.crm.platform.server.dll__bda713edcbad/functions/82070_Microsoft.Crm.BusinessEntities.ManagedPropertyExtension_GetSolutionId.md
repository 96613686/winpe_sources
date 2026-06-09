# Microsoft.Crm.BusinessEntities.ManagedPropertyExtension::GetSolutionId

- ea: `0x82070`
- end: `0x82171`
- name: `Microsoft.Crm.BusinessEntities.ManagedPropertyExtension::GetSolutionId`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x81ff0`

## callees

- `0x30b0`
- `0x3280`
- `0x7690`
- `0x13b10`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x355f0`
- `0x35b80`
- `0x36170`
- `0x36800`
- `0x58f50`
- `0x78330`
- `0x82070`

## string_xrefs

- `0x820e2`: `componenttype`
- `0x8210e`: `There should only ever be 1 dependency node for any given component.  Count: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x82070  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x82075  stloc.0
0x82076  ldarg.0
0x82077  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_PlatformName()
0x8207c  ldarg.0
0x8207d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_IsMetadata()
0x82082  call     int32 Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrieveComponentType(string platformName, bool isMetadata)
0x82087  stloc.1
0x82088  ldloc.1
0x82089  call     class Microsoft.Crm.Dependency.ComponentDefinition Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32 componentType)
0x8208e  callvirt instance bool Microsoft.Crm.Dependency.ComponentDefinition::get_DependencyDisabled()
0x82093  brtrue   loc_82143
0x82098  ldstr    aDependencynode// "DependencyNode"
0x8209d  ldarg.1
0x8209e  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x820a3  ldstr    aDependencynode// "DependencyNode"
0x820a8  ldarg.1
0x820a9  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x820ae  stloc.2
0x820af  ldloc.2
0x820b0  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x820b5  ldstr    aBasesolutionid// "basesolutionid"
0x820ba  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x820bf  ldloc.2
0x820c0  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x820c5  ldstr    aObjectid// "objectid"
0x820ca  ldc.i4.0
0x820cb  ldarg.0
0x820cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Id()
0x820d1  box      [mscorlib]System.Guid
0x820d6  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x820db  pop
0x820dc  ldloc.2
0x820dd  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x820e2  ldstr    aComponenttype// "componenttype"
0x820e7  ldc.i4.0
0x820e8  ldloc.1
0x820e9  box      [mscorlib]System.Int32
0x820ee  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x820f3  pop
0x820f4  ldloc.2
0x820f5  ldarg.1
0x820f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x820fb  stloc.3
0x820fc  ldloc.3
0x820fd  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x82102  ldc.i4.0
0x82103  ble.s    loc_82143
0x82105  ldloc.3
0x82106  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8210b  ldc.i4.1
0x8210c  ceq
0x8210e  ldstr    aThereShouldOnl_0// "There should only ever be 1 dependency "...
0x82113  ldc.i4.1
0x82114  newarr   [mscorlib]System.Object
0x82119  dup
0x8211a  ldc.i4.0
0x8211b  ldloc.3
0x8211c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x82121  box      [mscorlib]System.Int32
0x82126  stelem.ref
0x82127  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x8212c  ldloc.3
0x8212d  ldc.i4.0
0x8212e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x82133  ldstr    aBasesolutionid// "basesolutionid"
0x82138  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8213d  unbox.any [mscorlib]System.Guid
0x82142  stloc.0
0x82143  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x82148  ldloc.0
0x82149  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8214e  brfalse.s loc_8216F
0x82150  ldloc.1
0x82151  call     class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoaderFactory::Create(int32 componentType)
0x82156  ldloc.1
0x82157  ldarg.0
0x82158  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Id()
0x8215d  ldc.i4.0
0x8215e  ldarg.1
0x8215f  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x82164  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x82169  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x8216e  stloc.0
0x8216f  ldloc.0
0x82170  ret
```
