# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetObjectQueryBySyncDataBehavior

- ea: `0x2b050`
- end: `0x2b231`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetObjectQueryBySyncDataBehavior`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2af00`

## callees

- `0xf4b0`
- `0x2b050`

## string_xrefs

- `0x2b0f1`: `DirectoryObjectState`
- `0x2b1e7`: `DirectoryObjectState`

## pseudocode

```c

```

## disassembly

```asm
0x2b050  ldarg.0
0x2b051  brfalse  loc_2B135
0x2b056  ldarg.0
0x2b057  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncDataBehavior::get_SyncOnlyCompaniesAndSubscribedPlans()
0x2b05c  brfalse  loc_2B135
0x2b061  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b066  stloc.0
0x2b067  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b06c  stloc.1
0x2b06d  ldloc.0
0x2b06e  ldstr    aRevision// "Revision"
0x2b073  ldc.i4.1
0x2b074  ldarg.3
0x2b075  box      [mscorlib]System.Int64
0x2b07a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b07f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b084  ldloc.0
0x2b085  ldstr    aContextid// "ContextId"
0x2b08a  ldarg.2
0x2b08b  box      [mscorlib]System.Guid
0x2b090  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b095  ldloc.0
0x2b096  ldstr    aType// "Type"
0x2b09b  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company
0x2b0a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b0a5  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2b0aa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b0af  ldloc.1
0x2b0b0  ldstr    aRevision// "Revision"
0x2b0b5  ldc.i4.1
0x2b0b6  ldarg.3
0x2b0b7  box      [mscorlib]System.Int64
0x2b0bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b0c1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b0c6  ldloc.1
0x2b0c7  ldstr    aContextid// "ContextId"
0x2b0cc  ldarg.2
0x2b0cd  box      [mscorlib]System.Guid
0x2b0d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b0d7  ldloc.1
0x2b0d8  ldstr    aType// "Type"
0x2b0dd  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan
0x2b0e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b0e7  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2b0ec  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b0f1  ldstr    aDirectoryobjec_0// "DirectoryObjectState"
0x2b0f6  ldnull
0x2b0f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0x2b0fc  stloc.2
0x2b0fd  ldloc.2
0x2b0fe  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0x2b103  ldstr    aRevision// "Revision"
0x2b108  ldc.i4.0
0x2b109  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0x2b10e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0x2b113  ldloc.2
0x2b114  ldc.i4.2
0x2b115  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2b11a  dup
0x2b11b  ldc.i4.0
0x2b11c  ldloc.0
0x2b11d  stelem.ref
0x2b11e  dup
0x2b11f  ldc.i4.1
0x2b120  ldloc.1
0x2b121  stelem.ref
0x2b122  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0x2b127  ldloc.2
0x2b128  ldarg.1
0x2b129  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2b12e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0x2b133  ldloc.2
0x2b134  ret
0x2b135  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b13a  stloc.3
0x2b13b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b140  stloc.3
0x2b141  ldloc.3
0x2b142  ldstr    aRevision// "Revision"
0x2b147  ldc.i4.1
0x2b148  ldarg.3
0x2b149  box      [mscorlib]System.Int64
0x2b14e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b153  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b158  ldloc.3
0x2b159  ldstr    aContextid// "ContextId"
0x2b15e  ldarg.2
0x2b15f  box      [mscorlib]System.Guid
0x2b164  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b169  ldloc.3
0x2b16a  ldstr    aType// "Type"
0x2b16f  ldc.i4.5
0x2b170  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x2b175  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b17a  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2b17f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b184  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b189  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2b18e  stloc.s  4
0x2b190  ldloc.s  4
0x2b192  ldstr    aRevision// "Revision"
0x2b197  ldc.i4.1
0x2b198  ldarg.3
0x2b199  box      [mscorlib]System.Int64
0x2b19e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2b1a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b1a8  ldloc.s  4
0x2b1aa  ldstr    aContextid// "ContextId"
0x2b1af  ldarg.2
0x2b1b0  box      [mscorlib]System.Guid
0x2b1b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b1ba  ldloc.s  4
0x2b1bc  ldstr    aType// "Type"
0x2b1c1  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x2b1c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b1cb  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2b1d0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b1d5  ldloc.s  4
0x2b1d7  ldstr    aIstobeapplied// "IsToBeApplied"
0x2b1dc  ldc.i4.1
0x2b1dd  box      [mscorlib]System.Boolean
0x2b1e2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2b1e7  ldstr    aDirectoryobjec_0// "DirectoryObjectState"
0x2b1ec  ldnull
0x2b1ed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0x2b1f2  stloc.s  5
0x2b1f4  ldloc.s  5
0x2b1f6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0x2b1fb  ldstr    aRevision// "Revision"
0x2b200  ldc.i4.0
0x2b201  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0x2b206  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0x2b20b  ldloc.s  5
0x2b20d  ldc.i4.2
0x2b20e  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2b213  dup
0x2b214  ldc.i4.0
0x2b215  ldloc.3
0x2b216  stelem.ref
0x2b217  dup
0x2b218  ldc.i4.1
0x2b219  ldloc.s  4
0x2b21b  stelem.ref
0x2b21c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0x2b221  ldloc.s  5
0x2b223  ldarg.1
0x2b224  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2b229  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0x2b22e  ldloc.s  5
0x2b230  ret
```
