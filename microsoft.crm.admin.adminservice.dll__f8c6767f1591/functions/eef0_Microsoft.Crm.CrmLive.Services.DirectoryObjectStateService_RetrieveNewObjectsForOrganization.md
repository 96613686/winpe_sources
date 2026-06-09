# Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveNewObjectsForOrganization

- ea: `0xeef0`
- end: `0xf0ef`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveNewObjectsForOrganization`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfaa0`

## callees

- `0xeef0`

## string_xrefs

- `0xf04c`: `DirectoryObjectState`
- `0xef52`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`
- `0xf0a0`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`
- `0xef39`: `DirectoryObjectRevision`
- `0xef6b`: `DirectoryObjectRevision`
- `0xef79`: `DirectoryObjectRevision`
- `0xef87`: `DirectoryObjectRevision`

## pseudocode

```c

```

## disassembly

```asm
0xeef0  ldarg.1
0xeef1  ldstr    aOrganizationid// "organizationId"
0xeef6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xeefb  ldarg.2
0xeefc  ldstr    aBatchSizeMustB// "Batch size must be positive"
0xef01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0xef06  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0xef0b  stloc.0
0xef0c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xef11  stloc.1
0xef12  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xef17  stloc.2
0xef18  ldloc.2
0xef19  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xef1e  ldarg.1
0xef1f  box      [mscorlib]System.Guid
0xef24  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xef29  ldc.i4.2
0xef2a  newarr   [mscorlib]System.String
0xef2f  dup
0xef30  ldc.i4.0
0xef31  ldstr    aContextid// "ContextId"
0xef36  stelem.ref
0xef37  dup
0xef38  ldc.i4.1
0xef39  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xef3e  stelem.ref
0xef3f  stloc.3
0xef40  ldloc.1
0xef41  ldstr    aOrganizationli// "OrganizationLifecycle"
0xef46  ldloc.3
0xef47  ldloc.2
0xef48  ldc.i4   0xB0
0xef4d  ldstr    aRetrievenewobj// "RetrieveNewObjectsForOrganization"
0xef52  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xef57  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xef5c  stloc.s  4
0xef5e  ldloc.s  4
0xef60  brfalse  loc_F0B9
0xef65  ldc.i4.m1
0xef66  conv.i8
0xef67  stloc.s  5
0xef69  ldloc.s  4
0xef6b  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xef70  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xef75  brfalse.s loc_EF98
0xef77  ldloc.s  4
0xef79  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xef7e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xef83  brfalse.s loc_EF98
0xef85  ldloc.s  4
0xef87  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xef8c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xef91  unbox.any [mscorlib]System.Int64
0xef96  stloc.s  5
0xef98  ldloc.s  4
0xef9a  ldstr    aContextid// "ContextId"
0xef9f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xefa4  stloc.s  6
0xefa6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xefab  stloc.2
0xefac  ldloc.2
0xefad  ldstr    aRevision// "Revision"
0xefb2  ldc.i4.1
0xefb3  ldloc.s  5
0xefb5  box      [mscorlib]System.Int64
0xefba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xefbf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xefc4  ldloc.2
0xefc5  ldstr    aContextid// "ContextId"
0xefca  ldloc.s  6
0xefcc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xefd1  ldloc.2
0xefd2  ldstr    aType// "Type"
0xefd7  ldc.i4.5
0xefd8  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0xefdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xefe2  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xefe7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xefec  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xeff1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xeff6  stloc.s  7
0xeff8  ldloc.s  7
0xeffa  ldstr    aRevision// "Revision"
0xefff  ldc.i4.1
0xf000  ldloc.s  5
0xf002  box      [mscorlib]System.Int64
0xf007  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xf00c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf011  ldloc.s  7
0xf013  ldstr    aContextid// "ContextId"
0xf018  ldloc.s  6
0xf01a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf01f  ldloc.s  7
0xf021  ldstr    aType// "Type"
0xf026  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0xf02b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf030  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xf035  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf03a  ldloc.s  7
0xf03c  ldstr    aIstobeapplied// "IsToBeApplied"
0xf041  ldc.i4.1
0xf042  box      [mscorlib]System.Boolean
0xf047  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf04c  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xf051  ldnull
0xf052  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0xf057  stloc.s  8
0xf059  ldloc.s  8
0xf05b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0xf060  ldstr    aRevision// "Revision"
0xf065  ldc.i4.0
0xf066  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0xf06b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0xf070  ldloc.s  8
0xf072  ldc.i4.2
0xf073  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xf078  dup
0xf079  ldc.i4.0
0xf07a  ldloc.2
0xf07b  stelem.ref
0xf07c  dup
0xf07d  ldc.i4.1
0xf07e  ldloc.s  7
0xf080  stelem.ref
0xf081  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0xf086  ldloc.s  8
0xf088  ldarg.2
0xf089  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xf08e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0xf093  ldloc.1
0xf094  ldloc.s  8
0xf096  ldc.i4   0xD0
0xf09b  ldstr    aRetrievenewobj// "RetrieveNewObjectsForOrganization"
0xf0a0  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xf0a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0xf0aa  stloc.s  9
0xf0ac  ldloc.0
0xf0ad  ldloc.s  9
0xf0af  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0xf0b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xf0b9  ldloc.0
0xf0ba  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__5_0
0xf0bf  dup
0xf0c0  brtrue.s loc_F0D9
0xf0c2  pop
0xf0c3  ldsfld   class <>c <>c::<>9
0xf0c8  ldftn    instance object <>c::<RetrieveNewObjectsForOrganization>b__5_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record)
0xf0ce  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object>::.ctor(object, native int)
0xf0d3  dup
0xf0d4  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__5_0
0xf0d9  call     T0x2B000044
0xf0de  stloc.s  0xA
0xf0e0  leave.s  loc_F0EC
0xf0e2  ldloc.1
0xf0e3  brfalse.s loc_F0EB
0xf0e5  ldloc.1
0xf0e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf0eb  endfinally
0xf0ec  ldloc.s  0xA
0xf0ee  ret
```
