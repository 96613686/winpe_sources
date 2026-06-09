# Microsoft.Crm.Sandbox.SandboxWorkerMain::InitializeDefaultValues

- ea: `0x3ea0`
- end: `0x3f81`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::InitializeDefaultValues`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3aa0`

## callees

- `0x39f0`

## string_xrefs

- `0x3ea6`: `workerConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x3ea0  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration()
0x3ea5  dup
0x3ea6  ldstr    aWorkerconfigur_0// "workerConfiguration"
0x3eab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3eb0  dup
0x3eb1  ldc.i4.0
0x3eb2  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0x3eb7  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalIdleTimeInMin
0x3ebc  ldc.i4.1
0x3ebd  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0x3ec2  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalLifetimeInMin
0x3ec7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ecc  ldstr    a01_0// "{0}{1}"
0x3ed1  ldc.i4.2
0x3ed2  newarr   [mscorlib]System.Object
0x3ed7  dup
0x3ed8  ldc.i4.0
0x3ed9  ldc.i4.3
0x3eda  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x3edf  stelem.ref
0x3ee0  dup
0x3ee1  ldc.i4.1
0x3ee2  ldc.i4.s 0xE
0x3ee4  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x3ee9  stelem.ref
0x3eea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3eef  ldc.i4.s 0x3C
0x3ef1  box      [mscorlib]System.Int32
0x3ef6  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3efb  unbox.any [mscorlib]System.Int32
0x3f00  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalAppDomainLifetimeInMin
0x3f05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f0a  ldc.i4.s 0x26
0x3f0c  ldstr    aSandboxworkerm_10// "SandboxWorkerMain.InitializeDefaultValu"...
0x3f11  ldc.i4.1
0x3f12  newarr   [mscorlib]System.Object
0x3f17  dup
0x3f18  ldc.i4.0
0x3f19  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalIdleTimeInMin
0x3f1e  box      [mscorlib]System.Int32
0x3f23  stelem.ref
0x3f24  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f29  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f2e  ldc.i4.s 0x26
0x3f30  ldstr    aSandboxworkerm_11// "SandboxWorkerMain.InitializeDefaultValu"...
0x3f35  ldc.i4.1
0x3f36  newarr   [mscorlib]System.Object
0x3f3b  dup
0x3f3c  ldc.i4.0
0x3f3d  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalLifetimeInMin
0x3f42  box      [mscorlib]System.Int32
0x3f47  stelem.ref
0x3f48  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f4d  ldc.i4.0
0x3f4e  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalIdleTimeInMin
0x3f53  ldc.i4.0
0x3f54  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3f59  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.SandboxWorkerMain::_maxIdleTime
0x3f5e  ldc.i4.0
0x3f5f  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalLifetimeInMin
0x3f64  ldc.i4.0
0x3f65  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3f6a  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.SandboxWorkerMain::_maxLifetime
0x3f6f  ldc.i4.0
0x3f70  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_totalAppDomainLifetimeInMin
0x3f75  ldc.i4.0
0x3f76  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3f7b  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.SandboxWorkerMain::_maxAppDomainLifetime
0x3f80  ret
```
