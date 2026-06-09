# <GetChangeRequests>d__78::MoveNext

- ea: `0x23750`
- end: `0x238d9`
- name: `<GetChangeRequests>d__78::MoveNext`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x3c30`
- `0x145a0`
- `0x145d0`
- `0x14960`
- `0x23700`
- `0x23750`
- `0x238e0`
- `0x23900`

## pseudocode

```c

```

## disassembly

```asm
0x23750  ldarg.0
0x23751  ldfld    int32 <GetChangeRequests>d__78::<>1__state
0x23756  stloc.1
0x23757  ldarg.0
0x23758  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <GetChangeRequests>d__78::<>4__this
0x2375d  stloc.2
0x2375e  ldloc.1
0x2375f  switch   loc_23777, loc_23830, loc_238AA
0x23770  ldc.i4.0
0x23771  stloc.0
0x23772  leave    loc_238D7
0x23777  ldarg.0
0x23778  ldc.i4.m1
0x23779  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x2377e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>::.ctor()
0x23783  dup
0x23784  ldarg.0
0x23785  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequests>d__78::entity
0x2378a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x2378f  stloc.3
0x23790  ldarg.0
0x23791  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor()
0x23796  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequests>d__78::<localCircularLinks>5__2
0x2379b  ldarg.0
0x2379c  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequests>d__78::entity
0x237a1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x237a6  stloc.s  5
0x237a8  ldc.i4.0
0x237a9  stloc.s  6
0x237ab  ldloca.s 5
0x237ad  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x237b2  ldloc.s  6
0x237b4  ceq
0x237b6  ldloca.s 5
0x237b8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x237bd  and
0x237be  brtrue.s loc_237DB
0x237c0  ldloc.2
0x237c1  ldarg.0
0x237c2  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequests>d__78::results
0x237c7  ldarg.0
0x237c8  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequests>d__78::entity
0x237cd  ldloc.3
0x237ce  ldarg.0
0x237cf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequests>d__78::<localCircularLinks>5__2
0x237d4  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromChangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x237d9  br.s     loc_237F4
0x237db  ldloc.2
0x237dc  ldarg.0
0x237dd  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequests>d__78::results
0x237e2  ldarg.0
0x237e3  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequests>d__78::entity
0x237e8  ldloc.3
0x237e9  ldarg.0
0x237ea  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequests>d__78::<localCircularLinks>5__2
0x237ef  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromUnchangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x237f4  stloc.s  4
0x237f6  ldarg.0
0x237f7  ldloc.s  4
0x237f9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x237fe  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x23803  ldarg.0
0x23804  ldc.i4.s 0xFD
0x23806  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x2380b  br.s     loc_23838
0x2380d  ldarg.0
0x2380e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x23813  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x23818  stloc.s  7
0x2381a  ldarg.0
0x2381b  ldloc.s  7
0x2381d  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequests>d__78::<>2__current
0x23822  ldarg.0
0x23823  ldc.i4.1
0x23824  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x23829  ldc.i4.1
0x2382a  stloc.0
0x2382b  leave    loc_238D7
0x23830  ldarg.0
0x23831  ldc.i4.s 0xFD
0x23833  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x23838  ldarg.0
0x23839  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x2383e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23843  brtrue.s loc_2380D
0x23845  ldarg.0
0x23846  call     instance void <GetChangeRequests>d__78::<>m__Finally1()
0x2384b  ldarg.0
0x2384c  ldnull
0x2384d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x23852  ldarg.0
0x23853  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequests>d__78::<localCircularLinks>5__2
0x23858  call     T0x2B00007A
0x2385d  brfalse.s loc_238CC
0x2385f  ldloc.2
0x23860  ldarg.0
0x23861  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequests>d__78::<localCircularLinks>5__2
0x23866  ldarg.0
0x23867  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequests>d__78::results
0x2386c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateResults(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> links, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x23871  stloc.s  8
0x23873  ldarg.0
0x23874  ldloc.s  8
0x23876  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x2387b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x23880  ldarg.0
0x23881  ldc.i4.s 0xFC
0x23883  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x23888  br.s     loc_238B2
0x2388a  ldarg.0
0x2388b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x23890  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x23895  stloc.s  9
0x23897  ldarg.0
0x23898  ldloc.s  9
0x2389a  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequests>d__78::<>2__current
0x2389f  ldarg.0
0x238a0  ldc.i4.2
0x238a1  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x238a6  ldc.i4.1
0x238a7  stloc.0
0x238a8  leave.s  loc_238D7
0x238aa  ldarg.0
0x238ab  ldc.i4.s 0xFC
0x238ad  stfld    int32 <GetChangeRequests>d__78::<>1__state
0x238b2  ldarg.0
0x238b3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x238b8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x238bd  brtrue.s loc_2388A
0x238bf  ldarg.0
0x238c0  call     instance void <GetChangeRequests>d__78::<>m__Finally2()
0x238c5  ldarg.0
0x238c6  ldnull
0x238c7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequests>d__78::<>7__wrap2
0x238cc  ldc.i4.0
0x238cd  stloc.0
0x238ce  leave.s  loc_238D7
0x238d0  ldarg.0
0x238d1  call     instance void <GetChangeRequests>d__78::System.IDisposable.Dispose()
0x238d6  endfinally
0x238d7  ldloc.0
0x238d8  ret
```
