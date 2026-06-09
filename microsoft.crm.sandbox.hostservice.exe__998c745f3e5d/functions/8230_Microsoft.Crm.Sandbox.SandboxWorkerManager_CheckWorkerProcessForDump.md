# Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckWorkerProcessForDump

- ea: `0x8230`
- end: `0x8532`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckWorkerProcessForDump`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xcd60`

## callees

- `0x48e0`
- `0x62f0`
- `0x8230`
- `0x8540`
- `0x8550`
- `0x9770`
- `0x9790`
- `0x9800`
- `0x9890`
- `0x98a0`
- `0x98b0`
- `0x98c0`
- `0x98d0`
- `0x98e0`
- `0xb7e0`
- `0xb800`

## string_xrefs

- `0x8436`: `SandboxWorkerProcess dump failed. ProcessID: `
- `0x84ca`: `SandboxWorkerProcess dump failed. ProcessID: `

## pseudocode

```c

```

## disassembly

```asm
0x8230  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x8235  ldc.i4.s 0x17
0x8237  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x823c  stloc.0
0x823d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x8242  ldc.i4.s 0x18
0x8244  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x8249  stloc.1
0x824a  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x824f  ldc.i4.s 0x19
0x8251  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x8256  stloc.2
0x8257  ldc.i4.s 0xA
0x8259  stloc.3
0x825a  ldarg.0
0x825b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_LastDumpSampleTime()
0x8260  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x8265  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x826a  brtrue.s loc_828C
0x826c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8271  ldarg.0
0x8272  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_LastDumpSampleTime()
0x8277  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x827c  stloc.s  4
0x827e  ldloca.s 4
0x8280  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x8285  ldloc.1
0x8286  conv.r8
0x8287  ble.un   loc_8531
0x828c  ldarg.0
0x828d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8292  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_LastDumpSampleTime(valuetype [mscorlib]System.DateTime value)
0x8297  ldarg.0
0x8298  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x829d  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x82a2  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x82a7  stloc.s  5
0x82a9  ldloc.s  5
0x82ab  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetProcessById(int32)
0x82b0  stloc.s  6
0x82b2  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x82b7  ldloc.s  5
0x82b9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::ContainsKey(var<u1>)
0x82be  brtrue.s loc_82E1
0x82c0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x82c5  ldloc.s  5
0x82c7  ldc.i4.2
0x82c8  newarr   [mscorlib]System.Int32
0x82cd  dup
0x82ce  ldc.i4.0
0x82cf  ldc.i4.1
0x82d0  stelem.i4
0x82d1  dup
0x82d2  ldc.i4.1
0x82d3  ldarg.0
0x82d4  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Cpu()
0x82d9  stelem.i4
0x82da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::Add(var<u1>, !!T0)
0x82df  br.s     loc_8314
0x82e1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x82e6  ldloc.s  5
0x82e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::get_Item(void)
0x82ed  ldc.i4.0
0x82ee  ldelema  [mscorlib]System.Int32
0x82f3  dup
0x82f4  ldind.i4
0x82f5  ldc.i4.1
0x82f6  add
0x82f7  stind.i4
0x82f8  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x82fd  ldloc.s  5
0x82ff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::get_Item(void)
0x8304  ldc.i4.1
0x8305  ldelema  [mscorlib]System.Int32
0x830a  dup
0x830b  ldind.i4
0x830c  ldarg.0
0x830d  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Cpu()
0x8312  add
0x8313  stind.i4
0x8314  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x8319  ldloc.s  5
0x831b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::get_Item(void)
0x8320  ldc.i4.0
0x8321  ldelem.i4
0x8322  ldloc.3
0x8323  bne.un   loc_84B0
0x8328  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x832d  ldloc.s  5
0x832f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::get_Item(void)
0x8334  ldc.i4.1
0x8335  ldelem.i4
0x8336  ldloc.3
0x8337  ldloc.0
0x8338  call     bool Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckIfWorkerProcessExceedsThreshold(int32 workerProcessCpuTotal, int32 averageBase, int32 autoDumpCpuUsageThreshold)
0x833d  brfalse  loc_84A3
0x8342  ldarg.0
0x8343  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_LastDumpTime()
0x8348  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x834d  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x8352  brtrue.s loc_8374
0x8354  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8359  ldarg.0
0x835a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_LastDumpTime()
0x835f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x8364  stloc.s  4
0x8366  ldloca.s 4
0x8368  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x836d  ldloc.2
0x836e  conv.r8
0x836f  ble.un   loc_84A3
0x8374  ldarg.0
0x8375  callvirt instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_IsProcessDumpInProgress()
0x837a  brtrue   loc_84A3
0x837f  ldstr    aLocalappdata// "LOCALAPPDATA"
0x8384  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x8389  ldstr    aMaProcessdumps// "MA_ProcessDumps"
0x838e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x8393  stloc.s  7
0x8395  ldc.i4.5
0x8396  newarr   [mscorlib]System.Object
0x839b  dup
0x839c  ldc.i4.0
0x839d  ldstr    aSandboxworkerp_1// "SandboxWorkerProcess_"
0x83a2  stelem.ref
0x83a3  dup
0x83a4  ldc.i4.1
0x83a5  ldloc.s  5
0x83a7  box      [mscorlib]System.Int32
0x83ac  stelem.ref
0x83ad  dup
0x83ae  ldc.i4.2
0x83af  ldstr    asc_1BE12// "_"
0x83b4  stelem.ref
0x83b5  dup
0x83b6  ldc.i4.3
0x83b7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x83bc  stloc.s  0xA
0x83be  ldloca.s 0xA
0x83c0  ldstr    aDdmmyyyyhhmmss// "ddMMyyyyHHmmss"
0x83c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83ca  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x83cf  stelem.ref
0x83d0  dup
0x83d1  ldc.i4.4
0x83d2  ldstr    aDmp// ".dmp"
0x83d7  stelem.ref
0x83d8  call     string [mscorlib]System.String::Concat(object[])
0x83dd  stloc.s  8
0x83df  ldloc.s  7
0x83e1  ldloc.s  8
0x83e3  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x83e8  stloc.s  9
0x83ea  ldarg.0
0x83eb  ldloc.s  5
0x83ed  ldloc.s  7
0x83ef  ldloc.s  9
0x83f1  ldc.i4.2
0x83f2  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::WriteDumpForProcess(class Microsoft.Crm.Sandbox.SandboxWorkerProcess process, int32 processId, string folderName, string filePath, valuetype Microsoft.Crm.Sandbox.DumpTypes dumpType)
0x83f7  ldarg.0
0x83f8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x83fd  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_LastDumpTime(valuetype [mscorlib]System.DateTime value)
0x8402  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.Sandbox.SandboxDumpMetrics::get_SandboxWorkerProcessDumpSuccess()
0x8407  ldc.i4.1
0x8408  conv.i8
0x8409  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::ReportValue(int64)
0x840e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8413  ldc.i4.s 0x28
0x8415  ldstr    aSandboxworkerm_81// "SandboxWorkerManager.CheckWorkerProcess"...
0x841a  ldc.i4.1
0x841b  newarr   [mscorlib]System.Object
0x8420  dup
0x8421  ldc.i4.0
0x8422  ldloc.s  9
0x8424  stelem.ref
0x8425  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x842a  leave.s  loc_849C
0x842c  stloc.s  0xB
0x842e  ldc.i4.6
0x842f  newarr   [mscorlib]System.String
0x8434  dup
0x8435  ldc.i4.0
0x8436  ldstr    aSandboxworkerp_2// "SandboxWorkerProcess dump failed. Proce"...
0x843b  stelem.ref
0x843c  dup
0x843d  ldc.i4.1
0x843e  ldarg.0
0x843f  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8444  stelem.ref
0x8445  dup
0x8446  ldc.i4.2
0x8447  ldstr    aException// "; Exception: "
0x844c  stelem.ref
0x844d  dup
0x844e  ldc.i4.3
0x844f  ldloc.s  0xB
0x8451  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8456  stelem.ref
0x8457  dup
0x8458  ldc.i4.4
0x8459  ldstr    aStackTrace// "; Stack Trace: "
0x845e  stelem.ref
0x845f  dup
0x8460  ldc.i4.5
0x8461  ldloc.s  0xB
0x8463  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x8468  stelem.ref
0x8469  call     string [mscorlib]System.String::Concat(string[])
0x846e  stloc.s  0xC
0x8470  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.Sandbox.SandboxDumpMetrics::get_SandboxWorkerProcessDumpFailed()
0x8475  ldc.i4.1
0x8476  conv.i8
0x8477  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::ReportValue(int64)
0x847c  ldloc.s  0xB
0x847e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8483  ldc.i4.s 0x28
0x8485  ldstr    aSandboxworkerm_82// "SandboxWorkerManager.CheckWorkerProcess"...
0x848a  ldc.i4.1
0x848b  newarr   [mscorlib]System.Object
0x8490  dup
0x8491  ldc.i4.0
0x8492  ldloc.s  0xC
0x8494  stelem.ref
0x8495  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x849a  leave.s  loc_849C
0x849c  ldarg.0
0x849d  ldc.i4.0
0x849e  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_IsProcessDumpInProgress(bool value)
0x84a3  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x84a8  ldloc.s  5
0x84aa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::Remove(var<u1>)
0x84af  pop
0x84b0  leave.s  loc_84BE
0x84b2  ldloc.s  6
0x84b4  brfalse.s loc_84BD
0x84b6  ldloc.s  6
0x84b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84bd  endfinally
0x84be  leave.s  loc_8531
0x84c0  stloc.s  0xD
0x84c2  ldc.i4.6
0x84c3  newarr   [mscorlib]System.Object
0x84c8  dup
0x84c9  ldc.i4.0
0x84ca  ldstr    aSandboxworkerp_2// "SandboxWorkerProcess dump failed. Proce"...
0x84cf  stelem.ref
0x84d0  dup
0x84d1  ldc.i4.1
0x84d2  ldloc.s  5
0x84d4  box      [mscorlib]System.Int32
0x84d9  stelem.ref
0x84da  dup
0x84db  ldc.i4.2
0x84dc  ldstr    aException// "; Exception: "
0x84e1  stelem.ref
0x84e2  dup
0x84e3  ldc.i4.3
0x84e4  ldloc.s  0xD
0x84e6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x84eb  stelem.ref
0x84ec  dup
0x84ed  ldc.i4.4
0x84ee  ldstr    aStackTrace// "; Stack Trace: "
0x84f3  stelem.ref
0x84f4  dup
0x84f5  ldc.i4.5
0x84f6  ldloc.s  0xD
0x84f8  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x84fd  stelem.ref
0x84fe  call     string [mscorlib]System.String::Concat(object[])
0x8503  stloc.s  0xE
0x8505  ldloc.s  0xD
0x8507  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x850c  ldc.i4.s 0x28
0x850e  ldstr    aSandboxworkerm_82// "SandboxWorkerManager.CheckWorkerProcess"...
0x8513  ldc.i4.1
0x8514  newarr   [mscorlib]System.Object
0x8519  dup
0x851a  ldc.i4.0
0x851b  ldloc.s  0xE
0x851d  stelem.ref
0x851e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8523  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.Sandbox.SandboxDumpMetrics::get_SandboxWorkerProcessDumpFailed()
0x8528  ldc.i4.1
0x8529  conv.i8
0x852a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::ReportValue(int64)
0x852f  leave.s  loc_8531
0x8531  ret
```
