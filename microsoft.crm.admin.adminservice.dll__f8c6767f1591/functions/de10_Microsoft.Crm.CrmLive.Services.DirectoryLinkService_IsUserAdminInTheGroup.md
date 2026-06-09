# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsUserAdminInTheGroup

- ea: `0xde10`
- end: `0xdefe`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsUserAdminInTheGroup`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xdda0`

## callees

- `0xde10`
- `0x3d4b0`

## string_xrefs

- `0xdebe`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xde97`: `DirectoryObjectState`
- `0xde85`: `DeletedOn`

## pseudocode

```c

```

## disassembly

```asm
0xde10  newobj   instance void <>c__DisplayClass11_0::.ctor()
0xde15  stloc.0
0xde16  ldloc.0
0xde17  ldarg.0
0xde18  stfld    class Microsoft.Crm.CrmLive.Services.DirectoryLinkService <>c__DisplayClass11_0::<>4__this
0xde1d  ldloc.0
0xde1e  ldarg.2
0xde1f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::contextId
0xde24  ldloc.0
0xde25  ldarg.3
0xde26  stfld    string[] <>c__DisplayClass11_0::adminGroups
0xde2b  ldarg.1
0xde2c  ldstr    aUserprincipaln// "userPrincipalName"
0xde31  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xde36  ldloc.0
0xde37  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::contextId
0xde3c  ldstr    aContextid_0// "contextId"
0xde41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xde46  ldloc.0
0xde47  ldfld    string[] <>c__DisplayClass11_0::adminGroups
0xde4c  ldstr    aAdmingroups// "adminGroups"
0xde51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xde56  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xde5b  stloc.1
0xde5c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xde61  stloc.2
0xde62  ldloc.2
0xde63  ldstr    aUserprincipaln_0// "UserPrincipalName"
0xde68  ldarg.1
0xde69  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xde6e  ldloc.2
0xde6f  ldstr    aContextid// "ContextId"
0xde74  ldloc.0
0xde75  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::contextId
0xde7a  box      [mscorlib]System.Guid
0xde7f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xde84  ldloc.2
0xde85  ldstr    aDeletedon// "DeletedOn"
0xde8a  ldc.i4.0
0xde8b  ldnull
0xde8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xde91  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xde96  ldloc.1
0xde97  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xde9c  ldc.i4.1
0xde9d  newarr   [mscorlib]System.String
0xdea2  dup
0xdea3  ldc.i4.0
0xdea4  ldstr    aObjectid_0// "ObjectId"
0xdea9  stelem.ref
0xdeaa  ldc.i4.1
0xdeab  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xdeb0  dup
0xdeb1  ldc.i4.0
0xdeb2  ldloc.2
0xdeb3  stelem.ref
0xdeb4  ldc.i4   0x10A
0xdeb9  ldstr    aIsuseradminint// "IsUserAdminInTheGroup"
0xdebe  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xdec3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xdec8  stloc.3
0xdec9  ldloc.3
0xdeca  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xdecf  brfalse.s loc_DED6
0xded1  ldc.i4.0
0xded2  stloc.s  4
0xded4  leave.s  loc_DEFB
0xded6  ldloc.3
0xded7  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xdedc  ldloc.0
0xdedd  ldftn    instance bool <>c__DisplayClass11_0::<IsUserAdminInTheGroup>b__0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag user)
0xdee3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xdee8  call     T0x2B00003E
0xdeed  stloc.s  4
0xdeef  leave.s  loc_DEFB
0xdef1  ldloc.1
0xdef2  brfalse.s loc_DEFA
0xdef4  ldloc.1
0xdef5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdefa  endfinally
0xdefb  ldloc.s  4
0xdefd  ret
```
