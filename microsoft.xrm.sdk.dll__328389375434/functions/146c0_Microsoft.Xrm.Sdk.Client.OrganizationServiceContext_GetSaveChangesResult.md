# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetSaveChangesResult

- ea: `0x146c0`
- end: `0x14758`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetSaveChangesResult`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x23a20`

## callees

- `0x3bc0`
- `0x3bd0`
- `0x7e80`
- `0x12670`
- `0x12700`
- `0x14510`
- `0x14640`
- `0x146c0`
- `0x14f30`

## pseudocode

```c

```

## disassembly

```asm
0x146c0  ldarg.2
0x146c1  ldarg.0
0x146c2  ldfld    valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_concurrencyBehavior
0x146c7  call     class Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRequest(class Microsoft.Xrm.Sdk.Entity entity, valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior concurrencyBehavior)
0x146cc  stloc.0
0x146cd  ldloc.0
0x146ce  isinst   Microsoft.Xrm.Sdk.Messages.CreateRequest
0x146d3  stloc.1
0x146d4  ldloc.1
0x146d5  brfalse.s loc_14722
0x146d7  ldloc.1
0x146d8  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.CreateRequest::get_Target()
0x146dd  ldnull
0x146de  ldftn    void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId(class Microsoft.Xrm.Sdk.Entity entity)
0x146e4  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x146e9  ldsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__83_0
0x146ee  dup
0x146ef  brtrue.s loc_14708
0x146f1  pop
0x146f2  ldsfld   class <>c <>c::<>9
0x146f7  ldftn    instance void <>c::<GetSaveChangesResult>b__83_0(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x146fd  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x14702  dup
0x14703  stsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__83_0
0x14708  ldc.i4.1
0x14709  newarr   Microsoft.Xrm.Sdk.Entity
0x1470e  dup
0x1470f  ldc.i4.0
0x14710  ldloc.1
0x14711  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.CreateRequest::get_Target()
0x14716  stelem.ref
0x14717  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path)
0x1471c  call     T0x2B00002B
0x14721  pop
0x14722  ldarg.0
0x14723  ldloc.0
0x14724  ldarg.1
0x14725  call     instance class Microsoft.Xrm.Sdk.SaveChangesResult Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChange(class Microsoft.Xrm.Sdk.OrganizationRequest request, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x1472a  dup
0x1472b  callvirt instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.SaveChangesResult::get_Response()
0x14730  isinst   Microsoft.Xrm.Sdk.Messages.CreateResponse
0x14735  stloc.2
0x14736  ldloc.2
0x14737  brfalse.s loc_14757
0x14739  ldarg.2
0x1473a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x1473f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14744  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14749  brfalse.s loc_14757
0x1474b  ldarg.2
0x1474c  ldloc.2
0x1474d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Messages.CreateResponse::get_id()
0x14752  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid value)
0x14757  ret
```
