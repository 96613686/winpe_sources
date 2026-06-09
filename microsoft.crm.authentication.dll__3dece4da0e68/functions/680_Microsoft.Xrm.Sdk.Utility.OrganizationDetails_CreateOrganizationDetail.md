# Microsoft.Xrm.Sdk.Utility.OrganizationDetails::CreateOrganizationDetail

- ea: `0x680`
- end: `0x766`
- name: `Microsoft.Xrm.Sdk.Utility.OrganizationDetails::CreateOrganizationDetail`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x150`
- `0x170`
- `0x1d0`
- `0x380`
- `0x540`
- `0x680`

## string_xrefs

- `0x71d`: `serviceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldarg.2
0x681  ldarg.1
0x682  ldarg.3
0x683  ldarg.s  5
0x685  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider Microsoft.Xrm.Sdk.Utility.EndpointProviderRetriever::GetEndpointProvider(int32 authenticationType, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointAccessType endpointAccessType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x68a  stloc.0
0x68b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::.ctor()
0x690  stloc.1
0x691  ldloc.1
0x692  ldarg.0
0x693  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x698  ldloc.1
0x699  ldarg.s  4
0x69b  ldarg.0
0x69c  ldarg.s  5
0x69e  callvirt instance string Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationFriendlyName(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x6a3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_FriendlyName(string)
0x6a8  ldloc.1
0x6a9  ldarg.s  4
0x6ab  ldarg.0
0x6ac  ldarg.s  5
0x6ae  callvirt instance class [mscorlib]System.Version Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationVersion(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x6b3  call     T0x2B000002
0x6b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_OrganizationVersion(string)
0x6bd  ldarg.s  5
0x6bf  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6c4  ldarg.0
0x6c5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganizationState(valuetype [mscorlib]System.Guid)
0x6ca  stloc.2
0x6cb  ldloc.1
0x6cc  ldloc.2
0x6cd  ldc.i4.1
0x6ce  beq.s    loc_6D3
0x6d0  ldc.i4.1
0x6d1  br.s     loc_6D4
0x6d3  ldc.i4.0
0x6d4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_State(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationState)
0x6d9  ldloc.1
0x6da  ldarg.s  4
0x6dc  ldarg.0
0x6dd  ldarg.s  5
0x6df  callvirt instance string Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationUrlName(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x6e4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_UrlName(string)
0x6e9  ldloc.1
0x6ea  ldarg.s  4
0x6ec  ldarg.0
0x6ed  ldarg.s  5
0x6ef  callvirt instance string Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationName(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x6f4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::set_UniqueName(string)
0x6f9  ldloc.0
0x6fa  brfalse.s loc_764
0x6fc  ldloc.1
0x6fd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::get_Endpoints()
0x702  ldc.i4.2
0x703  ldloc.0
0x704  ldarg.0
0x705  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetWebApplicationUrl(valuetype [mscorlib]System.Guid)
0x70a  call     T0x2B000003
0x70f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointType, string>::Add(var<u1>, !!T0)
0x714  ldloc.0
0x715  ldarg.0
0x716  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetCrmServiceUrl(valuetype [mscorlib]System.Guid)
0x71b  stloc.3
0x71c  ldloc.3
0x71d  ldstr    aServiceendpoin// "serviceEndpoint"
0x722  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x727  ldloc.1
0x728  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::get_Endpoints()
0x72d  ldc.i4.0
0x72e  ldloc.3
0x72f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x734  call     T0x2B000004
0x739  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointType, string>::Add(var<u1>, !!T0)
0x73e  ldloc.1
0x73f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail::get_Endpoints()
0x744  ldc.i4.1
0x745  ldloc.3
0x746  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x74b  ldstr    aOrganizationSv// "Organization.svc"
0x750  ldstr    aOrganizationda// "OrganizationData.svc"
0x755  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x75a  call     T0x2B000004
0x75f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointType, string>::Add(var<u1>, !!T0)
0x764  ldloc.1
0x765  ret
```
