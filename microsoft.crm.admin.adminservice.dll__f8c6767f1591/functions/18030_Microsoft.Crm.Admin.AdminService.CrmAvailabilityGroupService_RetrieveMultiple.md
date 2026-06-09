# Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::RetrieveMultiple

- ea: `0x18030`
- end: `0x18224`
- name: `Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::RetrieveMultiple`
- size: `500`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18230`
- `0x18240`
- `0x18260`
- `0x182a0`
- `0x182c0`
- `0x184e0`

## callees

- `0x17950`
- `0x17c10`
- `0x17c30`
- `0x17c50`
- `0x17c70`
- `0x17c90`
- `0x17cb0`
- `0x18030`

## string_xrefs

- `0x18154`: `D:\a\1\s\src\CrmLive\Admin\AvailabilityGroup\CrmAvailabilityGroupService.cs`
- `0x18173`: `D:\a\1\s\src\CrmLive\Admin\AvailabilityGroup\CrmAvailabilityGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x18030  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18035  ldc.i4.s 0x14
0x18037  ldstr    aRetrieveMultip// "Retrieve multiple AvailabilityGroups"
0x1803c  ldc.i4.0
0x1803d  newarr   [mscorlib]System.Object
0x18042  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18047  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData>::.ctor()
0x1804c  stloc.0
0x1804d  ldnull
0x1804e  stloc.1
0x1804f  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x18054  stloc.2
0x18055  ldnull
0x18056  stloc.3
0x18057  ldarg.1
0x18058  brfalse  loc_1812D
0x1805d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x18062  stloc.1
0x18063  ldarg.1
0x18064  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_ScaleGroupId()
0x18069  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1806e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18073  brfalse.s loc_1808B
0x18075  ldloc.1
0x18076  ldstr    aScalegroupid_0// "ScaleGroupId"
0x1807b  ldarg.1
0x1807c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_ScaleGroupId()
0x18081  box      [mscorlib]System.Guid
0x18086  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1808b  ldarg.1
0x1808c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_DatacenterId()
0x18091  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18096  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1809b  brfalse.s loc_180B3
0x1809d  ldloc.1
0x1809e  ldstr    aDatacenterid_0// "DataCenterId"
0x180a3  ldarg.1
0x180a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_DatacenterId()
0x180a9  box      [mscorlib]System.Guid
0x180ae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x180b3  ldarg.1
0x180b4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_StorageGroupId()
0x180b9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x180be  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x180c3  brfalse.s loc_180DB
0x180c5  ldloc.1
0x180c6  ldstr    aStoragegroupid_0// "StorageGroupId"
0x180cb  ldarg.1
0x180cc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_StorageGroupId()
0x180d1  box      [mscorlib]System.Guid
0x180d6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x180db  ldarg.1
0x180dc  callvirt instance string Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_PrimaryServer()
0x180e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x180e6  brtrue.s loc_180F9
0x180e8  ldloc.1
0x180e9  ldstr    aPrimaryserver_0// "PrimaryServer"
0x180ee  ldarg.1
0x180ef  callvirt instance string Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_PrimaryServer()
0x180f4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x180f9  ldarg.1
0x180fa  callvirt instance string Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_SyncReplica()
0x180ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18104  brtrue.s loc_18117
0x18106  ldloc.1
0x18107  ldstr    aSyncreplica// "SyncReplica"
0x1810c  ldarg.1
0x1810d  callvirt instance string Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_SyncReplica()
0x18112  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x18117  ldloc.1
0x18118  ldstr    aType// "Type"
0x1811d  ldarg.1
0x1811e  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.AvailabilityGroupType Microsoft.Crm.Admin.AdminService.AvailabilityGroupFilter::get_AvailabilityGroupType()
0x18123  box      Microsoft.Crm.Admin.AdminService.AvailabilityGroupType
0x18128  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1812d  ldloc.1
0x1812e  brfalse.s loc_18161
0x18130  ldloc.1
0x18131  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Count()
0x18136  ldc.i4.0
0x18137  ble.s    loc_18161
0x18139  ldloc.2
0x1813a  ldstr    aAvailabilitygr_4// "AvailabilityGroups"
0x1813f  ldnull
0x18140  ldc.i4.1
0x18141  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x18146  dup
0x18147  ldc.i4.0
0x18148  ldloc.1
0x18149  stelem.ref
0x1814a  ldc.i4   0xE9
0x1814f  ldstr    aRetrievemultip// "RetrieveMultiple"
0x18154  ldstr    aDA1SSrcCrmlive_33// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Avail"...
0x18159  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1815e  stloc.3
0x1815f  br.s     loc_1817E
0x18161  ldloc.2
0x18162  ldstr    aAvailabilitygr_4// "AvailabilityGroups"
0x18167  ldnull
0x18168  ldnull
0x18169  ldc.i4   0xED
0x1816e  ldstr    aRetrievemultip// "RetrieveMultiple"
0x18173  ldstr    aDA1SSrcCrmlive_33// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Avail"...
0x18178  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1817d  stloc.3
0x1817e  ldloc.3
0x1817f  brfalse.s loc_181C3
0x18181  ldloc.3
0x18182  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x18187  stloc.s  4
0x18189  br.s     loc_181AA
0x1818b  ldloca.s 4
0x1818d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x18192  stloc.s  6
0x18194  ldloca.s 6
0x18196  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x1819b  newobj   instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x181a0  stloc.s  5
0x181a2  ldloc.0
0x181a3  ldloc.s  5
0x181a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData>::Add(var<u1>)
0x181aa  ldloca.s 4
0x181ac  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x181b1  brtrue.s loc_1818B
0x181b3  leave.s  loc_181C3
0x181b5  ldloca.s 4
0x181b7  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x181bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x181c2  endfinally
0x181c3  ldloc.0
0x181c4  ldsfld   class [mscorlib]System.Comparison`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData> <>c::<>9__7_0
0x181c9  dup
0x181ca  brtrue.s loc_181E3
0x181cc  pop
0x181cd  ldsfld   class <>c <>c::<>9
0x181d2  ldftn    instance int32 <>c::<RetrieveMultiple>b__7_0(class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData ag1, class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData ag2)
0x181d8  newobj   instance void class [mscorlib]System.Comparison`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData>::.ctor(object, native int)
0x181dd  dup
0x181de  stsfld   class [mscorlib]System.Comparison`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData> <>c::<>9__7_0
0x181e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x181e8  ldloc.0
0x181e9  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData>::ToArray()
0x181ee  stloc.s  7
0x181f0  leave.s  loc_18221
0x181f2  ldloc.2
0x181f3  brfalse.s loc_181FB
0x181f5  ldloc.2
0x181f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x181fb  endfinally
0x181fc  stloc.s  8
0x181fe  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18203  ldc.i4.s 0x14
0x18205  ldstr    aExceptionInRet_1// "Exception in retrieve multiple Availabi"...
0x1820a  ldc.i4.1
0x1820b  newarr   [mscorlib]System.Object
0x18210  dup
0x18211  ldc.i4.0
0x18212  ldloc.s  8
0x18214  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18219  stelem.ref
0x1821a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1821f  rethrow
0x18221  ldloc.s  7
0x18223  ret
```
