# Microsoft.Crm.Sandbox.SandboxStatisticsHelper::InternalWriteWorkerExecutionRecords

- ea: `0x60b0`
- end: `0x6312`
- name: `Microsoft.Crm.Sandbox.SandboxStatisticsHelper::InternalWriteWorkerExecutionRecords`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6060`

## callees

- `0x57c0`
- `0x60b0`
- `0x6320`

## string_xrefs

- `0x613a`: `SandboxStatisticsHelper.InternalWriteWorkerExecutionRecords: Some plug-in statistics have been discarded: {0}`
- `0x629d`: `SandboxStatisticsHelper.InternalWriteWorkerExecutionRecords: Some plug-in statistics have been discarded: {0}`
- `0x61b5`: `SandboxStatisticsHelper.InternalWriteWorkerExecutionRecords: The number of write attempts for the plug-in statistics has been exceeded, they have been discarded.`

## pseudocode

```c

```

## disassembly

```asm
0x60b0  br       loc_6301
0x60b5  ldnull
0x60b6  stloc.0
0x60b7  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueueLock
0x60bc  ldc.i4.0
0x60bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x60c2  stloc.2
0x60c3  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x60c8  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::get_Count()
0x60cd  ldc.i4.0
0x60ce  ble.s    loc_60DB
0x60d0  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x60d5  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::Peek()
0x60da  stloc.0
0x60db  leave.s  loc_60E7
0x60dd  ldloc.2
0x60de  brfalse.s loc_60E6
0x60e0  ldloc.2
0x60e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60e6  endfinally
0x60e7  ldloc.0
0x60e8  brfalse  loc_6301
0x60ed  ldloc.0
0x60ee  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_WriteAttempts()
0x60f3  ldc.i4.s 9
0x60f5  ble.s    loc_6169
0x60f7  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueueLock
0x60fc  ldc.i4.2
0x60fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x6102  stloc.2
0x6103  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x6108  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::get_Count()
0x610d  ldc.i4.0
0x610e  cgt
0x6110  ldstr    aWxrqueueCount// "_wxrQueue.Count"
0x6115  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x611a  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x611f  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::Dequeue()
0x6124  pop
0x6125  leave.s  loc_6131
0x6127  ldloc.2
0x6128  brfalse.s loc_6130
0x612a  ldloc.2
0x612b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6130  endfinally
0x6131  ldnull
0x6132  ldloc.0
0x6133  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationId()
0x6138  ldc.i4.s 0x28
0x613a  ldstr    aSandboxstatist_7// "SandboxStatisticsHelper.InternalWriteWo"...
0x613f  ldc.i4.1
0x6140  newarr   [mscorlib]System.Object
0x6145  dup
0x6146  ldc.i4.0
0x6147  ldloc.0
0x6148  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_LastErrorMessage()
0x614d  stelem.ref
0x614e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6153  ldloc.0
0x6154  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationName()
0x6159  ldloc.0
0x615a  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_LastErrorMessage()
0x615f  call     void Microsoft.Crm.Sandbox.SandboxStatisticsHelper::IssueLostStatisticsMessage(string organization, string reason)
0x6164  br       loc_6301
0x6169  ldloc.0
0x616a  dup
0x616b  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_WriteAttempts()
0x6170  stloc.3
0x6171  ldloc.3
0x6172  ldc.i4.1
0x6173  add
0x6174  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::set_WriteAttempts(int32)
0x6179  ldc.i4.0
0x617a  stloc.1
0x617b  ldloc.0
0x617c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_PluginExecutionRecords()
0x6181  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::GetEnumerator()
0x6186  stloc.s  4
0x6188  br       loc_626B
0x618d  ldloc.s  4
0x618f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::get_Current()
0x6194  stloc.s  5
0x6196  ldloc.s  5
0x6198  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_WrittenToPluginTypeStatistic()
0x619d  brtrue   loc_626B
0x61a2  ldloc.s  5
0x61a4  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_WriteAttempts()
0x61a9  ldc.i4.2
0x61aa  ble.s    loc_61CE
0x61ac  ldnull
0x61ad  ldloc.0
0x61ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationId()
0x61b3  ldc.i4.s 0x28
0x61b5  ldstr    aSandboxstatist_8// "SandboxStatisticsHelper.InternalWriteWo"...
0x61ba  ldc.i4.0
0x61bb  newarr   [mscorlib]System.Object
0x61c0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x61c5  ldloc.1
0x61c6  ldc.i4.1
0x61c7  add
0x61c8  stloc.1
0x61c9  br       loc_626B
0x61ce  ldloc.s  5
0x61d0  dup
0x61d1  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_WriteAttempts()
0x61d6  stloc.3
0x61d7  ldloc.3
0x61d8  ldc.i4.1
0x61d9  add
0x61da  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::set_WriteAttempts(int32)
0x61df  ldloc.0
0x61e0  ldloc.s  5
0x61e2  newobj   instance void Microsoft.Crm.Sandbox.SandboxStatistics::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord wxr, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord pxr)
0x61e7  stloc.s  6
0x61e9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginTypeStatisticService::.ctor()
0x61ee  stloc.s  7
0x61f0  ldloc.s  7
0x61f2  ldloc.0
0x61f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationId()
0x61f8  ldloc.s  5
0x61fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeId()
0x61ff  ldloc.s  6
0x6201  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginTypeStatisticService::Write(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ISandboxStatisticWriter)
0x6206  leave.s  loc_626B
0x6208  stloc.s  8
0x620a  ldloc.0
0x620b  ldc.i4.7
0x620c  newarr   [mscorlib]System.Object
0x6211  dup
0x6212  ldc.i4.0
0x6213  ldloc.s  5
0x6215  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeName()
0x621a  stelem.ref
0x621b  dup
0x621c  ldc.i4.1
0x621d  ldstr    asc_F6C4// "; "
0x6222  stelem.ref
0x6223  dup
0x6224  ldc.i4.2
0x6225  ldloc.s  5
0x6227  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeId()
0x622c  stloc.s  9
0x622e  ldloca.s 9
0x6230  ldstr    aD// "D"
0x6235  call     instance string [mscorlib]System.Guid::ToString(string)
0x623a  stelem.ref
0x623b  dup
0x623c  ldc.i4.3
0x623d  ldstr    asc_F6C4// "; "
0x6242  stelem.ref
0x6243  dup
0x6244  ldc.i4.4
0x6245  ldloc.s  8
0x6247  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x624c  stelem.ref
0x624d  dup
0x624e  ldc.i4.5
0x624f  ldstr    asc_F6C4// "; "
0x6254  stelem.ref
0x6255  dup
0x6256  ldc.i4.6
0x6257  ldloc.s  8
0x6259  callvirt instance string [mscorlib]System.Exception::get_Message()
0x625e  stelem.ref
0x625f  call     string [mscorlib]System.String::Concat(object[])
0x6264  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::set_LastErrorMessage(string)
0x6269  rethrow
0x626b  ldloc.s  4
0x626d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6272  brtrue   loc_618D
0x6277  leave.s  loc_6285
0x6279  ldloc.s  4
0x627b  brfalse.s loc_6284
0x627d  ldloc.s  4
0x627f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6284  endfinally
0x6285  ldloc.1
0x6286  brtrue.s loc_6294
0x6288  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExponentialBackOff Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_eventBackoff
0x628d  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExponentialBackOff::Reset()
0x6292  br.s     loc_62C7
0x6294  ldnull
0x6295  ldloc.0
0x6296  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationId()
0x629b  ldc.i4.s 0x28
0x629d  ldstr    aSandboxstatist_7// "SandboxStatisticsHelper.InternalWriteWo"...
0x62a2  ldc.i4.1
0x62a3  newarr   [mscorlib]System.Object
0x62a8  dup
0x62a9  ldc.i4.0
0x62aa  ldloc.0
0x62ab  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_LastErrorMessage()
0x62b0  stelem.ref
0x62b1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x62b6  ldloc.0
0x62b7  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationName()
0x62bc  ldloc.0
0x62bd  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_LastErrorMessage()
0x62c2  call     void Microsoft.Crm.Sandbox.SandboxStatisticsHelper::IssueLostStatisticsMessage(string organization, string reason)
0x62c7  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueueLock
0x62cc  ldc.i4.2
0x62cd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x62d2  stloc.2
0x62d3  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x62d8  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::get_Count()
0x62dd  ldc.i4.0
0x62de  cgt
0x62e0  ldstr    aWxrqueueCount// "_wxrQueue.Count"
0x62e5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x62ea  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x62ef  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::Dequeue()
0x62f4  pop
0x62f5  leave.s  loc_6301
0x62f7  ldloc.2
0x62f8  brfalse.s loc_6300
0x62fa  ldloc.2
0x62fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6300  endfinally
0x6301  ldsfld   class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_wxrQueue
0x6306  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::get_Count()
0x630b  ldc.i4.0
0x630c  bgt      loc_60B5
0x6311  ret
```
