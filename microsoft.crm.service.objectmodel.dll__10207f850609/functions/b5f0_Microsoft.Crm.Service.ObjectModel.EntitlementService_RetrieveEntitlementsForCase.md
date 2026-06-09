# Microsoft.Crm.Service.ObjectModel.EntitlementService::RetrieveEntitlementsForCase

- ea: `0xb5f0`
- end: `0xb8d5`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::RetrieveEntitlementsForCase`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x11b80`

## callees

- `0xb5f0`
- `0xbb60`

## string_xrefs

- `0xb627`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xb5f0  ldnull
0xb5f1  stloc.0
0xb5f2  ldnull
0xb5f3  stloc.1
0xb5f4  ldnull
0xb5f5  stloc.2
0xb5f6  ldarg.1
0xb5f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb5fc  brtrue   loc_B8D3
0xb601  ldarg.s  4
0xb603  brfalse  loc_B8D3
0xb608  ldarg.s  4
0xb60a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xb60f  ldc.i4.5
0xb610  newarr   [mscorlib]System.String
0xb615  dup
0xb616  ldc.i4.0
0xb617  ldstr    aEntitlementid// "entitlementid"
0xb61c  stelem.ref
0xb61d  dup
0xb61e  ldc.i4.1
0xb61f  ldstr    aName// "name"
0xb624  stelem.ref
0xb625  dup
0xb626  ldc.i4.2
0xb627  ldstr    aCreatedon// "createdon"
0xb62c  stelem.ref
0xb62d  dup
0xb62e  ldc.i4.3
0xb62f  ldstr    aStatecode// "statecode"
0xb634  stelem.ref
0xb635  dup
0xb636  ldc.i4.4
0xb637  ldstr    aIsdefault// "isdefault"
0xb63c  stelem.ref
0xb63d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xb642  ldarg.s  4
0xb644  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb649  ldstr    aCustomerid// "customerid"
0xb64e  ldc.i4.0
0xb64f  ldarg.1
0xb650  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xb655  pop
0xb656  ldarg.s  4
0xb658  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb65d  ldc.i4.0
0xb65e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xb663  ldarg.s  4
0xb665  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb66a  ldstr    aStatecode// "statecode"
0xb66f  ldc.i4.0
0xb670  ldstr    aActive// "Active"
0xb675  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xb67a  pop
0xb67b  ldarg.0
0xb67c  ldarg.s  4
0xb67e  ldarg.s  5
0xb680  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb685  call     T0x2B000001
0xb68a  stloc.0
0xb68b  ldarg.2
0xb68c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb691  brtrue.s loc_B6AA
0xb693  ldarg.0
0xb694  ldloc.0
0xb695  ldstr    aContactid// "contactid"
0xb69a  ldarg.2
0xb69b  ldstr    aEntitlementcon// "EntitlementContacts"
0xb6a0  ldarg.s  4
0xb6a2  ldarg.s  5
0xb6a4  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> Microsoft.Crm.Service.ObjectModel.EntitlementService::GetRelatedEntityEntitlements(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> customerEntitlements, string filterAttributeName, string filterAttributeValue, string intersectionEntityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression query, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb6a9  stloc.2
0xb6aa  ldarg.3
0xb6ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb6b0  brtrue.s loc_B6C9
0xb6b2  ldarg.0
0xb6b3  ldloc.0
0xb6b4  ldstr    aProductid// "productid"
0xb6b9  ldarg.3
0xb6ba  ldstr    aEntitlementpro// "EntitlementProducts"
0xb6bf  ldarg.s  4
0xb6c1  ldarg.s  5
0xb6c3  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> Microsoft.Crm.Service.ObjectModel.EntitlementService::GetRelatedEntityEntitlements(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> customerEntitlements, string filterAttributeName, string filterAttributeValue, string intersectionEntityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression query, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb6c8  stloc.1
0xb6c9  ldnull
0xb6ca  stloc.3
0xb6cb  ldloc.0
0xb6cc  brfalse  loc_B7AA
0xb6d1  ldloc.1
0xb6d2  brfalse  loc_B7AA
0xb6d7  ldloc.2
0xb6d8  brfalse  loc_B7AA
0xb6dd  ldloc.0
0xb6de  ldloc.1
0xb6df  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_0
0xb6e4  dup
0xb6e5  brtrue.s loc_B6FE
0xb6e7  pop
0xb6e8  ldsfld   class <>c <>c::<>9
0xb6ed  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer)
0xb6f3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb6f8  dup
0xb6f9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_0
0xb6fe  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_1
0xb703  dup
0xb704  brtrue.s loc_B71D
0xb706  pop
0xb707  ldsfld   class <>c <>c::<>9
0xb70c  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity product)
0xb712  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb717  dup
0xb718  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_1
0xb71d  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> <>c::<>9__5_2
0xb722  dup
0xb723  brtrue.s loc_B73C
0xb725  pop
0xb726  ldsfld   class <>c <>c::<>9
0xb72b  ldftn    instance class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<RetrieveEntitlementsForCase>b__5_2(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity product)
0xb731  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::.ctor(object, native int)
0xb736  dup
0xb737  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> <>c::<>9__5_2
0xb73c  call     T0x2B000002
0xb741  ldloc.2
0xb742  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, string> <>c::<>9__5_3
0xb747  dup
0xb748  brtrue.s loc_B761
0xb74a  pop
0xb74b  ldsfld   class <>c <>c::<>9
0xb750  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_3(class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>h__TransparentIdentifier0)
0xb756  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, string>::.ctor(object, native int)
0xb75b  dup
0xb75c  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, string> <>c::<>9__5_3
0xb761  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_4
0xb766  dup
0xb767  brtrue.s loc_B780
0xb769  pop
0xb76a  ldsfld   class <>c <>c::<>9
0xb76f  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_4(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity contact)
0xb775  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb77a  dup
0xb77b  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_4
0xb780  ldsfld   class [mscorlib]System.Func`3<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_5
0xb785  dup
0xb786  brtrue.s loc_B79F
0xb788  pop
0xb789  ldsfld   class <>c <>c::<>9
0xb78e  ldftn    instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity <>c::<RetrieveEntitlementsForCase>b__5_5(class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>h__TransparentIdentifier0, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity contact)
0xb794  newobj   instance void class [mscorlib]System.Func`3<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor(object, native int)
0xb799  dup
0xb79a  stsfld   class [mscorlib]System.Func`3<class <>f__AnonymousType0`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_5
0xb79f  call     T0x2B000003
0xb7a4  stloc.3
0xb7a5  br       loc_B889
0xb7aa  ldloc.0
0xb7ab  brfalse.s loc_B817
0xb7ad  ldloc.1
0xb7ae  brfalse.s loc_B817
0xb7b0  ldloc.0
0xb7b1  ldloc.1
0xb7b2  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_6
0xb7b7  dup
0xb7b8  brtrue.s loc_B7D1
0xb7ba  pop
0xb7bb  ldsfld   class <>c <>c::<>9
0xb7c0  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_6(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer)
0xb7c6  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb7cb  dup
0xb7cc  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_6
0xb7d1  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_7
0xb7d6  dup
0xb7d7  brtrue.s loc_B7F0
0xb7d9  pop
0xb7da  ldsfld   class <>c <>c::<>9
0xb7df  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_7(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity product)
0xb7e5  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb7ea  dup
0xb7eb  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_7
0xb7f0  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_8
0xb7f5  dup
0xb7f6  brtrue.s loc_B80F
0xb7f8  pop
0xb7f9  ldsfld   class <>c <>c::<>9
0xb7fe  ldftn    instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity <>c::<RetrieveEntitlementsForCase>b__5_8(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity product)
0xb804  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor(object, native int)
0xb809  dup
0xb80a  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_8
0xb80f  call     T0x2B000004
0xb814  stloc.3
0xb815  br.s     loc_B889
0xb817  ldloc.0
0xb818  brfalse.s loc_B884
0xb81a  ldloc.2
0xb81b  brfalse.s loc_B884
0xb81d  ldloc.0
0xb81e  ldloc.2
0xb81f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_9
0xb824  dup
0xb825  brtrue.s loc_B83E
0xb827  pop
0xb828  ldsfld   class <>c <>c::<>9
0xb82d  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_9(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer)
0xb833  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb838  dup
0xb839  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_9
0xb83e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_10
0xb843  dup
0xb844  brtrue.s loc_B85D
0xb846  pop
0xb847  ldsfld   class <>c <>c::<>9
0xb84c  ldftn    instance string <>c::<RetrieveEntitlementsForCase>b__5_10(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity contact)
0xb852  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string>::.ctor(object, native int)
0xb857  dup
0xb858  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string> <>c::<>9__5_10
0xb85d  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_11
0xb862  dup
0xb863  brtrue.s loc_B87C
0xb865  pop
0xb866  ldsfld   class <>c <>c::<>9
0xb86b  ldftn    instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity <>c::<RetrieveEntitlementsForCase>b__5_11(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity customer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity contact)
0xb871  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor(object, native int)
0xb876  dup
0xb877  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c::<>9__5_11
0xb87c  call     T0x2B000004
0xb881  stloc.3
0xb882  br.s     loc_B889
0xb884  ldloc.0
0xb885  brfalse.s loc_B889
0xb887  ldloc.0
0xb888  stloc.3
0xb889  ldstr    aEntitlement// "Entitlement"
0xb88e  ldarg.s  5
0xb890  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb895  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0xb89a  stloc.s  4
0xb89c  ldloc.3
0xb89d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::GetEnumerator()
0xb8a2  stloc.s  5
0xb8a4  br.s     loc_B8B9
0xb8a6  ldloc.s  5
0xb8a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Current()
0xb8ad  stloc.s  6
0xb8af  ldloc.s  4
0xb8b1  ldloc.s  6
0xb8b3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0xb8b8  pop
0xb8b9  ldloc.s  5
0xb8bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb8c0  brtrue.s loc_B8A6
0xb8c2  leave.s  loc_B8D0
0xb8c4  ldloc.s  5
0xb8c6  brfalse.s loc_B8CF
0xb8c8  ldloc.s  5
0xb8ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb8cf  endfinally
0xb8d0  ldloc.s  4
0xb8d2  ret
0xb8d3  ldnull
0xb8d4  ret
```
