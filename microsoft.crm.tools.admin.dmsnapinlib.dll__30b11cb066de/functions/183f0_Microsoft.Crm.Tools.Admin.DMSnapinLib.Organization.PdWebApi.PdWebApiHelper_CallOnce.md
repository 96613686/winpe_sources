# Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::CallOnce

- ea: `0x183f0`
- end: `0x1860e`
- name: `Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::CallOnce`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18310`

## callees

- `0x2be0`
- `0x2c20`
- `0x2cb0`
- `0x2ce0`
- `0x7100`
- `0x7110`
- `0x7140`
- `0x183f0`
- `0x18630`
- `0x18650`
- `0x18670`
- `0x186e0`
- `0x18710`
- `0x1a420`

## string_xrefs

- `0x1846a`: `PdWebApiKeepCompletedJobs`

## pseudocode

```c

```

## disassembly

```asm
0x183f0  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x183f5  stloc.0
0x183f6  ldloc.0
0x183f7  ldsfld   string [mscorlib]System.String::Empty
0x183fc  stfld    string <>c__DisplayClass5_0::pdExePath
0x18401  ldloc.0
0x18402  ldflda   string <>c__DisplayClass5_0::pdExePath
0x18407  call     bool Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::TryGetMultiTenantPdExePath([out] string& pdExePath)
0x1840c  brtrue.s loc_18428
0x1840e  ldstr    aPdApiMultitena// "PD API: MultiTenantPDNotFound: Unable t"...
0x18413  ldstr    aMicrosoftCrmMu// "Microsoft.Crm.MultiTenantPackageDeploym"...
0x18418  ldstr    aMultitenantpd// "MultiTenantPD"
0x1841d  call     string [mscorlib]System.String::Format(string, object, object)
0x18422  newobj   instance void [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Exceptions.JobHostException::.ctor(string)
0x18427  throw
0x18428  ldstr    aPdjobpollinter// "PdJobPollIntervalInSeconds"
0x1842d  ldc.i4.s 0xF
0x1842f  box      [mscorlib]System.Int32
0x18434  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x18439  unbox.any [mscorlib]System.Int32
0x1843e  stloc.1
0x1843f  ldloc.0
0x18440  call     int32 Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::GetApiPort()
0x18445  stfld    int32 <>c__DisplayClass5_0::apiPort
0x1844a  ldstr    aPdwebapijobtim// "PdWebApiJobTimeoutInMinutes"
0x1844f  ldsfld   int32 Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::MaxPackageInstallTimeInMinutes
0x18454  box      [mscorlib]System.Int32
0x18459  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1845e  unbox.any [mscorlib]System.Int32
0x18463  stloc.2
0x18464  call     int32 Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::GetApiTimeout()
0x18469  stloc.3
0x1846a  ldstr    aPdwebapikeepco// "PdWebApiKeepCompletedJobs"
0x1846f  ldc.i4.0
0x18470  box      [mscorlib]System.Int32
0x18475  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1847a  unbox.any [mscorlib]System.Int32
0x1847f  ldc.i4.1
0x18480  ceq
0x18482  stloc.s  4
0x18484  ldstr    aPdwebapiwaitjo// "PdWebApiWaitJobThresholdInSeconds"
0x18489  ldc.i4.s 0x14
0x1848b  box      [mscorlib]System.Int32
0x18490  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x18495  unbox.any [mscorlib]System.Int32
0x1849a  stloc.s  5
0x1849c  ldloc.0
0x1849d  ldftn    instance void <>c__DisplayClass5_0::<CallOnce>b__0(class [System]System.Diagnostics.ProcessStartInfo startInfo)
0x184a3  newobj   instance void class [mscorlib]System.Action`1<class [System]System.Diagnostics.ProcessStartInfo>::.ctor(object, native int)
0x184a8  ldstr    aHttpLocalhost0// "http://localhost:{0}/api/job"
0x184ad  ldloc.0
0x184ae  ldfld    int32 <>c__DisplayClass5_0::apiPort
0x184b3  box      [mscorlib]System.Int32
0x184b8  call     string [mscorlib]System.String::Format(string, object)
0x184bd  stloc.s  6
0x184bf  ldloc.s  6
0x184c1  ldloc.3
0x184c2  conv.r8
0x184c3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x184c8  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::.ctor(var<u1>)
0x184cd  newobj   instance void class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::.ctor(class [mscorlib]System.Action`1<class [System]System.Diagnostics.ProcessStartInfo>, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>)
0x184d2  dup
0x184d3  ldstr    aPdwebapihostde// "PdWebApiHostDebug"
0x184d8  ldc.i4.0
0x184d9  box      [mscorlib]System.Int32
0x184de  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x184e3  unbox.any [mscorlib]System.Int32
0x184e8  ldc.i4.1
0x184e9  ceq
0x184eb  callvirt instance void class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::set_DebugMode(bool)
0x184f0  stloc.s  7
0x184f2  ldloc.s  7
0x184f4  ldloca.s 8
0x184f6  callvirt instance int32 class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::EnsureServerIsRunning(bool&)
0x184fb  stloc.s  9
0x184fd  ldarg.0
0x184fe  ldarg.1
0x184ff  ldloc.s  8
0x18501  ldloc.s  9
0x18503  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDConnected(valuetype [mscorlib]System.Guid organizationId, string packageName, bool startedByThis, int32 attemptCount)
0x18508  ldloc.s  7
0x1850a  callvirt instance class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0> class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::get_Client()
0x1850f  ldarg.2
0x18510  ldloc.s  5
0x18512  ldc.i4   0x3E8
0x18517  mul
0x18518  ldloc.s  4
0x1851a  ldc.i4.0
0x1851b  ceq
0x1851d  callvirt instance class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>> class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::AddJob(void, var<u1>, !!T0)
0x18522  stloc.s  0xA
0x18524  ldloc.s  0xA
0x18526  callvirt instance bool class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_IsCompleted()
0x1852b  brtrue.s loc_18573
0x1852d  ldloc.s  0xA
0x1852f  callvirt instance valuetype [mscorlib]System.Guid class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Id()
0x18534  ldloc.s  7
0x18536  ldloc.1
0x18537  ldloc.2
0x18538  ldloc.s  4
0x1853a  call     class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string> Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::WaitJobWithOutput(valuetype [mscorlib]System.Guid jobId, class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string> host, int32 pollIntervalInSeconds, int32 hostRestartTimeoutInMinutes, bool keepCompletedJobs)
0x1853f  stloc.s  0xA
0x18541  leave.s  loc_18573
0x18543  pop
0x18544  ldloc.s  7
0x18546  callvirt instance bool class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::ShutdownServer()
0x1854b  stloc.s  0xC
0x1854d  ldarg.0
0x1854e  ldarg.1
0x1854f  ldloc.s  0xC
0x18551  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDTimedOut(valuetype [mscorlib]System.Guid orgId, string packageName, bool shutdownByThis)
0x18556  ldnull
0x18557  stloc.s  0xD
0x18559  leave    loc_1860B
0x1855e  pop
0x1855f  ldloc.s  7
0x18561  callvirt instance bool class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentInputArgs, string>::ShutdownServer()
0x18566  stloc.s  0xE
0x18568  ldarg.0
0x18569  ldarg.1
0x1856a  ldloc.s  0xE
0x1856c  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDAbort(valuetype [mscorlib]System.Guid orgId, string packageName, bool shutdownByThis)
0x18571  rethrow
0x18573  ldloc.s  0xA
0x18575  brtrue.s loc_18580
0x18577  ldarg.0
0x18578  ldarg.1
0x18579  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::PDRestarted(valuetype [mscorlib]System.Guid orgId, string packageName)
0x1857e  ldnull
0x1857f  ret
0x18580  ldloc.s  0xA
0x18582  callvirt instance var<u1>[] class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Output()
0x18587  brfalse.s loc_185A1
0x18589  ldloc.s  0xA
0x1858b  callvirt instance var<u1>[] class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Output()
0x18590  ldlen
0x18591  brfalse.s loc_185A1
0x18593  ldloc.s  0xA
0x18595  callvirt instance var<u1>[] class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Output()
0x1859a  call     T0x2B00001E
0x1859f  br.s     loc_185A6
0x185a1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x185a6  stloc.s  0xB
0x185a8  ldloc.s  0xA
0x185aa  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Error()
0x185af  brfalse.s loc_185C0
0x185b1  ldloc.s  0xB
0x185b3  ldc.i4.0
0x185b4  ldloc.s  0xA
0x185b6  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Error()
0x185bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Insert(int32, var<u1>)
0x185c0  ldloc.s  0xA
0x185c2  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_ExceptionType()
0x185c7  ldloc.s  0xA
0x185c9  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_ExceptionMessage()
0x185ce  call     bool Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::IsCriticalServerFailure(string exceptionType, string exceptionMessage)
0x185d3  brfalse.s loc_185EC
0x185d5  ldc.i4.0
0x185d6  ldc.i4.1
0x185d7  ldloc.s  0xB
0x185d9  newobj   instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::.ctor(bool isSuccess, bool isCriticalServerFailure, class [mscorlib]System.Collections.Generic.IList`1<string> pdInfoLog)
0x185de  dup
0x185df  ldloc.s  0xA
0x185e1  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Error()
0x185e6  callvirt instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::set_Error(string value)
0x185eb  ret
0x185ec  ldloc.s  0xA
0x185ee  callvirt instance valuetype [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.JobStatus class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Status()
0x185f3  ldc.i4.4
0x185f4  ceq
0x185f6  ldloc.s  0xB
0x185f8  newobj   instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::.ctor(bool isSuccess, class [mscorlib]System.Collections.Generic.IList`1<string> pdInfoLog)
0x185fd  dup
0x185fe  ldloc.s  0xA
0x18600  callvirt instance string class [Microsoft.Xrm.Tools.OwinJobManager.Client]Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<string>::get_Error()
0x18605  callvirt instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::set_Error(string value)
0x1860a  ret
0x1860b  ldloc.s  0xD
0x1860d  ret
```
