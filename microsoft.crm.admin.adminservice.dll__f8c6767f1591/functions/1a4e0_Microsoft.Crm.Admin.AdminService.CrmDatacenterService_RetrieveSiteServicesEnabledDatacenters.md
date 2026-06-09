# Microsoft.Crm.Admin.AdminService.CrmDatacenterService::RetrieveSiteServicesEnabledDatacenters

- ea: `0x1a4e0`
- end: `0x1a58c`
- name: `Microsoft.Crm.Admin.AdminService.CrmDatacenterService::RetrieveSiteServicesEnabledDatacenters`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a4e0`

## string_xrefs

- `0x1a512`: `D:\a\1\s\src\CrmLive\Admin\Datacenter\CrmDatacenterService.cs`
- `0x1a502`: `SiteServicesDisabled`
- `0x1a532`: `SiteServicesDisabled`
- `0x1a53f`: `SiteServicesDisabled`
- `0x1a50d`: `RetrieveSiteServicesEnabledDatacenters`

## pseudocode

```c

```

## disassembly

```asm
0x1a4e0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1a4e5  stloc.0
0x1a4e6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1a4eb  stloc.1
0x1a4ec  ldloc.1
0x1a4ed  ldstr    aDatacenter// "Datacenter"
0x1a4f2  ldc.i4.2
0x1a4f3  newarr   [mscorlib]System.String
0x1a4f8  dup
0x1a4f9  ldc.i4.0
0x1a4fa  ldstr    aId// "Id"
0x1a4ff  stelem.ref
0x1a500  dup
0x1a501  ldc.i4.1
0x1a502  ldstr    aSiteservicesdi// "SiteServicesDisabled"
0x1a507  stelem.ref
0x1a508  ldc.i4   0x141
0x1a50d  ldstr    aRetrievesitese// "RetrieveSiteServicesEnabledDatacenters"
0x1a512  ldstr    aDA1SSrcCrmlive_35// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Datac"...
0x1a517  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x1a51c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1a521  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1a526  stloc.2
0x1a527  br.s     loc_1A567
0x1a529  ldloca.s 2
0x1a52b  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1a530  stloc.3
0x1a531  ldloc.3
0x1a532  ldstr    aSiteservicesdi// "SiteServicesDisabled"
0x1a537  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1a53c  brfalse.s loc_1A550
0x1a53e  ldloc.3
0x1a53f  ldstr    aSiteservicesdi// "SiteServicesDisabled"
0x1a544  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1a549  unbox.any [mscorlib]System.Boolean
0x1a54e  brtrue.s loc_1A567
0x1a550  ldloc.0
0x1a551  ldloc.3
0x1a552  ldstr    aId// "Id"
0x1a557  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1a55c  unbox.any [mscorlib]System.Guid
0x1a561  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1a566  pop
0x1a567  ldloca.s 2
0x1a569  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x1a56e  brtrue.s loc_1A529
0x1a570  leave.s  loc_1A58A
0x1a572  ldloca.s 2
0x1a574  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x1a57a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a57f  endfinally
0x1a580  ldloc.1
0x1a581  brfalse.s loc_1A589
0x1a583  ldloc.1
0x1a584  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a589  endfinally
0x1a58a  ldloc.0
0x1a58b  ret
```
