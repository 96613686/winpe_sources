# <GetChangeRequestsFromChangedTree>d__79::MoveNext

- ea: `0x23a20`
- end: `0x23bb6`
- name: `<GetChangeRequestsFromChangedTree>d__79::MoveNext`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14600`
- `0x146c0`
- `0x14760`
- `0x14960`
- `0x239e0`
- `0x23a20`
- `0x23bc0`
- `0x23be0`

## pseudocode

```c

```

## disassembly

```asm
0x23a20  ldarg.0
0x23a21  ldfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23a26  stloc.1
0x23a27  ldarg.0
0x23a28  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <GetChangeRequestsFromChangedTree>d__79::<>4__this
0x23a2d  stloc.2
0x23a2e  ldloc.1
0x23a2f  switch   loc_23A4B, loc_23AD0, loc_23B1C, loc_23B87
0x23a44  ldc.i4.0
0x23a45  stloc.0
0x23a46  leave    loc_23BB4
0x23a4b  ldarg.0
0x23a4c  ldc.i4.m1
0x23a4d  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23a52  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>::.ctor()
0x23a57  dup
0x23a58  ldarg.0
0x23a59  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromChangedTree>d__79::entity
0x23a5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x23a63  stloc.3
0x23a64  ldarg.0
0x23a65  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor()
0x23a6a  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromChangedTree>d__79::<localCircularLinks>5__2
0x23a6f  ldloc.2
0x23a70  ldarg.0
0x23a71  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromChangedTree>d__79::results
0x23a76  ldarg.0
0x23a77  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromChangedTree>d__79::entity
0x23a7c  ldloc.3
0x23a7d  ldarg.0
0x23a7e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromChangedTree>d__79::<localCircularLinks>5__2
0x23a83  ldarg.0
0x23a84  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromChangedTree>d__79::path
0x23a89  ldarg.0
0x23a8a  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromChangedTree>d__79::circularLinks
0x23a8f  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromSubtree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> localPath, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> localCircularLinks, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x23a94  stloc.s  4
0x23a96  ldarg.0
0x23a97  ldloc.s  4
0x23a99  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x23a9e  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23aa3  ldarg.0
0x23aa4  ldc.i4.s 0xFD
0x23aa6  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23aab  br.s     loc_23AD8
0x23aad  ldarg.0
0x23aae  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23ab3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x23ab8  stloc.s  6
0x23aba  ldarg.0
0x23abb  ldloc.s  6
0x23abd  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromChangedTree>d__79::<>2__current
0x23ac2  ldarg.0
0x23ac3  ldc.i4.1
0x23ac4  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23ac9  ldc.i4.1
0x23aca  stloc.0
0x23acb  leave    loc_23BB4
0x23ad0  ldarg.0
0x23ad1  ldc.i4.s 0xFD
0x23ad3  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23ad8  ldarg.0
0x23ad9  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23ade  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23ae3  brtrue.s loc_23AAD
0x23ae5  ldarg.0
0x23ae6  call     instance void <GetChangeRequestsFromChangedTree>d__79::<>m__Finally1()
0x23aeb  ldarg.0
0x23aec  ldnull
0x23aed  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23af2  ldloc.2
0x23af3  ldarg.0
0x23af4  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromChangedTree>d__79::results
0x23af9  ldarg.0
0x23afa  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromChangedTree>d__79::entity
0x23aff  call     instance class Microsoft.Xrm.Sdk.SaveChangesResult Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetSaveChangesResult(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity)
0x23b04  stloc.s  5
0x23b06  ldarg.0
0x23b07  ldloc.s  5
0x23b09  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromChangedTree>d__79::<>2__current
0x23b0e  ldarg.0
0x23b0f  ldc.i4.2
0x23b10  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23b15  ldc.i4.1
0x23b16  stloc.0
0x23b17  leave    loc_23BB4
0x23b1c  ldarg.0
0x23b1d  ldc.i4.m1
0x23b1e  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23b23  ldloc.2
0x23b24  ldarg.0
0x23b25  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromChangedTree>d__79::entity
0x23b2a  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachOnSave(class Microsoft.Xrm.Sdk.Entity entity)
0x23b2f  ldarg.0
0x23b30  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromChangedTree>d__79::<localCircularLinks>5__2
0x23b35  call     T0x2B00007A
0x23b3a  brfalse.s loc_23BA9
0x23b3c  ldloc.2
0x23b3d  ldarg.0
0x23b3e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromChangedTree>d__79::<localCircularLinks>5__2
0x23b43  ldarg.0
0x23b44  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromChangedTree>d__79::results
0x23b49  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateResults(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> links, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x23b4e  stloc.s  7
0x23b50  ldarg.0
0x23b51  ldloc.s  7
0x23b53  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x23b58  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23b5d  ldarg.0
0x23b5e  ldc.i4.s 0xFC
0x23b60  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23b65  br.s     loc_23B8F
0x23b67  ldarg.0
0x23b68  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23b6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x23b72  stloc.s  8
0x23b74  ldarg.0
0x23b75  ldloc.s  8
0x23b77  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromChangedTree>d__79::<>2__current
0x23b7c  ldarg.0
0x23b7d  ldc.i4.3
0x23b7e  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23b83  ldc.i4.1
0x23b84  stloc.0
0x23b85  leave.s  loc_23BB4
0x23b87  ldarg.0
0x23b88  ldc.i4.s 0xFC
0x23b8a  stfld    int32 <GetChangeRequestsFromChangedTree>d__79::<>1__state
0x23b8f  ldarg.0
0x23b90  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23b95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23b9a  brtrue.s loc_23B67
0x23b9c  ldarg.0
0x23b9d  call     instance void <GetChangeRequestsFromChangedTree>d__79::<>m__Finally2()
0x23ba2  ldarg.0
0x23ba3  ldnull
0x23ba4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromChangedTree>d__79::<>7__wrap2
0x23ba9  ldc.i4.0
0x23baa  stloc.0
0x23bab  leave.s  loc_23BB4
0x23bad  ldarg.0
0x23bae  call     instance void <GetChangeRequestsFromChangedTree>d__79::System.IDisposable.Dispose()
0x23bb3  endfinally
0x23bb4  ldloc.0
0x23bb5  ret
```
