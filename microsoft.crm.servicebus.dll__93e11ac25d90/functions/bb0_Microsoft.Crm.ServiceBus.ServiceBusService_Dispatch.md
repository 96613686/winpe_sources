# Microsoft.Crm.ServiceBus.ServiceBusService::Dispatch

- ea: `0xbb0`
- end: `0xe1e`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::Dispatch`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb00`

## callees

- `0xbb0`
- `0xe20`
- `0xe80`
- `0x1a70`
- `0x1a90`
- `0x1ab0`
- `0x1af0`
- `0x1b10`
- `0x1bb0`
- `0x1bd0`
- `0x1c50`
- `0x1c70`
- `0x1cb0`
- `0x1d10`
- `0x1d30`
- `0x2950`
- `0x2990`
- `0x29d0`
- `0x2a30`
- `0x2a70`
- `0x2ae0`
- `0x38b0`
- `0x38d0`

## pseudocode

```c

```

## disassembly

```asm
0xbb0  ldnull
0xbb1  stloc.0
0xbb2  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xbb7  stloc.1
0xbb8  ldloc.1
0xbb9  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xbbe  ldarg.1
0xbbf  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0xbc4  ldc.i4.8
0xbc5  bne.un.s loc_BD2
0xbc7  ldarg.0
0xbc8  ldarg.1
0xbc9  ldarg.2
0xbca  call     instance string Microsoft.Crm.ServiceBus.ServiceBusService::WebhookDispatch(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xbcf  stloc.0
0xbd0  br.s     loc_BDB
0xbd2  ldarg.0
0xbd3  ldarg.1
0xbd4  ldarg.2
0xbd5  call     instance string Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusDispatch(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xbda  stloc.0
0xbdb  ldloc.1
0xbdc  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbe1  leave    loc_D4F
0xbe6  stloc.2
0xbe7  ldloc.1
0xbe8  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbed  ldsfld   string [mscorlib]System.String::Empty
0xbf2  stloc.3
0xbf3  ldc.i4.0
0xbf4  stloc.s  4
0xbf6  ldc.i4.0
0xbf7  stloc.s  5
0xbf9  ldc.i4.0
0xbfa  stloc.s  6
0xbfc  ldc.i4.0
0xbfd  stloc.s  7
0xbff  ldc.i4.0
0xc00  stloc.s  8
0xc02  ldloc.2
0xc03  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0xc08  stloc.s  9
0xc0a  ldloc.s  9
0xc0c  brtrue.s loc_C1C
0xc0e  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.ServiceBusService::_exceptionConverter
0xc13  ldloc.2
0xc14  ldloca.s 9
0xc16  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToCrmException(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException&)
0xc1b  pop
0xc1c  ldloc.s  9
0xc1e  brfalse.s loc_C3F
0xc20  ldloc.s  9
0xc22  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xc27  stloc.s  0xA
0xc29  ldloca.s 0xA
0xc2b  call     instance string [mscorlib]System.Int32::ToString()
0xc30  stloc.3
0xc31  ldloc.s  9
0xc33  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xc38  call     int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::ClassifyErrorCode(int32)
0xc3d  stloc.s  4
0xc3f  ldarg.1
0xc40  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0xc45  ldc.i4.8
0xc46  bne.un.s loc_C77
0xc48  ldarg.1
0xc49  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Url()
0xc4e  newobj   instance void [System]System.Uri::.ctor(string)
0xc53  call     class [System]System.Net.ServicePoint [System]System.Net.ServicePointManager::FindServicePoint(class [System]System.Uri)
0xc58  dup
0xc59  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLimit()
0xc5e  stloc.s  5
0xc60  dup
0xc61  callvirt instance int32 [System]System.Net.ServicePoint::get_MaxIdleTime()
0xc66  stloc.s  6
0xc68  dup
0xc69  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLeaseTimeout()
0xc6e  stloc.s  7
0xc70  callvirt instance int32 [System]System.Net.ServicePoint::get_CurrentConnections()
0xc75  stloc.s  8
0xc77  call     class Microsoft.Crm.ServiceBus.ServiceEndpointEventSource Microsoft.Crm.ServiceBus.ServiceEndpointEventSource::get_Instance()
0xc7c  ldarg.2
0xc7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xc82  ldc.i4.0
0xc83  ldsfld   string [mscorlib]System.String::Empty
0xc88  ldarg.1
0xc89  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0xc8e  ldarg.1
0xc8f  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0xc94  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertAuthTypeToString(int32 authType)
0xc99  ldarg.1
0xc9a  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0xc9f  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertContractTypeToString(int32 type)
0xca4  ldarg.1
0xca5  callvirt instance valuetype UserClaimType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserClaim()
0xcaa  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertUserClaimTypeToString(int32 type)
0xcaf  ldsfld   string [mscorlib]System.String::Empty
0xcb4  ldarg.1
0xcb5  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_SolutionName()
0xcba  dup
0xcbb  brtrue.s loc_CC3
0xcbd  pop
0xcbe  ldsfld   string [mscorlib]System.String::Empty
0xcc3  ldsfld   string [mscorlib]System.String::Empty
0xcc8  ldarg.1
0xcc9  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_IsFederatedMode()
0xcce  ldarg.1
0xccf  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ValidateOnly()
0xcd4  ldsfld   string [mscorlib]System.String::Empty
0xcd9  ldarg.1
0xcda  callvirt instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_MessageFormat()
0xcdf  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertMessageFormatToString(int32 format)
0xce4  ldarg.1
0xce5  callvirt instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceFormat()
0xcea  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertNamespaceFormatTypeToString(int32 format)
0xcef  ldsfld   string [mscorlib]System.String::Empty
0xcf4  ldarg.1
0xcf5  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Scheme()
0xcfa  ldarg.1
0xcfb  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AssemblyName()
0xd00  ldarg.2
0xd01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0xd06  ldarg.2
0xd07  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0xd0c  ldarg.2
0xd0d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0xd12  ldarg.2
0xd13  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0xd18  stloc.s  0xB
0xd1a  ldloca.s 0xB
0xd1c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xd21  ldloc.1
0xd22  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xd27  ldloc.3
0xd28  ldloc.2
0xd29  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xd2e  callvirt instance string [mscorlib]System.Object::ToString()
0xd33  ldloc.2
0xd34  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xd39  ldloc.s  4
0xd3b  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertOperationResult(int32 operationResult)
0xd40  ldloc.s  5
0xd42  ldloc.s  6
0xd44  ldloc.s  7
0xd46  ldloc.s  8
0xd48  callvirt instance void Microsoft.Crm.ServiceBus.ServiceEndpointEventSource::LogUsage(valuetype [mscorlib]System.Guid organizationId, bool passed, string serviceEndpointName, string serviceEndpointId, string authType, string contract, string userClaimType, string url, string solutionName, string path, bool isFederatedMode, bool validateOnly, string sasKeyName, string messageFormat, string namespaceFormat, string namespaceAddress, string scheme, string pluginType, valuetype [mscorlib]System.Guid primaryEntityId, string requestName, valuetype [mscorlib]System.Guid correlationId, valuetype [mscorlib]System.Guid requestId, int64 executionTime, string errorCode, string exceptionType, string exceptionMessage, string errorCategory, int32 maxConnectionLimit, int32 maxIdleTime, int32 connectionLeaseTimeout, int32 currentConnections)
0xd4d  rethrow
0xd4f  call     class Microsoft.Crm.ServiceBus.ServiceEndpointEventSource Microsoft.Crm.ServiceBus.ServiceEndpointEventSource::get_Instance()
0xd54  ldarg.2
0xd55  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xd5a  ldc.i4.1
0xd5b  ldsfld   string [mscorlib]System.String::Empty
0xd60  ldarg.1
0xd61  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0xd66  ldarg.1
0xd67  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0xd6c  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertAuthTypeToString(int32 authType)
0xd71  ldarg.1
0xd72  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0xd77  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertContractTypeToString(int32 type)
0xd7c  ldarg.1
0xd7d  callvirt instance valuetype UserClaimType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_UserClaim()
0xd82  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertUserClaimTypeToString(int32 type)
0xd87  ldsfld   string [mscorlib]System.String::Empty
0xd8c  ldarg.1
0xd8d  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_SolutionName()
0xd92  dup
0xd93  brtrue.s loc_D9B
0xd95  pop
0xd96  ldsfld   string [mscorlib]System.String::Empty
0xd9b  ldsfld   string [mscorlib]System.String::Empty
0xda0  ldarg.1
0xda1  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_IsFederatedMode()
0xda6  ldarg.1
0xda7  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ValidateOnly()
0xdac  ldsfld   string [mscorlib]System.String::Empty
0xdb1  ldarg.1
0xdb2  callvirt instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_MessageFormat()
0xdb7  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertMessageFormatToString(int32 format)
0xdbc  ldarg.1
0xdbd  callvirt instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceFormat()
0xdc2  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::ConvertNamespaceFormatTypeToString(int32 format)
0xdc7  ldsfld   string [mscorlib]System.String::Empty
0xdcc  ldarg.1
0xdcd  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Scheme()
0xdd2  ldarg.1
0xdd3  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AssemblyName()
0xdd8  ldarg.2
0xdd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0xdde  ldarg.2
0xddf  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0xde4  ldarg.2
0xde5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0xdea  ldarg.2
0xdeb  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0xdf0  stloc.s  0xB
0xdf2  ldloca.s 0xB
0xdf4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xdf9  ldloc.1
0xdfa  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xdff  ldsfld   string [mscorlib]System.String::Empty
0xe04  ldsfld   string [mscorlib]System.String::Empty
0xe09  ldsfld   string [mscorlib]System.String::Empty
0xe0e  ldsfld   string [mscorlib]System.String::Empty
0xe13  ldc.i4.0
0xe14  ldc.i4.0
0xe15  ldc.i4.0
0xe16  ldc.i4.0
0xe17  callvirt instance void Microsoft.Crm.ServiceBus.ServiceEndpointEventSource::LogUsage(valuetype [mscorlib]System.Guid organizationId, bool passed, string serviceEndpointName, string serviceEndpointId, string authType, string contract, string userClaimType, string url, string solutionName, string path, bool isFederatedMode, bool validateOnly, string sasKeyName, string messageFormat, string namespaceFormat, string namespaceAddress, string scheme, string pluginType, valuetype [mscorlib]System.Guid primaryEntityId, string requestName, valuetype [mscorlib]System.Guid correlationId, valuetype [mscorlib]System.Guid requestId, int64 executionTime, string errorCode, string exceptionType, string exceptionMessage, string errorCategory, int32 maxConnectionLimit, int32 maxIdleTime, int32 connectionLeaseTimeout, int32 currentConnections)
0xe1c  ldloc.0
0xe1d  ret
```
