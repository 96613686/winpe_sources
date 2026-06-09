# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues

- ea: `0xc60`
- end: `0xcc7`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x930`

## callees

- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.1
0xc61  brfalse.s loc_CC6
0xc63  ldarg.1
0xc64  callvirt instance valuetype [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.AuthenticationType [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_ActiveAuthenticationType()
0xc69  ldc.i4.5
0xc6a  bne.un.s loc_CB2
0xc6c  ldarg.1
0xc6d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0xc72  brfalse.s loc_CC6
0xc74  ldarg.1
0xc75  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0xc7a  callvirt instance class [System.ServiceModel]System.ServiceModel.IClientChannel class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_InnerChannel()
0xc7f  ldarg.2
0xc80  callvirt instance void [System.ServiceModel]System.ServiceModel.IContextChannel::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0xc85  ldarg.1
0xc86  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0xc8b  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_Endpoint()
0xc90  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0xc95  ldarg.2
0xc96  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0xc9b  ldarg.1
0xc9c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationWebProxyClient()
0xca1  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class [System.ServiceModel]System.ServiceModel.ClientBase`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_Endpoint()
0xca6  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0xcab  ldarg.2
0xcac  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0xcb1  ret
0xcb2  ldarg.1
0xcb3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationServiceProxy()
0xcb8  brfalse.s loc_CC6
0xcba  ldarg.1
0xcbb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_OrganizationServiceProxy()
0xcc0  ldarg.2
0xcc1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0xcc6  ret
```
