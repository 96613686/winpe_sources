# Microsoft.Crm.Sandbox.SandboxHost::TraceExecution

- ea: `0x4c10`
- end: `0x4e1f`
- name: `Microsoft.Crm.Sandbox.SandboxHost::TraceExecution`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4240`
- `0xbf70`

## string_xrefs

- `0x4d74`: `workerProcessId`
- `0x4db8`: `orgReadyBucketsCount`

## pseudocode

```c

```

## disassembly

```asm
0x4c10  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::get_Instance()
0x4c15  ldarg.1
0x4c16  ldarg.2
0x4c17  ldarg.3
0x4c18  ldarg.s  4
0x4c1a  ldarg.s  5
0x4c1c  ldarg.s  6
0x4c1e  ldarg.s  7
0x4c20  ldarg.s  8
0x4c22  ldarg.s  9
0x4c24  ldarg.s  0xA
0x4c26  ldarg.s  0xB
0x4c28  ldarg.s  0xC
0x4c2a  ldarg.s  0xD
0x4c2c  ldarg.s  0xE
0x4c2e  ldarg.s  0xF
0x4c30  ldarg.s  0x10
0x4c32  ldarg.s  0x11
0x4c34  ldarg.s  0x12
0x4c36  ldarg.s  0x13
0x4c38  ldarg.s  0x14
0x4c3a  ldarg.s  0x15
0x4c3c  ldarg.s  0x16
0x4c3e  ldarg.s  0x17
0x4c40  ldarg.s  0x18
0x4c42  ldarg.s  0x19
0x4c44  ldarg.s  0x1A
0x4c46  ldarg.s  0x1B
0x4c48  ldarg.s  0x1C
0x4c4a  ldarg.s  0x1D
0x4c4c  ldarg.s  0x1E
0x4c4e  ldarg.s  0x1F
0x4c50  ldnull
0x4c51  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxExecutionDiagnostics(valuetype [mscorlib]System.Guid, string, bool, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, string, string, string, float64, int32, string, string, string, valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, int32, int32, int32, int32, int32, int32, int32, int32, int32, int32, string, string)
0x4c56  ldstr    aTrackingid// "trackingId"
0x4c5b  ldarga.s 4
0x4c5d  ldstr    aD// "D"
0x4c62  call     instance string [mscorlib]System.Guid::ToString(string)
0x4c67  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4c6c  ldstr    aRequestid// "requestId"
0x4c71  ldarga.s 5
0x4c73  ldstr    aD// "D"
0x4c78  call     instance string [mscorlib]System.Guid::ToString(string)
0x4c7d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4c82  ldstr    aErrorcode// "errorCode"
0x4c87  ldarg.s  6
0x4c89  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4c8e  ldstr    aExceptiondetai// "exceptionDetails"
0x4c93  ldarg.s  7
0x4c95  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4c9a  ldstr    aOriginalexcept// "originalException"
0x4c9f  ldarg.s  8
0x4ca1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ca6  ldstr    aExceptionsourc// "exceptionSource"
0x4cab  ldarg.s  9
0x4cad  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4cb2  ldstr    aExecutiontime// "executionTime"
0x4cb7  ldarga.s 0xA
0x4cb9  call     instance string [mscorlib]System.Double::ToString()
0x4cbe  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4cc3  ldstr    aDepth// "depth"
0x4cc8  ldarga.s 0xB
0x4cca  call     instance string [mscorlib]System.Int32::ToString()
0x4ccf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4cd4  ldstr    aAssemblyname// "assemblyName"
0x4cd9  ldarg.s  0xC
0x4cdb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ce0  ldstr    aTypename// "typeName"
0x4ce5  ldarg.s  0xD
0x4ce7  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4cec  ldstr    aExecutionid// "executionId"
0x4cf1  ldarga.s 0x11
0x4cf3  ldstr    aD// "D"
0x4cf8  call     instance string [mscorlib]System.Guid::ToString(string)
0x4cfd  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d02  ldstr    aParentexecutio// "parentExecutionId"
0x4d07  ldarga.s 0x12
0x4d09  ldstr    aD// "D"
0x4d0e  call     instance string [mscorlib]System.Guid::ToString(string)
0x4d13  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d18  ldstr    aErrorcategory// "errorCategory"
0x4d1d  ldarg.s  0x13
0x4d1f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d24  ldstr    aUsedrawbridgei// "useDrawBridgeIsolation"
0x4d29  ldarga.s 0x14
0x4d2b  call     instance string [mscorlib]System.Boolean::ToString()
0x4d30  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d35  ldstr    aPerceivedpasse// "perceivedPassed"
0x4d3a  ldarga.s 0x1E
0x4d3c  call     instance string [mscorlib]System.Int32::ToString()
0x4d41  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d46  ldstr    aMessagename// "messageName"
0x4d4b  ldarg.s  0x1F
0x4d4d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d52  ldstr    aCodeunittype// "codeUnitType"
0x4d57  ldarg.s  0xE
0x4d59  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d5e  ldstr    aWorkerid// "workerId"
0x4d63  ldarga.s 0xF
0x4d65  ldstr    aD// "D"
0x4d6a  call     instance string [mscorlib]System.Guid::ToString(string)
0x4d6f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d74  ldstr    aWorkerprocessi// "workerProcessId"
0x4d79  ldarga.s 0x10
0x4d7b  call     instance string [mscorlib]System.Int32::ToString()
0x4d80  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d85  ldstr    aTotalactivewor// "totalActiveWorkerRequestCount"
0x4d8a  ldarga.s 0x15
0x4d8c  call     instance string [mscorlib]System.Int32::ToString()
0x4d91  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4d96  ldstr    aTotalrequestse// "totalRequestsExecutedByWorkerId"
0x4d9b  ldarga.s 0x16
0x4d9d  call     instance string [mscorlib]System.Int32::ToString()
0x4da2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4da7  ldstr    aOrgcleanbucket// "orgCleanBucketsCount"
0x4dac  ldarga.s 0x17
0x4dae  call     instance string [mscorlib]System.Int32::ToString()
0x4db3  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4db8  ldstr    aOrgreadybucket// "orgReadyBucketsCount"
0x4dbd  ldarga.s 0x18
0x4dbf  call     instance string [mscorlib]System.Int32::ToString()
0x4dc4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4dc9  ldstr    aOrginitializin// "orgInitializingBucketsCount"
0x4dce  ldarga.s 0x19
0x4dd0  call     instance string [mscorlib]System.Int32::ToString()
0x4dd5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4dda  ldstr    aOrgwaitinginit// "orgWaitingInitializingBucketCount"
0x4ddf  ldarga.s 0x1A
0x4de1  call     instance string [mscorlib]System.Int32::ToString()
0x4de6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4deb  ldstr    aOrginactivebuc// "orgInactiveBucketCount"
0x4df0  ldarga.s 0x1B
0x4df2  call     instance string [mscorlib]System.Int32::ToString()
0x4df7  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4dfc  ldstr    aHostcleannativ// "hostCleanNativeProcessCount"
0x4e01  ldarga.s 0x1C
0x4e03  call     instance string [mscorlib]System.Int32::ToString()
0x4e08  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4e0d  ldstr    aHostcleandrawb// "hostCleanDrawbridgeProcessCount"
0x4e12  ldarga.s 0x1D
0x4e14  call     instance string [mscorlib]System.Int32::ToString()
0x4e19  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4e1e  ret
```
