# Microsoft.Crm.Application.Utility.OrganizationSdkProxyFactory::CreateSdkService_0

- ea: `0x40b70`
- end: `0x40c69`
- name: `Microsoft.Crm.Application.Utility.OrganizationSdkProxyFactory::CreateSdkService_0`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x40b60`
- `0x7b260`

## callees

- `0x33f80`
- `0x33f90`
- `0x3a010`
- `0x40b70`
- `0x40c70`

## string_xrefs

- `0x40b97`: `Creating the Sdk Service in the server context requires a valid caller id.`
- `0x40baa`: `Creating the Sdk Service in the server context requires a valid organization name.`

## pseudocode

```c

```

## disassembly

```asm
0x40b70  ldarg.0
0x40b71  callvirt instance string Microsoft.Crm.Application.Utility.IOrganizationSdkProxyContext::get_OrganizationName()
0x40b76  stloc.0
0x40b77  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x40b7c  brfalse.s loc_40B90
0x40b7e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x40b83  brtrue.s loc_40B90
0x40b85  ldstr    aShouldNeverRea// "Should never reach this point."
0x40b8a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x40b8f  throw
0x40b90  ldarga.s 1
0x40b92  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x40b97  ldstr    aCreatingTheSdk// "Creating the Sdk Service in the server "...
0x40b9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x40ba1  ldloc.0
0x40ba2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40ba7  ldc.i4.0
0x40ba8  ceq
0x40baa  ldstr    aCreatingTheSdk_0// "Creating the Sdk Service in the server "...
0x40baf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x40bb4  ldarg.3
0x40bb5  brfalse.s loc_40BEB
0x40bb7  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_Application()
0x40bbc  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin
0x40bc1  stloc.2
0x40bc2  ldloc.2
0x40bc3  ldarg.s  4
0x40bc5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin::set_Feature(int32)
0x40bca  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x40bcf  ldarg.0
0x40bd0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x40bd5  ldarga.s 1
0x40bd7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x40bdc  ldnull
0x40bdd  ldloc.2
0x40bde  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x40be3  ldarg.s  5
0x40be5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x40bea  ret
0x40beb  ldarg.0
0x40bec  callvirt instance string Microsoft.Crm.Application.Utility.IOrganizationSdkProxyContext::get_ServerUrl()
0x40bf1  ldloc.0
0x40bf2  ldarg.0
0x40bf3  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateForOrganization(string uri, string organizationName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x40bf8  dup
0x40bf9  ldloc.0
0x40bfa  call     void Microsoft.Crm.Application.Utility.OrganizationSdkProxyFactory::SetSdkPath(class Microsoft.Crm.Application.Utility.CrmUri baseUri, string orgName)
0x40bff  callvirt instance string [mscorlib]System.Object::ToString()
0x40c04  newobj   instance void [System]System.Uri::.ctor(string)
0x40c09  ldnull
0x40c0a  ldnull
0x40c0b  ldnull
0x40c0c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::.ctor(class [System]System.Uri, class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x40c11  dup
0x40c12  ldarga.s 1
0x40c14  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x40c19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::set_CallerId(valuetype [mscorlib]System.Guid)
0x40c1e  dup
0x40c1f  ldarg.2
0x40c20  conv.r8
0x40c21  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x40c26  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x40c2b  stloc.1
0x40c2c  ldarg.s  5
0x40c2e  ldnull
0x40c2f  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x40c34  brfalse.s loc_40C67
0x40c36  ldloc.1
0x40c37  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x40c3c  brfalse.s loc_40C67
0x40c3e  ldloc.1
0x40c3f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x40c44  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_CurrentServiceEndpoint()
0x40c49  brfalse.s loc_40C67
0x40c4b  ldloc.1
0x40c4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x40c51  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_CurrentServiceEndpoint()
0x40c56  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x40c5b  ldarg.s  5
0x40c5d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ProxyTypesBehavior::.ctor(class [mscorlib]System.Reflection.Assembly)
0x40c62  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x40c67  ldloc.1
0x40c68  ret
```
