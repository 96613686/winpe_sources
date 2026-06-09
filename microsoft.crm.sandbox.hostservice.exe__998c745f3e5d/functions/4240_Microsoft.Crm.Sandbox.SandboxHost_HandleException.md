# Microsoft.Crm.Sandbox.SandboxHost::HandleException

- ea: `0x4240`
- end: `0x4666`
- name: `Microsoft.Crm.Sandbox.SandboxHost::HandleException`
- size: `1062`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x4830`
- `0xba70`
- `0xbf70`

## callees

- `0x4240`
- `0x4c10`
- `0x6320`
- `0x6330`
- `0x9720`
- `0x9790`
- `0x9840`
- `0x9860`

## pseudocode

```c

```

## disassembly

```asm
0x4240  ldarg.2
0x4241  brfalse.s loc_424A
0x4243  ldarg.2
0x4244  ldarg.1
0x4245  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadExit(class [mscorlib]System.Exception)
0x424a  ldarg.3
0x424b  brtrue.s loc_4254
0x424d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4252  br.s     loc_425A
0x4254  ldarg.3
0x4255  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x425a  stloc.0
0x425b  ldarg.3
0x425c  brtrue.s loc_4265
0x425e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4263  br.s     loc_426B
0x4265  ldarg.3
0x4266  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x426b  stloc.1
0x426c  ldarg.3
0x426d  brfalse.s loc_4280
0x426f  ldarg.3
0x4270  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0x4275  stloc.s  0xF
0x4277  ldloca.s 0xF
0x4279  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x427e  brtrue.s loc_4287
0x4280  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4285  br.s     loc_4296
0x4287  ldarg.3
0x4288  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0x428d  stloc.s  0xF
0x428f  ldloca.s 0xF
0x4291  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x4296  stloc.2
0x4297  ldarg.3
0x4298  brtrue.s loc_429D
0x429a  ldc.i4.0
0x429b  br.s     loc_42A3
0x429d  ldarg.3
0x429e  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0x42a3  stloc.3
0x42a4  ldarg.s  8
0x42a6  brtrue.s loc_42AF
0x42a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42ad  br.s     loc_42B6
0x42af  ldarg.s  8
0x42b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x42b6  stloc.s  4
0x42b8  ldarg.s  8
0x42ba  brfalse.s loc_42C5
0x42bc  ldarg.s  8
0x42be  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x42c3  brtrue.s loc_42C8
0x42c5  ldc.i4.m1
0x42c6  br.s     loc_42D4
0x42c8  ldarg.s  8
0x42ca  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x42cf  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x42d4  stloc.s  5
0x42d6  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxHost::_exceptionConverter
0x42db  ldarg.1
0x42dc  ldc.i4.1
0x42dd  ldloca.s 7
0x42df  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException(class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter, class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x42e4  stloc.s  6
0x42e6  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxHost::_exceptionConverter
0x42eb  ldarg.1
0x42ec  ldloca.s 8
0x42ee  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToCrmException(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException&)
0x42f3  stloc.s  9
0x42f5  leave.s  loc_4337
0x42f7  stloc.s  0x10
0x42f9  ldloc.s  0x10
0x42fb  ldloc.0
0x42fc  ldc.i4.s 0x21
0x42fe  ldstr    aSandboxhostHan// "SandboxHost.HandleException: UNEXPECTED"...
0x4303  ldc.i4.2
0x4304  newarr   [mscorlib]System.Object
0x4309  dup
0x430a  ldc.i4.0
0x430b  ldarg.1
0x430c  callvirt instance string [mscorlib]System.Object::ToString()
0x4311  stelem.ref
0x4312  dup
0x4313  ldc.i4.1
0x4314  ldloc.s  0x10
0x4316  callvirt instance string [mscorlib]System.Object::ToString()
0x431b  stelem.ref
0x431c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4321  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::.ctor()
0x4326  dup
0x4327  ldstr    aUnexpectedTryc// "UNEXPECTED TryConvertToCrmException. Un"...
0x432c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0x4331  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>)
0x4336  throw
0x4337  ldc.i4.0
0x4338  stloc.s  0xA
0x433a  ldloc.s  6
0x433c  brfalse.s loc_434E
0x433e  ldloc.s  7
0x4340  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x4345  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x434a  stloc.s  0xA
0x434c  br.s     loc_435B
0x434e  ldloc.s  9
0x4350  brfalse.s loc_435B
0x4352  ldloc.s  8
0x4354  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x4359  stloc.s  0xA
0x435b  ldsfld   string [mscorlib]System.String::Empty
0x4360  stloc.s  0xC
0x4362  ldsfld   string [mscorlib]System.String::Empty
0x4367  stloc.s  0xD
0x4369  ldarg.1
0x436a  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmAssemblyMissingInCacheException
0x436f  brfalse.s loc_438B
0x4371  ldloc.s  7
0x4373  ldarg.1
0x4374  ldc.i4.7
0x4375  stloc.s  0x11
0x4377  ldloca.s 0x11
0x4379  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x437f  callvirt instance string [mscorlib]System.Object::ToString()
0x4384  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, class [mscorlib]System.Exception, string)
0x4389  br.s     loc_43C5
0x438b  ldarg.1
0x438c  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmSandboxStartStopException
0x4391  brfalse.s loc_43AD
0x4393  ldloc.s  7
0x4395  ldarg.1
0x4396  ldc.i4.8
0x4397  stloc.s  0x11
0x4399  ldloca.s 0x11
0x439b  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x43a1  callvirt instance string [mscorlib]System.Object::ToString()
0x43a6  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, class [mscorlib]System.Exception, string)
0x43ab  br.s     loc_43C5
0x43ad  ldloc.s  7
0x43af  ldarg.1
0x43b0  ldc.i4.6
0x43b1  stloc.s  0x11
0x43b3  ldloca.s 0x11
0x43b5  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x43bb  callvirt instance string [mscorlib]System.Object::ToString()
0x43c0  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, class [mscorlib]System.Exception, string)
0x43c5  ldloc.s  7
0x43c7  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x43cc  ldarg.s  0xE
0x43ce  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_ExceptionRetriable(bool)
0x43d3  ldloc.s  7
0x43d5  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x43da  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x43df  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x43e4  brtrue.s loc_4415
0x43e6  ldloc.s  7
0x43e8  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x43ed  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x43f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x43f7  brtrue.s loc_4415
0x43f9  ldloc.s  7
0x43fb  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x4400  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x4405  stloc.s  0xD
0x4407  ldloc.s  7
0x4409  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x440e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x4413  stloc.s  0xC
0x4415  ldloc.s  0xA
0x4417  call     int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::ClassifyErrorCode(int32)
0x441c  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ConvertOperationResult(int32)
0x4421  stloc.s  0xE
0x4423  ldloc.s  6
0x4425  brfalse  loc_44DB
0x442a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x442f  ldstr    aOriginalExcept// "Original Exception: {0}, Converted Faul"...
0x4434  ldc.i4.2
0x4435  newarr   [mscorlib]System.Object
0x443a  dup
0x443b  ldc.i4.0
0x443c  ldarg.1
0x443d  callvirt instance string [mscorlib]System.Object::ToString()
0x4442  stelem.ref
0x4443  dup
0x4444  ldc.i4.1
0x4445  ldloc.s  7
0x4447  stelem.ref
0x4448  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x444d  stloc.s  0xB
0x444f  ldarg.0
0x4450  ldloc.0
0x4451  ldstr    aSandboxhost// "SandboxHost"
0x4456  ldc.i4.0
0x4457  ldloc.1
0x4458  ldloc.2
0x4459  ldloca.s 0xA
0x445b  call     instance string [mscorlib]System.Int32::ToString()
0x4460  ldloc.s  0xB
0x4462  ldloc.s  0xC
0x4464  ldloc.s  0xD
0x4466  ldarg.s  4
0x4468  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ExecutionTime()
0x446d  stloc.s  0x12
0x446f  ldloca.s 0x12
0x4471  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4476  ldloc.3
0x4477  ldarg.s  5
0x4479  ldarg.s  6
0x447b  ldarg.s  7
0x447d  ldloc.s  4
0x447f  ldloc.s  5
0x4481  ldarg.s  4
0x4483  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x4488  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x448d  ldloc.s  0xE
0x448f  ldarg.s  4
0x4491  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x4496  ldarg.s  8
0x4498  brfalse.s loc_44A3
0x449a  ldarg.s  8
0x449c  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x44a1  br.s     loc_44A4
0x44a3  ldc.i4.0
0x44a4  ldarg.s  8
0x44a6  brfalse.s loc_44B1
0x44a8  ldarg.s  8
0x44aa  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalRequestsExecuted()
0x44af  br.s     loc_44B2
0x44b1  ldc.i4.0
0x44b2  ldarg.s  9
0x44b4  ldarg.s  0xA
0x44b6  ldarg.s  0xB
0x44b8  ldarg.s  0xC
0x44ba  ldarg.s  0xD
0x44bc  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanNativeProcessCount()
0x44c1  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::get_CleanDrawbridgeProcessCount()
0x44c6  ldarg.s  0xE
0x44c8  brtrue.s loc_44CD
0x44ca  ldc.i4.0
0x44cb  br.s     loc_44CE
0x44cd  ldc.i4.2
0x44ce  ldsfld   string [mscorlib]System.String::Empty
0x44d3  call     instance void Microsoft.Crm.Sandbox.SandboxHost::TraceExecution(valuetype [mscorlib]System.Guid organizationId, string component, bool passed, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid requestId, string errorCode, string exceptionDetails, string originalException, string exceptionSource, float64 executionTime, int32 depth, string assemblyName, string typeName, string codeUnitType, valuetype [mscorlib]System.Guid workerId, int32 workerProcessId, valuetype [mscorlib]System.Guid executionId, valuetype [mscorlib]System.Guid parentExecutionId, string errorCategory, bool useDrawBridgeIsolation, int32 totalActiveWorkerRequestCount, int32 totalRequestsExecutedByWorkerId, int32 orgCleanBucketsCount, int32 orgReadyBucketsCount, int32 orgInitializingBucketsCount, int32 orgWaitingInitializingBucketCount, int32 orgInactiveBucketCount, int32 hostCleanNativeProcessCount, int32 hostCleanDrawbridgeProcessCount, int32 perceivedPassed, string messageName)
0x44d8  ldloc.s  7
0x44da  throw
0x44db  ldarg.1
0x44dc  isinst   [mscorlib]System.TimeoutException
0x44e1  brfalse.s loc_455F
0x44e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44e8  ldstr    aUnexpectedExce_0// "UNEXPECTED: exception not converted. WC"...
0x44ed  ldarg.1
0x44ee  call     string [mscorlib]System.String::Concat(object, object)
0x44f3  ldc.i4.0
0x44f4  newarr   [mscorlib]System.Object
0x44f9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44fe  stloc.s  0xB
0x4500  ldnull
0x4501  ldloc.0
0x4502  ldc.i4.s 0x21
0x4504  ldstr    a0// "{0}"
0x4509  ldc.i4.1
0x450a  newarr   [mscorlib]System.Object
0x450f  dup
0x4510  ldc.i4.0
0x4511  ldloc.s  0xB
0x4513  stelem.ref
0x4514  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4519  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::get_Instance()
0x451e  ldloc.0
0x451f  ldstr    aSandboxhost// "SandboxHost"
0x4524  ldc.i4.0
0x4525  ldloc.1
0x4526  ldloca.s 0xA
0x4528  call     instance string [mscorlib]System.Int32::ToString()
0x452d  ldloc.s  0xB
0x452f  ldarg.s  4
0x4531  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ExecutionTime()
0x4536  stloc.s  0x12
0x4538  ldloca.s 0x12
0x453a  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x453f  stloc.s  0x13
0x4541  ldloca.s 0x13
0x4543  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4548  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x454d  ldloc.3
0x454e  ldarg.s  5
0x4550  ldarg.s  6
0x4552  ldarg.s  7
0x4554  ldloc.s  4
0x4556  ldloc.s  5
0x4558  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxChannelTimeoutLog(valuetype [mscorlib]System.Guid, string, bool, valuetype [mscorlib]System.Guid, string, string, string, int32, string, string, string, valuetype [mscorlib]System.Guid, int32)
0x455d  br.s     loc_45D7
0x455f  ldarg.1
0x4560  isinst   [System.ServiceModel]System.ServiceModel.CommunicationException
0x4565  brfalse.s loc_459F
0x4567  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x456c  ldstr    aUnexpectedExce_0// "UNEXPECTED: exception not converted. WC"...
0x4571  ldarg.1
0x4572  call     string [mscorlib]System.String::Concat(object, object)
0x4577  ldc.i4.0
  ... truncated ...
```
