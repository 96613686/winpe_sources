# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutor::MainInternal

- ea: `0x650`
- end: `0x7d9`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutor::MainInternal`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x600`

## callees

- `0xe0`
- `0x120`
- `0x540`
- `0x650`
- `0x830`
- `0x850`

## pseudocode

```c

```

## disassembly

```asm
0x650  ldarg.0
0x651  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::.ctor(string[] args)
0x656  stloc.0
0x657  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x65c  ldsfld   class [mscorlib]System.UnhandledExceptionEventHandler <>c::<>9__1_0
0x661  dup
0x662  brtrue.s loc_67B
0x664  pop
0x665  ldsfld   class <>c <>c::<>9
0x66a  ldftn    instance void <>c::<MainInternal>b__1_0(object sender, class [mscorlib]System.UnhandledExceptionEventArgs eventArgs)
0x670  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x675  dup
0x676  stsfld   class [mscorlib]System.UnhandledExceptionEventHandler <>c::<>9__1_0
0x67b  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x680  call     void [Microsoft.Crm.Core]Microsoft.Crm.RegControl::SetIsInScaleGroupProvisioningServiceContext()
0x685  ldc.i4.1
0x686  call     void [Microsoft.Crm.Core]Microsoft.Crm.RegControl::set_DisableIfxLogging(bool)
0x68b  call     void [Microsoft.Xrm.Kernel.Composition]Microsoft.Xrm.Kernel.Composition.CompositionRoot::Compose()
0x690  ldstr    aPdExeArgs// "PD EXE args: "
0x695  call     string [mscorlib]System.Environment::get_CommandLine()
0x69a  call     string [mscorlib]System.String::Concat(string, string)
0x69f  ldc.i4.0
0x6a0  newarr   [mscorlib]System.Object
0x6a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x6aa  ldloc.0
0x6ab  callvirt instance int32 Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_ApiPort()
0x6b0  brtrue.s loc_6BD
0x6b2  ldstr    aArgumentApipor// "Argument apiport must be specified"
0x6b7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6bc  throw
0x6bd  call     void Microsoft.Crm.MultiTenantPackageDeployment.LifecycleEvent::Start()
0x6c2  ldc.i4.0
0x6c3  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x6c8  stloc.1
0x6c9  ldstr    aPdwebapihostid// "PdWebApiHostIdleTimeoutInSeconds"
0x6ce  ldc.i4   0xE10
0x6d3  box      [mscorlib]System.Int32
0x6d8  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x6dd  unbox.any [mscorlib]System.Int32
0x6e2  conv.r8
0x6e3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x6e8  stloc.2
0x6e9  ldloc.2
0x6ea  ldloc.1
0x6eb  newobj   instance void [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::.ctor(valuetype [mscorlib]System.TimeSpan, class [mscorlib]System.Threading.ManualResetEvent)
0x6f0  dup
0x6f1  callvirt instance void [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::OnIdle()
0x6f6  call     void Microsoft.Crm.MultiTenantPackageDeployment.PdJobController::Init(class [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper idleTimer)
0x6fb  ldsfld   class [mscorlib]System.Action`1<string> <>c::<>9__1_1
0x700  dup
0x701  brtrue.s loc_71A
0x703  pop
0x704  ldsfld   class <>c <>c::<>9
0x709  ldftn    instance void <>c::<MainInternal>b__1_1(string text)
0x70f  newobj   instance void class [mscorlib]System.Action`1<string>::.ctor(object, native int)
0x714  dup
0x715  stsfld   class [mscorlib]System.Action`1<string> <>c::<>9__1_1
0x71a  stsfld   class [mscorlib]System.Action`1<string> [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::Logger
0x71f  ldloc.0
0x720  callvirt instance int32 Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_ApiPort()
0x725  ldloc.1
0x726  call     void [Microsoft.Xrm.Tools.OwinJobManager.Server]Microsoft.Xrm.Tools.OwinJobManager.Server.Startup::Start(int32, class [mscorlib]System.Threading.ManualResetEvent)
0x72b  ldstr    aIdledFor0// "idled for {0}"
0x730  ldloc.2
0x731  box      [mscorlib]System.TimeSpan
0x736  call     string [mscorlib]System.String::Format(string, object)
0x73b  ldnull
0x73c  call     void Microsoft.Crm.MultiTenantPackageDeployment.LifecycleEvent::Exit(string reason, [opt] class [mscorlib]System.Exception ex)
0x741  leave    loc_7D4
0x746  isinst   [mscorlib]System.Reflection.TargetInvocationException
0x74b  dup
0x74c  brtrue.s loc_752
0x74e  pop
0x74f  ldc.i4.0
0x750  br.s     loc_77D
0x752  stloc.3
0x753  ldloc.3
0x754  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x759  isinst   [System]System.Net.HttpListenerException
0x75e  brfalse.s loc_779
0x760  ldloc.3
0x761  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x766  castclass [System]System.Net.HttpListenerException
0x76b  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x770  ldc.i4   0xB7
0x775  ceq
0x777  br.s     loc_77A
0x779  ldc.i4.0
0x77a  ldc.i4.0
0x77b  cgt.un
0x77d  endfilter
0x77f  pop
0x780  ldstr    aPdWebApiFailed// "PD WEB API failed to start due to the p"...
0x785  ldloc.0
0x786  callvirt instance int32 Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_ApiPort()
0x78b  box      [mscorlib]System.Int32
0x790  call     string [mscorlib]System.String::Format(string, object)
0x795  ldc.i4.0
0x796  newarr   [mscorlib]System.Object
0x79b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x7a0  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x7a5  ldloc.3
0x7a6  callvirt instance string [mscorlib]System.Object::ToString()
0x7ab  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x7b0  ldstr    aPort0IsNotAvai// "port {0} is not available"
0x7b5  ldloc.0
0x7b6  callvirt instance int32 Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_ApiPort()
0x7bb  box      [mscorlib]System.Int32
0x7c0  call     string [mscorlib]System.String::Format(string, object)
0x7c5  ldloc.3
0x7c6  call     void Microsoft.Crm.MultiTenantPackageDeployment.LifecycleEvent::Exit(string reason, [opt] class [mscorlib]System.Exception ex)
0x7cb  ldsfld   int32 Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorCodes::RetriableError
0x7d0  stloc.s  4
0x7d2  leave.s  loc_7D6
0x7d4  ldc.i4.0
0x7d5  ret
0x7d6  ldloc.s  4
0x7d8  ret
```
