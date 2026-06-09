# <RetrieveMultiplePaged>d__2`1::MoveNext

- ea: `0x173b0`
- end: `0x174c5`
- name: `<RetrieveMultiplePaged>d__2`1::MoveNext`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x11a30`
- `0x11a50`
- `0x173b0`

## pseudocode

```c

```

## disassembly

```asm
0x173b0  ldarg.0
0x173b1  ldfld    int32 class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>1__state
0x173b6  stloc.1
0x173b7  ldloc.1
0x173b8  brfalse.s loc_173C8
0x173ba  ldloc.1
0x173bb  ldc.i4.1
0x173bc  beq      loc_1744B
0x173c1  ldc.i4.0
0x173c2  stloc.0
0x173c3  leave    loc_174C3
0x173c8  ldarg.0
0x173c9  ldc.i4.m1
0x173ca  stfld    int32 class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>1__state
0x173cf  ldarg.0
0x173d0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression class <RetrieveMultiplePaged>d__2`1<var<u1>>::query
0x173d5  ldc.i4   0x1388
0x173da  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::CreateFirstPagePagingInfo(int32 numberOfRecordsPerResultPage)
0x173df  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_PageInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo)
0x173e4  ldarg.0
0x173e5  ldarg.0
0x173e6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService class <RetrieveMultiplePaged>d__2`1<var<u1>>::organizationService
0x173eb  ldarg.0
0x173ec  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression class <RetrieveMultiplePaged>d__2`1<var<u1>>::query
0x173f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x173f6  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x173fb  ldarg.0
0x173fc  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x17401  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x17406  brfalse.s loc_1746D
0x17408  ldarg.0
0x17409  ldarg.0
0x1740a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x1740f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x17414  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x17419  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>7__wrap1
0x1741e  ldarg.0
0x1741f  ldc.i4.s 0xFD
0x17421  stfld    int32 class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>1__state
0x17426  br.s     loc_17453
0x17428  ldarg.0
0x17429  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>7__wrap1
0x1742e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x17433  callvirt T0x2B000031
0x17438  stloc.2
0x17439  ldarg.0
0x1743a  ldloc.2
0x1743b  stfld    var<u1> class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>2__current
0x17440  ldarg.0
0x17441  ldc.i4.1
0x17442  stfld    int32 class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>1__state
0x17447  ldc.i4.1
0x17448  stloc.0
0x17449  leave.s  loc_174C3
0x1744b  ldarg.0
0x1744c  ldc.i4.s 0xFD
0x1744e  stfld    int32 class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>1__state
0x17453  ldarg.0
0x17454  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>7__wrap1
0x17459  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1745e  brtrue.s loc_17428
0x17460  ldarg.0
0x17461  call     instance void class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>m__Finally1()
0x17466  ldarg.0
0x17467  ldnull
0x17468  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__2`1<var<u1>>::<>7__wrap1
0x1746d  ldarg.0
0x1746e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x17473  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x17478  brfalse.s loc_17495
0x1747a  ldarg.0
0x1747b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression class <RetrieveMultiplePaged>d__2`1<var<u1>>::query
0x17480  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0x17485  ldarg.0
0x17486  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x1748b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x17490  call     void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::SetPagingInfoForNextPageRetrieval(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo pagingInfo, string pagingCookie)
0x17495  ldarg.0
0x17496  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__2`1<var<u1>>::<returnCollection>5__1
0x1749b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x174a0  brfalse.s loc_174B8
0x174a2  ldarg.0
0x174a3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression class <RetrieveMultiplePaged>d__2`1<var<u1>>::query
0x174a8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0x174ad  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::get_PageNumber()
0x174b2  ldc.i4.1
0x174b3  ble      loc_173E4
0x174b8  ldc.i4.0
0x174b9  stloc.0
0x174ba  leave.s  loc_174C3
0x174bc  ldarg.0
0x174bd  call     instance void class <RetrieveMultiplePaged>d__2`1<var<u1>>::System.IDisposable.Dispose()
0x174c2  endfinally
0x174c3  ldloc.0
0x174c4  ret
```
