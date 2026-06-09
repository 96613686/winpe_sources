# Microsoft.Crm.Dependency.ComponentCollector::RetrieveAllOldInvalidDependencies

- ea: `0x62f0`
- end: `0x63bc`
- name: `Microsoft.Crm.Dependency.ComponentCollector::RetrieveAllOldInvalidDependencies`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x5970`

## callees

- `0x62f0`
- `0x13ee0`
- `0x184b0`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1af00`
- `0x58f50`
- `0x78470`

## string_xrefs

- `0x631a`: `existingcomponentid`
- `0x635a`: `existingcomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x62f0  ldarg.1
0x62f1  brfalse.s loc_62FB
0x62f3  ldarg.1
0x62f4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x62f9  brtrue.s loc_62FD
0x62fb  ldnull
0x62fc  ret
0x62fd  ldstr    aInvaliddepende// "InvalidDependency"
0x6302  ldarg.2
0x6303  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x6308  stloc.0
0x6309  ldloc.0
0x630a  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x630f  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x6314  ldloc.0
0x6315  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x631a  ldstr    aExistingcompon// "existingcomponentid"
0x631f  ldc.i4.8
0x6320  ldarg.1
0x6321  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x6326  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, class [mscorlib]System.Array values)
0x632b  pop
0x632c  ldloc.0
0x632d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x6332  ldc.i4.1
0x6333  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, bool returnBaseServiceIfNoServiceFound)
0x6338  ldloc.0
0x6339  ldarg.2
0x633a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x633f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::.ctor()
0x6344  stloc.1
0x6345  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x634a  stloc.2
0x634b  br.s     loc_639C
0x634d  ldloc.2
0x634e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6353  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6358  stloc.3
0x6359  ldloc.3
0x635a  ldstr    aExistingcompon// "existingcomponentid"
0x635f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6364  unbox.any [mscorlib]System.Guid
0x6369  stloc.s  4
0x636b  ldloc.1
0x636c  ldloc.s  4
0x636e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::ContainsKey(var<u1>)
0x6373  brtrue.s loc_638D
0x6375  ldloc.1
0x6376  ldloc.s  4
0x6378  ldstr    aInvaliddepende// "InvalidDependency"
0x637d  ldarg.2
0x637e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6383  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x6388  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::Add(var<u1>, !!T0)
0x638d  ldloc.1
0x638e  ldloc.s  4
0x6390  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::get_Item(void)
0x6395  ldloc.3
0x6396  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x639b  pop
0x639c  ldloc.2
0x639d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x63a2  brtrue.s loc_634D
0x63a4  leave.s  loc_63BA
0x63a6  ldloc.2
0x63a7  isinst   [mscorlib]System.IDisposable
0x63ac  stloc.s  5
0x63ae  ldloc.s  5
0x63b0  brfalse.s loc_63B9
0x63b2  ldloc.s  5
0x63b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63b9  endfinally
0x63ba  ldloc.1
0x63bb  ret
```
