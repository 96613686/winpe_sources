# <RetrieveMultiplePaged>d__3`1::MoveNext

- ea: `0x175d0`
- end: `0x17713`
- name: `<RetrieveMultiplePaged>d__3`1::MoveNext`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11a70`
- `0x175d0`

## pseudocode

```c

```

## disassembly

```asm
0x175d0  ldarg.0
0x175d1  ldfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>1__state
0x175d6  stloc.1
0x175d7  ldloc.1
0x175d8  brfalse.s loc_175E8
0x175da  ldloc.1
0x175db  ldc.i4.1
0x175dc  beq      loc_1768C
0x175e1  ldc.i4.0
0x175e2  stloc.0
0x175e3  leave    loc_17711
0x175e8  ldarg.0
0x175e9  ldc.i4.m1
0x175ea  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>1__state
0x175ef  ldarg.0
0x175f0  ldc.i4.1
0x175f1  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<page>5__3
0x175f6  ldarg.0
0x175f7  ldarg.0
0x175f8  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression class <RetrieveMultiplePaged>d__3`1<var<u1>>::expression
0x175fd  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::get_Query()
0x17602  ldarg.0
0x17603  ldfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<page>5__3
0x17608  ldstr    asc_238BC// ""
0x1760d  call     string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::CreatePagingFetchXml(string xml, int32 page, [opt] string cookie)
0x17612  stfld    string class <RetrieveMultiplePaged>d__3`1<var<u1>>::<fetchWithPaging>5__1
0x17617  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x1761c  pop
0x1761d  ldarg.0
0x1761e  ldarg.0
0x1761f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService class <RetrieveMultiplePaged>d__3`1<var<u1>>::organizationService
0x17624  ldarg.0
0x17625  ldfld    string class <RetrieveMultiplePaged>d__3`1<var<u1>>::<fetchWithPaging>5__1
0x1762a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x1762f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x17634  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x17639  ldarg.0
0x1763a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x1763f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x17644  brfalse.s loc_176AE
0x17646  ldarg.0
0x17647  ldarg.0
0x17648  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x1764d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x17652  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x17657  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>7__wrap1
0x1765c  ldarg.0
0x1765d  ldc.i4.s 0xFD
0x1765f  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>1__state
0x17664  br.s     loc_17694
0x17666  ldarg.0
0x17667  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>7__wrap1
0x1766c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x17671  callvirt T0x2B000031
0x17676  stloc.2
0x17677  ldarg.0
0x17678  ldloc.2
0x17679  stfld    var<u1> class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>2__current
0x1767e  ldarg.0
0x1767f  ldc.i4.1
0x17680  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>1__state
0x17685  ldc.i4.1
0x17686  stloc.0
0x17687  leave    loc_17711
0x1768c  ldarg.0
0x1768d  ldc.i4.s 0xFD
0x1768f  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>1__state
0x17694  ldarg.0
0x17695  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>7__wrap1
0x1769a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1769f  brtrue.s loc_17666
0x176a1  ldarg.0
0x176a2  call     instance void class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>m__Finally1()
0x176a7  ldarg.0
0x176a8  ldnull
0x176a9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> class <RetrieveMultiplePaged>d__3`1<var<u1>>::<>7__wrap1
0x176ae  ldarg.0
0x176af  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x176b4  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x176b9  brfalse.s loc_176ED
0x176bb  ldarg.0
0x176bc  ldarg.0
0x176bd  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression class <RetrieveMultiplePaged>d__3`1<var<u1>>::expression
0x176c2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::get_Query()
0x176c7  ldarg.0
0x176c8  ldfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<page>5__3
0x176cd  ldc.i4.1
0x176ce  add
0x176cf  stloc.3
0x176d0  ldarg.0
0x176d1  ldloc.3
0x176d2  stfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<page>5__3
0x176d7  ldloc.3
0x176d8  ldarg.0
0x176d9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x176de  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x176e3  call     string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::CreatePagingFetchXml(string xml, int32 page, [opt] string cookie)
0x176e8  stfld    string class <RetrieveMultiplePaged>d__3`1<var<u1>>::<fetchWithPaging>5__1
0x176ed  ldarg.0
0x176ee  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection class <RetrieveMultiplePaged>d__3`1<var<u1>>::<returnCollection>5__2
0x176f3  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x176f8  brfalse.s loc_17706
0x176fa  ldarg.0
0x176fb  ldfld    int32 class <RetrieveMultiplePaged>d__3`1<var<u1>>::<page>5__3
0x17700  ldc.i4.1
0x17701  ble      loc_1761D
0x17706  ldc.i4.0
0x17707  stloc.0
0x17708  leave.s  loc_17711
0x1770a  ldarg.0
0x1770b  call     instance void class <RetrieveMultiplePaged>d__3`1<var<u1>>::System.IDisposable.Dispose()
0x17710  endfinally
0x17711  ldloc.0
0x17712  ret
```
