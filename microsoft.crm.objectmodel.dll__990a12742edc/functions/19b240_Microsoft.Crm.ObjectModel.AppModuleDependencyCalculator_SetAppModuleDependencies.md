# Microsoft.Crm.ObjectModel.AppModuleDependencyCalculator::SetAppModuleDependencies

- ea: `0x19b240`
- end: `0x19b3d8`
- name: `Microsoft.Crm.ObjectModel.AppModuleDependencyCalculator::SetAppModuleDependencies`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x19b120`
- `0x19b180`

## callees

- `0x8f9b0`
- `0x11f9d0`
- `0x19b240`
- `0x19b3e0`

## string_xrefs

- `0x19b389`: `welcomepageid`
- `0x19b39b`: `welcomepageid`
- `0x19b3b3`: `welcomepageid`
- `0x19b2ba`: `componenttype`
- `0x19b309`: `componenttype`
- `0x19b25c`: `AppModuleComponent`
- `0x19b268`: `AppModuleComponent`
- `0x19b29d`: `AppModuleComponent`

## pseudocode

```c

```

## disassembly

```asm
0x19b240  ldarg.1
0x19b241  brtrue.s loc_19B25C
0x19b243  ldarg.3
0x19b244  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x19b249  ldc.i4.s 0x14
0x19b24b  ldstr    aEmptyEntityPas// "Empty Entity passed"
0x19b250  ldc.i4.0
0x19b251  newarr   [mscorlib]System.Object
0x19b256  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19b25b  ret
0x19b25c  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x19b261  ldarg.3
0x19b262  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x19b267  stloc.0
0x19b268  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x19b26d  ldarg.3
0x19b26e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19b273  stloc.1
0x19b274  ldloc.1
0x19b275  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x19b27a  ldc.i4.0
0x19b27b  ldarg.1
0x19b27c  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x19b281  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b286  unbox.any [mscorlib]System.Guid
0x19b28b  box      [mscorlib]System.Guid
0x19b290  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19b295  pop
0x19b296  ldloc.0
0x19b297  ldloc.1
0x19b298  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x19b29d  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x19b2a2  ldarg.3
0x19b2a3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19b2a8  stloc.2
0x19b2a9  ldloc.2
0x19b2aa  ldc.i4.2
0x19b2ab  newarr   [mscorlib]System.String
0x19b2b0  dup
0x19b2b1  ldc.i4.0
0x19b2b2  ldstr    aObjectid// "objectid"
0x19b2b7  stelem.ref
0x19b2b8  dup
0x19b2b9  ldc.i4.1
0x19b2ba  ldstr    aComponenttype// "componenttype"
0x19b2bf  stelem.ref
0x19b2c0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x19b2c5  ldloc.0
0x19b2c6  ldloc.2
0x19b2c7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x19b2cc  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x19b2d1  ldloc.0
0x19b2d2  ldarg.3
0x19b2d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19b2d8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.ComponentInfo>::.ctor()
0x19b2dd  stloc.3
0x19b2de  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x19b2e3  stloc.s  4
0x19b2e5  br.s     loc_19B322
0x19b2e7  ldloc.s  4
0x19b2e9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19b2ee  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x19b2f3  stloc.s  5
0x19b2f5  ldloc.3
0x19b2f6  ldloc.s  5
0x19b2f8  ldstr    aObjectid// "objectid"
0x19b2fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b302  unbox.any [mscorlib]System.Guid
0x19b307  ldloc.s  5
0x19b309  ldstr    aComponenttype// "componenttype"
0x19b30e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b313  unbox.any [mscorlib]System.Int32
0x19b318  newobj   instance void Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(valuetype [mscorlib]System.Guid objectId, int32 type)
0x19b31d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>)
0x19b322  ldloc.s  4
0x19b324  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19b329  brtrue.s loc_19B2E7
0x19b32b  leave.s  loc_19B342
0x19b32d  ldloc.s  4
0x19b32f  isinst   [mscorlib]System.IDisposable
0x19b334  stloc.s  6
0x19b336  ldloc.s  6
0x19b338  brfalse.s loc_19B341
0x19b33a  ldloc.s  6
0x19b33c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19b341  endfinally
0x19b342  ldarg.1
0x19b343  ldstr    aWebresourceid// "webresourceid"
0x19b348  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b34d  brfalse.s loc_19B388
0x19b34f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19b354  ldarg.1
0x19b355  ldstr    aWebresourceid// "webresourceid"
0x19b35a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b35f  unbox.any [mscorlib]System.Guid
0x19b364  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19b369  brfalse.s loc_19B388
0x19b36b  ldloc.3
0x19b36c  ldarg.1
0x19b36d  ldstr    aWebresourceid// "webresourceid"
0x19b372  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b377  unbox.any [mscorlib]System.Guid
0x19b37c  ldc.i4.s 0x3D
0x19b37e  newobj   instance void Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(valuetype [mscorlib]System.Guid objectId, int32 type)
0x19b383  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>)
0x19b388  ldarg.1
0x19b389  ldstr    aWelcomepageid// "welcomepageid"
0x19b38e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b393  brfalse.s loc_19B3CE
0x19b395  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19b39a  ldarg.1
0x19b39b  ldstr    aWelcomepageid// "welcomepageid"
0x19b3a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b3a5  unbox.any [mscorlib]System.Guid
0x19b3aa  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19b3af  brfalse.s loc_19B3CE
0x19b3b1  ldloc.3
0x19b3b2  ldarg.1
0x19b3b3  ldstr    aWelcomepageid// "welcomepageid"
0x19b3b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19b3bd  unbox.any [mscorlib]System.Guid
0x19b3c2  ldc.i4.s 0x3D
0x19b3c4  newobj   instance void Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(valuetype [mscorlib]System.Guid objectId, int32 type)
0x19b3c9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>)
0x19b3ce  ldarg.0
0x19b3cf  ldloc.3
0x19b3d0  ldarg.2
0x19b3d1  ldarg.3
0x19b3d2  call     instance void Microsoft.Crm.ObjectModel.AppModuleDependencyCalculator::SetAncestorsFromList(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.ComponentInfo> components, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes type, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19b3d7  ret
```
