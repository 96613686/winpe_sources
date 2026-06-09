# Microsoft.Crm.Sdk.Crm2007.MetadataService::Execute

- ea: `0xacf0`
- end: `0xad88`
- name: `Microsoft.Crm.Sdk.Crm2007.MetadataService::Execute`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe40`

## callees

- `0xacf0`
- `0xadb0`
- `0xfa50`

## string_xrefs

- `0xad0d`: `The Microsoft Dynamics CRM 4.0 (2007) Web service endpoint is not supported in this release.`

## pseudocode

```c

```

## disassembly

```asm
0xacf0  ldarg.1
0xacf1  ldstr    aRequest_0// "request"
0xacf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xacfb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0xad00  dup
0xad01  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LegacySupportValidatorUtility::Is2007EndpointValidForOrg(valuetype [mscorlib]System.Guid)
0xad06  brtrue.s loc_AD18
0xad08  ldc.i4   0x194
0xad0d  ldstr    aTheMicrosoftDy// "The Microsoft Dynamics CRM 4.0 (2007) W"...
0xad12  newobj   instance void [System.Web]System.Web.HttpException::.ctor(int32, string)
0xad17  throw
0xad18  ldarg.0
0xad19  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xad1e  ldc.i4.0
0xad1f  ldc.i4.0
0xad20  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xad25  stloc.0
0xad26  ldloc.0
0xad27  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xad2c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_TimeOut()
0xad31  ldc.i4.s 0x3C
0xad33  bge.s    loc_AD42
0xad35  ldloc.0
0xad36  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xad3b  ldc.i4.s 0x3C
0xad3d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_TimeOut(int32)
0xad42  ldloc.0
0xad43  ldarg.0
0xad44  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xad49  ldc.i4.0
0xad4a  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_CurrentSoapContext()
0xad4f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DefaultExecutionOperationContext::.ctor()
0xad54  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_WebServiceApi()
0xad59  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken)
0xad5e  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::ClearCurrentSoapContext()
0xad63  ldarg.1
0xad64  ldloc.0
0xad65  callvirt instance class Microsoft.Crm.Sdk.Crm2007.MetadataServiceResponse Microsoft.Crm.Sdk.Crm2007.MetadataServiceRequest::Process(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xad6a  ldloc.0
0xad6b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xad70  stloc.1
0xad71  leave.s  loc_AD86
0xad73  pop
0xad74  ldloc.0
0xad75  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xad7a  rethrow
0xad7c  ldloc.0
0xad7d  brfalse.s loc_AD85
0xad7f  ldloc.0
0xad80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad85  endfinally
0xad86  ldloc.1
0xad87  ret
```
