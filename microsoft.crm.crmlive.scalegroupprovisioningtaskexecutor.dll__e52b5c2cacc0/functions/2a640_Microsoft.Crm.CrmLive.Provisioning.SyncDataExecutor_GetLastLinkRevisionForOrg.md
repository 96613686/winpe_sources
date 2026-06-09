# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetLastLinkRevisionForOrg

- ea: `0x2a640`
- end: `0x2a73a`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::GetLastLinkRevisionForOrg`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29cb0`

## callees

- `0x2a640`

## string_xrefs

- `0x2a6e6`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2a646`: `DirectoryLink`
- `0x2a6e1`: `GetLastLinkRevisionForOrg`

## pseudocode

```c

```

## disassembly

```asm
0x2a640  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2a645  stloc.0
0x2a646  ldstr    aDirectorylink// "DirectoryLink"
0x2a64b  ldc.i4.1
0x2a64c  newarr   [mscorlib]System.String
0x2a651  dup
0x2a652  ldc.i4.0
0x2a653  ldstr    aRevision// "Revision"
0x2a658  stelem.ref
0x2a659  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0x2a65e  stloc.1
0x2a65f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2a664  stloc.2
0x2a665  ldloc.2
0x2a666  ldstr    aContextid// "ContextId"
0x2a66b  ldarg.0
0x2a66c  box      [mscorlib]System.Guid
0x2a671  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a676  ldloc.2
0x2a677  ldstr    aModifiedon// "ModifiedOn"
0x2a67c  ldc.i4.5
0x2a67d  ldnull
0x2a67e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x2a683  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a688  ldloc.2
0x2a689  ldstr    aSourceclass// "SourceClass"
0x2a68e  ldstr    aGroup// "Group"
0x2a693  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a698  ldloc.2
0x2a699  ldstr    aTargetclass// "TargetClass"
0x2a69e  ldstr    aUser_0// "User"
0x2a6a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2a6a8  ldloc.1
0x2a6a9  ldc.i4.1
0x2a6aa  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2a6af  dup
0x2a6b0  ldc.i4.0
0x2a6b1  ldloc.2
0x2a6b2  stelem.ref
0x2a6b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0x2a6b8  ldloc.1
0x2a6b9  ldc.i4.1
0x2a6ba  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2a6bf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0x2a6c4  ldloc.1
0x2a6c5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0x2a6ca  ldstr    aRevision// "Revision"
0x2a6cf  ldc.i4.1
0x2a6d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0x2a6d5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0x2a6da  ldloc.0
0x2a6db  ldloc.1
0x2a6dc  ldc.i4   0x218
0x2a6e1  ldstr    aGetlastlinkrev// "GetLastLinkRevisionForOrg"
0x2a6e6  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2a6eb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0x2a6f0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0x2a6f5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x2a6fa  stloc.3
0x2a6fb  br.s     loc_2A716
0x2a6fd  ldloc.3
0x2a6fe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x2a703  ldstr    aRevision// "Revision"
0x2a708  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a70d  unbox.any [mscorlib]System.UInt64
0x2a712  stloc.s  4
0x2a714  leave.s  loc_2A737
0x2a716  ldloc.3
0x2a717  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a71c  brtrue.s loc_2A6FD
0x2a71e  leave.s  loc_2A734
0x2a720  ldloc.3
0x2a721  brfalse.s loc_2A729
0x2a723  ldloc.3
0x2a724  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a729  endfinally
0x2a72a  ldloc.0
0x2a72b  brfalse.s loc_2A733
0x2a72d  ldloc.0
0x2a72e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a733  endfinally
0x2a734  ldc.i4.0
0x2a735  conv.i8
0x2a736  ret
0x2a737  ldloc.s  4
0x2a739  ret
```
