# Microsoft.Crm.Sandbox.SandboxWorkerProcess::Initialize

- ea: `0xae00`
- end: `0xaf77`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::Initialize`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xa960`
- `0xb140`

## callees

- `0x5760`
- `0x5770`
- `0x9730`
- `0xae00`

## pseudocode

```c

```

## disassembly

```asm
0xae00  ldarg.2
0xae01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xae06  ldc.i4.s 0x21
0xae08  ldstr    aSandboxworkerp_39// "SandboxWorkerProcess.Initialize: FullId"...
0xae0d  ldc.i4.1
0xae0e  newarr   [mscorlib]System.Object
0xae13  dup
0xae14  ldc.i4.0
0xae15  ldarg.0
0xae16  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xae1b  stelem.ref
0xae1c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xae21  ldarg.0
0xae22  ldfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::_processTerminated
0xae27  ldc.i4.0
0xae28  ceq
0xae2a  ldstr    aProcesstermina// "_processTerminated"
0xae2f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xae34  ldarg.0
0xae35  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xae3a  stloc.0
0xae3b  ldloc.0
0xae3c  ldstr    aWorkerclient_0// "workerClient"
0xae41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xae46  ldloc.0
0xae47  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_RawProxy()
0xae4c  ldstr    aWorkerclientPr// "workerClient.Proxy"
0xae51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xae56  ldloc.0
0xae57  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_lastUsedCounter
0xae5c  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xae61  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_LastUsedCounter(int32 value)
0xae66  ldarg.0
0xae67  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerExecutionRecord
0xae6c  ldarg.2
0xae6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xae72  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xae77  ldarg.0
0xae78  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerExecutionRecord
0xae7d  ldarg.2
0xae7e  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationName()
0xae83  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::set_OrganizationName(string)
0xae88  ldarg.0
0xae89  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerExecutionRecord
0xae8e  ldarg.1
0xae8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ScaleGroupId()
0xae94  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0xae99  ldstr    aIsandboxworker// "ISandboxWorkerProcess.Execute"
0xae9e  ldarg.2
0xae9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0xaea4  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0xaea9  stloc.1
0xaeaa  ldnull
0xaeab  stloc.2
0xaeac  ldarg.0
0xaead  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryLock
0xaeb2  ldstr    aDictionarylock// "_dictionaryLock"
0xaeb7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xaebc  ldarg.0
0xaebd  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryLock
0xaec2  ldc.i4.0
0xaec3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0xaec8  stloc.3
0xaec9  ldarg.0
0xaeca  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0xaecf  ldarg.s  4
0xaed1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::ContainsKey(var<u1>)
0xaed6  brfalse.s loc_AEE6
0xaed8  ldarg.0
0xaed9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0xaede  ldarg.s  4
0xaee0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::get_Item(void)
0xaee5  stloc.2
0xaee6  leave.s  loc_AEF2
0xaee8  ldloc.3
0xaee9  brfalse.s loc_AEF1
0xaeeb  ldloc.3
0xaeec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaef1  endfinally
0xaef2  ldloc.2
0xaef3  brtrue.s loc_AF51
0xaef5  ldarg.0
0xaef6  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryLock
0xaefb  ldc.i4.2
0xaefc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0xaf01  stloc.3
0xaf02  ldarg.0
0xaf03  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0xaf08  ldarg.s  4
0xaf0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::ContainsKey(var<u1>)
0xaf0f  brfalse.s loc_AF21
0xaf11  ldarg.0
0xaf12  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0xaf17  ldarg.s  4
0xaf19  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::get_Item(void)
0xaf1e  stloc.2
0xaf1f  br.s     loc_AF45
0xaf21  ldarg.s  4
0xaf23  ldarg.3
0xaf24  ldarg.s  5
0xaf26  ldarg.0
0xaf27  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xaf2c  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xaf31  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::.ctor(valuetype [mscorlib]System.Guid, string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0xaf36  stloc.2
0xaf37  ldarg.0
0xaf38  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0xaf3d  ldarg.s  4
0xaf3f  ldloc.2
0xaf40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::set_Item(var<u1>, !!T0)
0xaf45  leave.s  loc_AF51
0xaf47  ldloc.3
0xaf48  brfalse.s loc_AF50
0xaf4a  ldloc.3
0xaf4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf50  endfinally
0xaf51  ldloc.1
0xaf52  ldloc.2
0xaf53  ldloc.0
0xaf54  newobj   instance void class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::.ctor(var<u1>, !!T0, var<u1>)
0xaf59  stloc.s  4
0xaf5b  leave.s  loc_AF74
0xaf5d  pop
0xaf5e  ldarg.0
0xaf5f  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xaf64  brfalse.s loc_AF72
0xaf66  ldarg.0
0xaf67  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xaf6c  ldc.i4.4
0xaf6d  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0xaf72  rethrow
0xaf74  ldloc.s  4
0xaf76  ret
```
