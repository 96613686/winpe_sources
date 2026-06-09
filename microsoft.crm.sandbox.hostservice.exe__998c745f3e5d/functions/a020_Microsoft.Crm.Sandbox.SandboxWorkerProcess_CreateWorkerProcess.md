# Microsoft.Crm.Sandbox.SandboxWorkerProcess::CreateWorkerProcess

- ea: `0xa020`
- end: `0xa0eb`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::CreateWorkerProcess`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x7e30`

## callees

- `0x9720`
- `0x98f0`
- `0xa020`
- `0xa800`

## string_xrefs

- `0xa0ac`: ` Uri: `
- `0xa0d1`: `SandboxWorkerProcess.CreateWorkerProcess: New worker process started: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa020  ldarg.0
0xa021  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0xa026  ldstr    aWorkerid_0// "_workerId"
0xa02b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xa030  ldarg.0
0xa031  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0xa036  ldstr    aWorkerport// "_workerPort"
0xa03b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0xa040  ldarg.0
0xa041  ldarg.0
0xa042  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::CreateProcess()
0xa047  stfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xa04c  ldarg.0
0xa04d  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xa052  brfalse  loc_A0EA
0xa057  ldarg.0
0xa058  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa05d  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::_startTime
0xa062  ldarg.0
0xa063  ldc.i4.6
0xa064  newarr   [mscorlib]System.Object
0xa069  dup
0xa06a  ldc.i4.0
0xa06b  ldstr    aWorkerid_1// "WorkerId: "
0xa070  stelem.ref
0xa071  dup
0xa072  ldc.i4.1
0xa073  ldarg.0
0xa074  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0xa079  stloc.0
0xa07a  ldloca.s 0
0xa07c  ldstr    aB// "B"
0xa081  call     instance string [mscorlib]System.Guid::ToString(string)
0xa086  stelem.ref
0xa087  dup
0xa088  ldc.i4.2
0xa089  ldstr    aPid// " PID: "
0xa08e  stelem.ref
0xa08f  dup
0xa090  ldc.i4.3
0xa091  ldarg.0
0xa092  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xa097  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0xa09c  stloc.1
0xa09d  ldloca.s 1
0xa09f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa0a4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa0a9  stelem.ref
0xa0aa  dup
0xa0ab  ldc.i4.4
0xa0ac  ldstr    aUri// " Uri: "
0xa0b1  stelem.ref
0xa0b2  dup
0xa0b3  ldc.i4.5
0xa0b4  ldarg.0
0xa0b5  call     instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0xa0ba  stelem.ref
0xa0bb  call     string [mscorlib]System.String::Concat(object[])
0xa0c0  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xa0c5  ldnull
0xa0c6  ldarg.0
0xa0c7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::_organizationId
0xa0cc  ldc.i4.3
0xa0cd  ldc.i4.s 0x26
0xa0cf  ldc.i4.0
0xa0d0  ldc.i4.1
0xa0d1  ldstr    aSandboxworkerp_18// "SandboxWorkerProcess.CreateWorkerProces"...
0xa0d6  ldc.i4.1
0xa0d7  newarr   [mscorlib]System.Object
0xa0dc  dup
0xa0dd  ldc.i4.0
0xa0de  ldarg.0
0xa0df  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xa0e4  stelem.ref
0xa0e5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0xa0ea  ret
```
