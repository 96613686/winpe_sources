# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues

- ea: `0x1440`
- end: `0x14a7`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10c0`

## callees

- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldarg.1
0x1441  brfalse.s loc_14A6
0x1443  ldarg.1
0x1444  callvirt instance valuetype [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.AuthenticationType [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_ActiveAuthenticationType()
0x1449  ldc.i4.5
0x144a  bne.un.s loc_1492
0x144c  ldarg.1
0x144d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0x1452  brfalse.s loc_14A6
0x1454  ldarg.1
0x1455  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0x145a  callvirt instance class [System.ServiceModel]System.ServiceModel.IClientChannel class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_InnerChannel()
0x145f  ldarg.2
0x1460  callvirt instance void [System.ServiceModel]System.ServiceModel.IContextChannel::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x1465  ldarg.1
0x1466  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0x146b  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_Endpoint()
0x1470  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1475  ldarg.2
0x1476  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0x147b  ldarg.1
0x147c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0x1481  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_Endpoint()
0x1486  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x148b  ldarg.2
0x148c  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x1491  ret
0x1492  ldarg.1
0x1493  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationServiceProxy()
0x1498  brfalse.s loc_14A6
0x149a  ldarg.1
0x149b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationServiceProxy()
0x14a0  ldarg.2
0x14a1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x14a6  ret
```
