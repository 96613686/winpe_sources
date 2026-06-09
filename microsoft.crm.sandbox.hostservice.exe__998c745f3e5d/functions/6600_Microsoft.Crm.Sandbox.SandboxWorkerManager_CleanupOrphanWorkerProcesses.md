# Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOrphanWorkerProcesses

- ea: `0x6600`
- end: `0x6ac2`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOrphanWorkerProcesses`
- size: `1218`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x6600`
- `0xcbc0`

## string_xrefs

- `0x683a`: `select ProcessId, CommandLine from Win32_Process where Name = '{0}.exe'`
- `0x6890`: `ProcessId`
- `0x68ae`: `ProcessId`
- `0x689e`: `CommandLine`
- `0x68c4`: `CommandLine`
- `0x690a`: `SandboxWorkerManager.CleanupOrphanWorkerProcesses: Encounterd Error during WMI Query for the CommandLine. Exception: {0}`
- `0x69f7`: `SandboxWorkerManager.CleanupOrphanWorkerProcesses: Found orphan {0} with Pid {1}. Process StartTime: {2}. CommandLine: {3}. Killing this orphan process.`
- `0x6aa3`: `SandboxWorkerManager.CleanupOrphanWorkerProcesses: Exception thrown inside CleanupOrphanWorkerProcesses. Catching all exception to prevent SandboxHostUnhandledException. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6600  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanupInProgress
0x6605  brfalse.s loc_6608
0x6607  ret
0x6608  nop
0x6609  ldc.i4.1
0x660a  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanupInProgress
0x660f  ldstr    aSandboxworkerm_8// "SandboxWorkerManager.CleanupOrphanWorke"...
0x6614  ldc.i4.3
0x6615  ldc.i4.s 0x21
0x6617  ldc.i4.1
0x6618  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, bool)
0x661d  stloc.0
0x661e  ldc.i4.2
0x661f  newarr   [mscorlib]System.String
0x6624  dup
0x6625  ldc.i4.0
0x6626  ldstr    aDkmon// "DkMon"
0x662b  stelem.ref
0x662c  dup
0x662d  ldc.i4.1
0x662e  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox.WorkerProcess"
0x6633  stelem.ref
0x6634  stloc.1
0x6635  ldc.i4.0
0x6636  stloc.2
0x6637  br       loc_6A81
0x663c  ldloc.1
0x663d  ldloc.2
0x663e  ldelem.ref
0x663f  stloc.3
0x6640  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x6645  ldloc.3
0x6646  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcessesByName(string)
0x664b  stloc.s  4
0x664d  dup
0x664e  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x6653  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x6658  stloc.s  7
0x665a  ldloca.s 7
0x665c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x6661  stloc.s  5
0x6663  ldnull
0x6664  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6669  ldc.i4.3
0x666a  ldc.i4.s 0x21
0x666c  ldc.i4.0
0x666d  ldc.i4.1
0x666e  ldstr    aSandboxworkerm_9// "SandboxWorkerManager.CleanupOrphanWorke"...
0x6673  ldc.i4.2
0x6674  newarr   [mscorlib]System.Object
0x6679  dup
0x667a  ldc.i4.0
0x667b  ldloc.s  5
0x667d  box      [mscorlib]System.Double
0x6682  stelem.ref
0x6683  dup
0x6684  ldc.i4.1
0x6685  ldloc.3
0x6686  stelem.ref
0x6687  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x668c  ldloc.s  5
0x668e  ldc.r8   120.0
0x6697  ble.un.s loc_66BF
0x6699  ldnull
0x669a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x669f  ldc.i4.s 0x21
0x66a1  ldstr    aSandboxworkerm_10// "SandboxWorkerManager.CleanupOrphanWorke"...
0x66a6  ldc.i4.2
0x66a7  newarr   [mscorlib]System.Object
0x66ac  dup
0x66ad  ldc.i4.0
0x66ae  ldloc.s  5
0x66b0  box      [mscorlib]System.Double
0x66b5  stelem.ref
0x66b6  dup
0x66b7  ldc.i4.1
0x66b8  ldloc.3
0x66b9  stelem.ref
0x66ba  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x66bf  ldc.i4.0
0x66c0  stloc.s  6
0x66c2  ldloc.3
0x66c3  ldstr    aDkmon// "DkMon"
0x66c8  ldc.i4.2
0x66c9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x66ce  brfalse.s loc_6742
0x66d0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x66d5  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x66da  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_0
0x66df  dup
0x66e0  brtrue.s loc_66F9
0x66e2  pop
0x66e3  ldsfld   class <>c <>c::<>9
0x66e8  ldftn    instance bool <>c::<CleanupOrphanWorkerProcesses>b__16_0(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x66ee  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x66f3  dup
0x66f4  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_0
0x66f9  call     T0x2B000008
0x66fe  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_terminationWorkers
0x6703  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x6708  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_1
0x670d  dup
0x670e  brtrue.s loc_6727
0x6710  pop
0x6711  ldsfld   class <>c <>c::<>9
0x6716  ldftn    instance bool <>c::<CleanupOrphanWorkerProcesses>b__16_1(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x671c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x6721  dup
0x6722  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_1
0x6727  call     T0x2B000008
0x672c  add
0x672d  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x6732  add
0x6733  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeProcessQueue
0x6738  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::get_Count()
0x673d  sub
0x673e  stloc.s  6
0x6740  br.s     loc_67B2
0x6742  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x6747  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x674c  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_2
0x6751  dup
0x6752  brtrue.s loc_676B
0x6754  pop
0x6755  ldsfld   class <>c <>c::<>9
0x675a  ldftn    instance bool <>c::<CleanupOrphanWorkerProcesses>b__16_2(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x6760  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x6765  dup
0x6766  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_2
0x676b  call     T0x2B000008
0x6770  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_terminationWorkers
0x6775  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x677a  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_3
0x677f  dup
0x6780  brtrue.s loc_6799
0x6782  pop
0x6783  ldsfld   class <>c <>c::<>9
0x6788  ldftn    instance bool <>c::<CleanupOrphanWorkerProcesses>b__16_3(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x678e  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x6793  dup
0x6794  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__16_3
0x6799  call     T0x2B000008
0x679e  add
0x679f  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x67a4  add
0x67a5  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_nativeProcessQueue
0x67aa  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::get_Count()
0x67af  sub
0x67b0  stloc.s  6
0x67b2  ldnull
0x67b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x67b8  ldc.i4.3
0x67b9  ldc.i4.s 0x21
0x67bb  ldc.i4.0
0x67bc  ldc.i4.1
0x67bd  ldstr    aSandboxworkerm_11// "SandboxWorkerManager.CleanupOrphanWorke"...
0x67c2  ldc.i4.3
0x67c3  newarr   [mscorlib]System.Object
0x67c8  dup
0x67c9  ldc.i4.0
0x67ca  ldloc.s  4
0x67cc  ldlen
0x67cd  conv.i4
0x67ce  box      [mscorlib]System.Int32
0x67d3  stelem.ref
0x67d4  dup
0x67d5  ldc.i4.1
0x67d6  ldloc.3
0x67d7  stelem.ref
0x67d8  dup
0x67d9  ldc.i4.2
0x67da  ldloc.s  6
0x67dc  box      [mscorlib]System.Int32
0x67e1  stelem.ref
0x67e2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x67e7  ldc.i4.s 0x19
0x67e9  ldc.i4.0
0x67ea  call     T0x2B000001
0x67ef  ldc.i4.0
0x67f0  ble      loc_6A7D
0x67f5  ldloc.s  4
0x67f7  ldlen
0x67f8  brfalse  loc_6A7D
0x67fd  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x6802  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x6807  stloc.s  8
0x6809  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_terminationWorkers
0x680e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x6813  stloc.s  9
0x6815  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x681a  stloc.s  0xA
0x681c  ldc.i4.s 0x1A
0x681e  ldc.i4.0
0x681f  call     T0x2B000001
0x6824  ldc.i4.0
0x6825  ble      loc_6921
0x682a  ldstr    aSandboxworkerm_12// "SandboxWorkerManager.CleanupOrphanWorke"...
0x682f  ldc.i4.3
0x6830  ldc.i4.s 0x21
0x6832  ldc.i4.1
0x6833  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, bool)
0x6838  stloc.s  0xB
0x683a  ldstr    aSelectProcessi// "select ProcessId, CommandLine from Win3"...
0x683f  ldloc.3
0x6840  call     string [mscorlib]System.String::Format(string, object)
0x6845  newobj   instance void [System.Management]System.Management.ManagementObjectSearcher::.ctor(string)
0x684a  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementObjectSearcher::Get()
0x684f  call     T0x2B000009
0x6854  ldsfld   class [mscorlib]System.Func`2<class [System.Management]System.Management.ManagementObject, class [System.Management]System.Management.ManagementObject> <>c::<>9__16_4
0x6859  dup
0x685a  brtrue.s loc_6873
0x685c  pop
0x685d  ldsfld   class <>c <>c::<>9
0x6862  ldftn    instance class [System.Management]System.Management.ManagementObject <>c::<CleanupOrphanWorkerProcesses>b__16_4(class [System.Management]System.Management.ManagementObject x)
0x6868  newobj   instance void class [mscorlib]System.Func`2<class [System.Management]System.Management.ManagementObject, class [System.Management]System.Management.ManagementObject>::.ctor(object, native int)
0x686d  dup
0x686e  stsfld   class [mscorlib]System.Func`2<class [System.Management]System.Management.ManagementObject, class [System.Management]System.Management.ManagementObject> <>c::<>9__16_4
0x6873  call     T0x2B00000A
0x6878  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Management]System.Management.ManagementObject>::GetEnumerator()
0x687d  stloc.s  0xC
0x687f  br.s     loc_68D8
0x6881  ldloc.s  0xC
0x6883  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Management]System.Management.ManagementObject>::get_Current()
0x6888  stloc.s  0xD
0x688a  ldloc.s  0xD
0x688c  brfalse.s loc_68D8
0x688e  ldloc.s  0xD
0x6890  ldstr    aProcessid// "ProcessId"
0x6895  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x689a  brfalse.s loc_68D8
0x689c  ldloc.s  0xD
0x689e  ldstr    aCommandline// "CommandLine"
0x68a3  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x68a8  brfalse.s loc_68D8
0x68aa  ldloc.s  0xA
0x68ac  ldloc.s  0xD
0x68ae  ldstr    aProcessid// "ProcessId"
0x68b3  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x68b8  unbox.any [mscorlib]System.UInt32
0x68bd  call     int32 [mscorlib]System.Convert::ToInt32(unsigned int32)
0x68c2  ldloc.s  0xD
0x68c4  ldstr    aCommandline// "CommandLine"
0x68c9  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x68ce  castclass [mscorlib]System.String
0x68d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x68d8  ldloc.s  0xC
0x68da  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x68df  brtrue.s loc_6881
0x68e1  leave.s  loc_68EF
0x68e3  ldloc.s  0xC
0x68e5  brfalse.s loc_68EE
0x68e7  ldloc.s  0xC
0x68e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68ee  endfinally
0x68ef  leave.s  loc_68FD
0x68f1  ldloc.s  0xB
0x68f3  brfalse.s loc_68FC
0x68f5  ldloc.s  0xB
0x68f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68fc  endfinally
0x68fd  leave.s  loc_6921
0x68ff  stloc.s  0xE
0x6901  ldloc.s  0xE
0x6903  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6908  ldc.i4.s 0x21
0x690a  ldstr    aSandboxworkerm_13// "SandboxWorkerManager.CleanupOrphanWorke"...
0x690f  ldc.i4.1
0x6910  newarr   [mscorlib]System.Object
0x6915  dup
0x6916  ldc.i4.0
0x6917  ldloc.s  0xE
0x6919  stelem.ref
0x691a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x691f  leave.s  loc_6921
0x6921  ldloc.s  4
0x6923  stloc.s  0xF
0x6925  ldc.i4.0
0x6926  stloc.s  0x10
0x6928  br       loc_6A72
0x692d  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x6932  stloc.s  0x11
0x6934  ldloc.s  0x11
0x6936  ldloc.s  0xF
0x6938  ldloc.s  0x10
0x693a  ldelem.ref
0x693b  stfld    class [System]System.Diagnostics.Process <>c__DisplayClass16_0::process
0x6940  ldloc.s  0x11
0x6942  ldfld    class [System]System.Diagnostics.Process <>c__DisplayClass16_0::process
0x6947  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Diagnostics.Process::get_StartTime()
0x694c  stloc.s  0x12
0x694e  ldloca.s 0x12
0x6950  ldc.r8   15.0
0x6959  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x695e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6963  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6968  brfalse  loc_6A44
0x696d  ldloc.s  8
0x696f  brfalse  loc_6A44
0x6974  ldloc.s  8
0x6976  ldloc.s  0x11
  ... truncated ...
```
