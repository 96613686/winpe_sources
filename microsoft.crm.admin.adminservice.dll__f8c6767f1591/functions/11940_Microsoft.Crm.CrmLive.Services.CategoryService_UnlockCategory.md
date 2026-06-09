# Microsoft.Crm.CrmLive.Services.CategoryService::UnlockCategory

- ea: `0x11940`
- end: `0x11ace`
- name: `Microsoft.Crm.CrmLive.Services.CategoryService::UnlockCategory`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x11940`
- `0x11dc0`

## string_xrefs

- `0x119b2`: `D:\a\1\s\src\CrmLive\Admin\RestrictedOffers\CategoryService.cs`
- `0x11aaa`: `D:\a\1\s\src\CrmLive\Admin\RestrictedOffers\CategoryService.cs`
- `0x11a36`: `Organization already has access to category`

## pseudocode

```c

```

## disassembly

```asm
0x11940  ldarg.1
0x11941  ldstr    aOrganizationid// "organizationId"
0x11946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1194b  ldarg.2
0x1194c  ldstr    aCategory// "category"
0x11951  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x11956  ldarg.1
0x11957  ldc.i4.s 0xB
0x11959  ldstr    aRequestToUnloc// "Request to unlock category {0} for orga"...
0x1195e  ldc.i4.2
0x1195f  newarr   [mscorlib]System.Object
0x11964  dup
0x11965  ldc.i4.0
0x11966  ldarg.2
0x11967  stelem.ref
0x11968  dup
0x11969  ldc.i4.1
0x1196a  ldarg.1
0x1196b  box      [mscorlib]System.Guid
0x11970  stelem.ref
0x11971  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11976  ldarg.2
0x11977  call     void Microsoft.Crm.CrmLive.Services.CategoryService::ThrowIfCategoryNotFound(string category)
0x1197c  ldstr    aUnlockcategory// "UnlockCategoryLock"
0x11981  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string)
0x11986  stloc.0
0x11987  ldnull
0x11988  stloc.1
0x11989  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1198e  stloc.s  4
0x11990  ldloc.s  4
0x11992  ldstr    aOrganization// "Organization"
0x11997  ldarg.1
0x11998  box      [mscorlib]System.Guid
0x1199d  ldc.i4.1
0x1199e  newarr   [mscorlib]System.String
0x119a3  dup
0x119a4  ldc.i4.0
0x119a5  ldstr    aUnlockedcatego// "UnlockedCategories"
0x119aa  stelem.ref
0x119ab  ldc.i4.s 0x4D
0x119ad  ldstr    aUnlockcategory_0// "UnlockCategory"
0x119b2  ldstr    aDA1SSrcCrmlive_22// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Restr"...
0x119b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x119bc  stloc.1
0x119bd  leave.s  loc_119CB
0x119bf  ldloc.s  4
0x119c1  brfalse.s loc_119CA
0x119c3  ldloc.s  4
0x119c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x119ca  endfinally
0x119cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x119d0  stloc.2
0x119d1  ldloc.2
0x119d2  ldstr    aUnlockedcatego// "UnlockedCategories"
0x119d7  ldarg.2
0x119d8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x119dd  ldloc.1
0x119de  ldstr    aUnlockedcatego// "UnlockedCategories"
0x119e3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x119e8  isinst   [mscorlib]System.String
0x119ed  stloc.3
0x119ee  ldarg.1
0x119ef  ldc.i4.s 0xB
0x119f1  ldstr    aRetrievedCateg// "Retrieved category string: {0}"
0x119f6  ldc.i4.1
0x119f7  newarr   [mscorlib]System.Object
0x119fc  dup
0x119fd  ldc.i4.0
0x119fe  ldloc.3
0x119ff  stelem.ref
0x11a00  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11a05  ldloc.3
0x11a06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11a0b  brtrue.s loc_11A70
0x11a0d  ldloc.3
0x11a0e  ldc.i4.1
0x11a0f  newarr   [mscorlib]System.Char
0x11a14  dup
0x11a15  ldc.i4.0
0x11a16  ldc.i4.s 0x3B
0x11a18  stelem.i2
0x11a19  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x11a1e  stloc.s  5
0x11a20  ldc.i4.0
0x11a21  stloc.s  6
0x11a23  br.s     loc_11A51
0x11a25  ldloc.s  5
0x11a27  ldloc.s  6
0x11a29  ldelem.ref
0x11a2a  ldarg.2
0x11a2b  ldc.i4.5
0x11a2c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x11a31  brfalse.s loc_11A4B
0x11a33  ldarg.1
0x11a34  ldc.i4.s 0xB
0x11a36  ldstr    aOrganizationAl// "Organization already has access to cate"...
0x11a3b  ldc.i4.0
0x11a3c  newarr   [mscorlib]System.Object
0x11a41  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11a46  leave    loc_11ACD
0x11a4b  ldloc.s  6
0x11a4d  ldc.i4.1
0x11a4e  add
0x11a4f  stloc.s  6
0x11a51  ldloc.s  6
0x11a53  ldloc.s  5
0x11a55  ldlen
0x11a56  conv.i4
0x11a57  blt.s    loc_11A25
0x11a59  ldloc.2
0x11a5a  ldstr    aUnlockedcatego// "UnlockedCategories"
0x11a5f  ldloc.3
0x11a60  ldstr    asc_564AC// ";"
0x11a65  ldarg.2
0x11a66  call     string [mscorlib]System.String::Concat(string, string, string)
0x11a6b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11a70  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x11a75  stloc.s  7
0x11a77  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x11a7c  stloc.s  8
0x11a7e  ldloc.s  8
0x11a80  ldstr    aId// "Id"
0x11a85  ldarg.1
0x11a86  box      [mscorlib]System.Guid
0x11a8b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11a90  ldloc.s  7
0x11a92  ldstr    aOrganization// "Organization"
0x11a97  ldloc.2
0x11a98  ldc.i4.1
0x11a99  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x11a9e  dup
0x11a9f  ldc.i4.0
0x11aa0  ldloc.s  8
0x11aa2  stelem.ref
0x11aa3  ldc.i4.s 0x70
0x11aa5  ldstr    aUnlockcategory_0// "UnlockCategory"
0x11aaa  ldstr    aDA1SSrcCrmlive_22// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Restr"...
0x11aaf  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x11ab4  pop
0x11ab5  leave.s  loc_11ACD
0x11ab7  ldloc.s  7
0x11ab9  brfalse.s loc_11AC2
0x11abb  ldloc.s  7
0x11abd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ac2  endfinally
0x11ac3  ldloc.0
0x11ac4  brfalse.s loc_11ACC
0x11ac6  ldloc.0
0x11ac7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11acc  endfinally
0x11acd  ret
```
