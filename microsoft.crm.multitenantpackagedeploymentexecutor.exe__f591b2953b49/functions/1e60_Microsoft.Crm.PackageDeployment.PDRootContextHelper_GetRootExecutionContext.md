# Microsoft.Crm.PackageDeployment.PDRootContextHelper::GetRootExecutionContext

- ea: `0x1e60`
- end: `0x1ece`
- name: `Microsoft.Crm.PackageDeployment.PDRootContextHelper::GetRootExecutionContext`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x1e60`
- `0x1ed0`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.0
0x1e61  brtrue.s loc_1E6E
0x1e63  ldstr    aLogger// "logger"
0x1e68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1e6d  throw
0x1e6e  ldarg.1
0x1e6f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1e74  brfalse.s loc_1EA2
0x1e76  ldarg.2
0x1e77  call     class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext Microsoft.Crm.PackageDeployment.PDRootContextHelper::CreateDefaultRootExecutionContext(valuetype [mscorlib]System.Guid organizationId)
0x1e7c  stloc.0
0x1e7d  ldarg.0
0x1e7e  ldstr    aNoRootexecutio// "No RootExecutionContext found, creating"...
0x1e83  ldc.i4.2
0x1e84  newarr   [mscorlib]System.Object
0x1e89  dup
0x1e8a  ldc.i4.0
0x1e8b  ldloc.0
0x1e8c  callvirt instance string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::get_SessionId()
0x1e91  stelem.ref
0x1e92  dup
0x1e93  ldc.i4.1
0x1e94  ldloc.0
0x1e95  callvirt instance string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::get_RootActivityId()
0x1e9a  stelem.ref
0x1e9b  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1ea0  br.s     loc_1ECC
0x1ea2  ldarg.1
0x1ea3  call     class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryUtility::RestoreRoot(string)
0x1ea8  stloc.0
0x1ea9  ldarg.0
0x1eaa  ldstr    aRestoredRootex// "Restored RootExecutionContext with Sess"...
0x1eaf  ldc.i4.2
0x1eb0  newarr   [mscorlib]System.Object
0x1eb5  dup
0x1eb6  ldc.i4.0
0x1eb7  ldloc.0
0x1eb8  callvirt instance string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::get_SessionId()
0x1ebd  stelem.ref
0x1ebe  dup
0x1ebf  ldc.i4.1
0x1ec0  ldloc.0
0x1ec1  callvirt instance string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::get_RootActivityId()
0x1ec6  stelem.ref
0x1ec7  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1ecc  ldloc.0
0x1ecd  ret
```
