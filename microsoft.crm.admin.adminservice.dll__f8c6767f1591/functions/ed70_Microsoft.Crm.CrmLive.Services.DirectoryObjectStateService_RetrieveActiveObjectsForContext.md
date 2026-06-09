# Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveActiveObjectsForContext

- ea: `0xed70`
- end: `0xeee4`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveActiveObjectsForContext`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xed70`
- `0x3d690`

## string_xrefs

- `0xee34`: `DirectoryObjectState`
- `0xee00`: `DeletedOn`
- `0xee84`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xed70  newobj   instance void <>c__DisplayClass4_0::.ctor()
0xed75  stloc.0
0xed76  ldloc.0
0xed77  ldarg.s  4
0xed79  stfld    int64 <>c__DisplayClass4_0::maximumRevision
0xed7e  ldarg.2
0xed7f  ldstr    aType_0// "type"
0xed84  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xed89  ldarg.s  5
0xed8b  ldstr    aBatchsize// "batchSize"
0xed90  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0xed95  ldarg.1
0xed96  ldstr    aContextid_0// "contextId"
0xed9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xeda0  ldarg.3
0xeda1  ldloc.0
0xeda2  ldfld    int64 <>c__DisplayClass4_0::maximumRevision
0xeda7  ble.s    loc_EDB4
0xeda9  ldstr    aMinimumrevisio// "minimumRevision must be less than maxim"...
0xedae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0xedb3  throw
0xedb4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0xedb9  stloc.1
0xedba  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xedbf  stloc.2
0xedc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xedc5  stloc.3
0xedc6  ldloc.3
0xedc7  ldstr    aRevision// "Revision"
0xedcc  ldc.i4.1
0xedcd  ldarg.3
0xedce  box      [mscorlib]System.Int64
0xedd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xedd8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xeddd  ldloc.3
0xedde  ldstr    aType// "Type"
0xede3  ldarg.2
0xede4  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xede9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xedee  ldloc.3
0xedef  ldstr    aContextid// "ContextId"
0xedf4  ldarg.1
0xedf5  box      [mscorlib]System.Guid
0xedfa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xedff  ldloc.3
0xee00  ldstr    aDeletedon// "DeletedOn"
0xee05  ldc.i4.0
0xee06  ldnull
0xee07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xee0c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xee11  ldarg.2
0xee12  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0xee17  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xee1c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xee21  brfalse.s loc_EE34
0xee23  ldloc.3
0xee24  ldstr    aIstobeapplied// "IsToBeApplied"
0xee29  ldc.i4.1
0xee2a  box      [mscorlib]System.Boolean
0xee2f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xee34  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xee39  ldnull
0xee3a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0xee3f  stloc.s  4
0xee41  ldloc.s  4
0xee43  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0xee48  ldstr    aRevision// "Revision"
0xee4d  ldc.i4.0
0xee4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0xee53  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0xee58  ldloc.s  4
0xee5a  ldc.i4.1
0xee5b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xee60  dup
0xee61  ldc.i4.0
0xee62  ldloc.3
0xee63  stelem.ref
0xee64  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0xee69  ldloc.s  4
0xee6b  ldarg.s  5
0xee6d  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xee72  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0xee77  ldloc.2
0xee78  ldloc.s  4
0xee7a  ldc.i4   0x99
0xee7f  ldstr    aRetrieveactive// "RetrieveActiveObjectsForContext"
0xee84  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xee89  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0xee8e  stloc.s  5
0xee90  ldloc.1
0xee91  ldloc.s  5
0xee93  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0xee98  ldloc.0
0xee99  ldftn    instance bool <>c__DisplayClass4_0::<RetrieveActiveObjectsForContext>b__0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag x)
0xee9f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xeea4  call     T0x2B000040
0xeea9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xeeae  ldloc.1
0xeeaf  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__4_1
0xeeb4  dup
0xeeb5  brtrue.s loc_EECE
0xeeb7  pop
0xeeb8  ldsfld   class <>c <>c::<>9
0xeebd  ldftn    instance object <>c::<RetrieveActiveObjectsForContext>b__4_1(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record)
0xeec3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object>::.ctor(object, native int)
0xeec8  dup
0xeec9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__4_1
0xeece  call     T0x2B000044
0xeed3  stloc.s  6
0xeed5  leave.s  loc_EEE1
0xeed7  ldloc.2
0xeed8  brfalse.s loc_EEE0
0xeeda  ldloc.2
0xeedb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeee0  endfinally
0xeee1  ldloc.s  6
0xeee3  ret
```
