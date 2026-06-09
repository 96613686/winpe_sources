# Microsoft.Crm.Application.Platform.DataSource::RetrieveUserSharedAttributePermissions

- ea: `0x5a480`
- end: `0x5a659`
- name: `Microsoft.Crm.Application.Platform.DataSource::RetrieveUserSharedAttributePermissions`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5b830`

## callees

- `0xfd20`
- `0x59800`
- `0x5a480`
- `0x5bae0`
- `0x5bb40`
- `0x5be20`

## string_xrefs

- `0x5a48b`: `principalobjectattributeaccess`
- `0x5a4a7`: `readaccess`
- `0x5a5d6`: `readaccess`
- `0x5a4af`: `updateaccess`
- `0x5a5ec`: `updateaccess`

## pseudocode

```c

```

## disassembly

```asm
0x5a480  ldarg.0
0x5a481  ldstr    aEntity// "entity"
0x5a486  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5a48b  ldstr    aPrincipalobjec// "principalobjectattributeaccess"
0x5a490  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x5a495  stloc.0
0x5a496  ldloc.0
0x5a497  ldc.i4.3
0x5a498  newarr   [mscorlib]System.String
0x5a49d  dup
0x5a49e  ldc.i4.0
0x5a49f  ldstr    aAttributeid// "attributeid"
0x5a4a4  stelem.ref
0x5a4a5  dup
0x5a4a6  ldc.i4.1
0x5a4a7  ldstr    aReadaccess// "readaccess"
0x5a4ac  stelem.ref
0x5a4ad  dup
0x5a4ae  ldc.i4.2
0x5a4af  ldstr    aUpdateaccess// "updateaccess"
0x5a4b4  stelem.ref
0x5a4b5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x5a4ba  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x5a4bf  ldloc.0
0x5a4c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5a4c5  ldc.i4.0
0x5a4c6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x5a4cb  ldloc.0
0x5a4cc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5a4d1  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5a4d6  ldstr    aObjecttypecode// "objecttypecode"
0x5a4db  ldc.i4.0
0x5a4dc  ldarg.0
0x5a4dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5a4e2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5a4e7  box      [mscorlib]System.Int32
0x5a4ec  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x5a4f1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5a4f6  pop
0x5a4f7  ldloc.0
0x5a4f8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5a4fd  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5a502  ldstr    aObjectid_0// "objectid"
0x5a507  ldc.i4.0
0x5a508  ldarg.0
0x5a509  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x5a50e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x5a513  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5a518  pop
0x5a519  ldloc.0
0x5a51a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5a51f  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5a524  ldstr    aPrincipalid// "principalid"
0x5a529  ldc.i4.s 0x4A
0x5a52b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x5a530  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5a535  pop
0x5a536  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x5a53b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x5a540  ldc.i4.0
0x5a541  ldc.i4.0
0x5a542  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x5a547  stloc.3
0x5a548  ldloc.3
0x5a549  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x5a54e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x5a553  ldc.i4.0
0x5a554  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x5a559  ldloc.0
0x5a55a  ldloc.3
0x5a55b  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5a560  stloc.1
0x5a561  ldloc.3
0x5a562  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x5a567  leave.s  loc_5A573
0x5a569  ldloc.3
0x5a56a  brfalse.s loc_5A572
0x5a56c  ldloc.3
0x5a56d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a572  endfinally
0x5a573  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AttributePermissions>::.ctor()
0x5a578  stloc.2
0x5a579  ldloc.1
0x5a57a  call     T0x2B000094
0x5a57f  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Platform.Entity, object> <>c::<>9__168_0
0x5a584  dup
0x5a585  brtrue.s loc_5A59E
0x5a587  pop
0x5a588  ldsfld   class <>c <>c::<>9
0x5a58d  ldftn    instance object <>c::<RetrieveUserSharedAttributePermissions>b__168_0(class Microsoft.Crm.Application.Platform.Entity be)
0x5a593  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Platform.Entity, object>::.ctor(object, native int)
0x5a598  dup
0x5a599  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Platform.Entity, object> <>c::<>9__168_0
0x5a59e  call     T0x2B000095
0x5a5a3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.IGrouping`2<object, class Microsoft.Crm.Application.Platform.Entity>>::GetEnumerator()
0x5a5a8  stloc.s  4
0x5a5aa  br       loc_5A63D
0x5a5af  ldloc.s  4
0x5a5b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<object, class Microsoft.Crm.Application.Platform.Entity>>::get_Current()
0x5a5b6  stloc.s  5
0x5a5b8  ldc.i4.0
0x5a5b9  stloc.s  6
0x5a5bb  ldc.i4.0
0x5a5bc  stloc.s  7
0x5a5be  ldloc.s  5
0x5a5c0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x5a5c5  stloc.s  8
0x5a5c7  br.s     loc_5A5FE
0x5a5c9  ldloc.s  8
0x5a5cb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x5a5d0  stloc.s  9
0x5a5d2  ldloc.s  6
0x5a5d4  ldloc.s  9
0x5a5d6  ldstr    aReadaccess// "readaccess"
0x5a5db  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5a5e0  unbox.any [mscorlib]System.Boolean
0x5a5e5  or
0x5a5e6  stloc.s  6
0x5a5e8  ldloc.s  7
0x5a5ea  ldloc.s  9
0x5a5ec  ldstr    aUpdateaccess// "updateaccess"
0x5a5f1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5a5f6  unbox.any [mscorlib]System.Boolean
0x5a5fb  or
0x5a5fc  stloc.s  7
0x5a5fe  ldloc.s  8
0x5a600  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a605  brtrue.s loc_5A5C9
0x5a607  leave.s  loc_5A615
0x5a609  ldloc.s  8
0x5a60b  brfalse.s loc_5A614
0x5a60d  ldloc.s  8
0x5a60f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a614  endfinally
0x5a615  ldloc.2
0x5a616  ldloc.s  5
0x5a618  callvirt instance var<u1> class [System.Core]System.Linq.IGrouping`2<object, class Microsoft.Crm.Application.Platform.Entity>::get_Key()
0x5a61d  unbox.any [mscorlib]System.Guid
0x5a622  ldc.i4.0
0x5a623  ldloc.s  6
0x5a625  brtrue.s loc_5A62A
0x5a627  ldc.i4.0
0x5a628  br.s     loc_5A62B
0x5a62a  ldc.i4.4
0x5a62b  ldloc.s  7
0x5a62d  brtrue.s loc_5A632
0x5a62f  ldc.i4.0
0x5a630  br.s     loc_5A633
0x5a632  ldc.i4.4
0x5a633  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AttributePermissions::.ctor(int32, int32, int32)
0x5a638  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AttributePermissions>::set_Item(var<u1>, !!T0)
0x5a63d  ldloc.s  4
0x5a63f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a644  brtrue   loc_5A5AF
0x5a649  leave.s  loc_5A657
0x5a64b  ldloc.s  4
0x5a64d  brfalse.s loc_5A656
0x5a64f  ldloc.s  4
0x5a651  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a656  endfinally
0x5a657  ldloc.2
0x5a658  ret
```
