# Microsoft.Crm.Sandbox.HostServiceProgram::Main

- ea: `0xaa0`
- end: `0xb31`
- name: `Microsoft.Crm.Sandbox.HostServiceProgram::Main`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`
- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  .entrypoint
0xaa5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xaaa  ldloca.s 0
0xaac  ldloca.s 1
0xaae  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryUtility::GetMdmAccountDetails(string&, string&)
0xab3  ldc.i4.2
0xab4  ceq
0xab6  ldloc.0
0xab7  ldloc.1
0xab8  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryModule::.ctor(bool, string, string)
0xabd  pop
0xabe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xac3  ldc.i4.s 0x21
0xac5  ldstr    aHostprogramMai// "HostProgram.Main: ENTER {0}"
0xaca  ldc.i4.1
0xacb  newarr   [mscorlib]System.Object
0xad0  dup
0xad1  ldc.i4.0
0xad2  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessId()
0xad7  stelem.ref
0xad8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xadd  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xae2  ldnull
0xae3  ldftn    void Microsoft.Crm.Sandbox.HostServiceProgram::UnhandledExceptionHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs e)
0xae9  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0xaee  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0xaf3  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0xaf8  ldc.i4   0x80
0xafd  callvirt instance void [System]System.Diagnostics.Process::set_PriorityClass(valuetype [System]System.Diagnostics.ProcessPriorityClass)
0xb02  ldarg.0
0xb03  ldlen
0xb04  brtrue.s loc_B19
0xb06  ldc.i4.1
0xb07  newarr   [System.ServiceProcess]System.ServiceProcess.ServiceBase
0xb0c  dup
0xb0d  ldc.i4.0
0xb0e  newobj   instance void Microsoft.Crm.Sandbox.HostService::.ctor()
0xb13  stelem.ref
0xb14  call     void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Run(class [System.ServiceProcess]System.ServiceProcess.ServiceBase[])
0xb19  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb1e  ldc.i4.s 0x26
0xb20  ldstr    aHostprogramMai_0// "HostProgram.Main: EXIT"
0xb25  ldc.i4.0
0xb26  newarr   [mscorlib]System.Object
0xb2b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb30  ret
```
