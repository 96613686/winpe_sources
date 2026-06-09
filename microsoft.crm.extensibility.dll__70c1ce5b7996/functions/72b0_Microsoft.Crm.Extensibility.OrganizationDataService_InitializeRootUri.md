# Microsoft.Crm.Extensibility.OrganizationDataService::InitializeRootUri

- ea: `0x72b0`
- end: `0x7314`
- name: `Microsoft.Crm.Extensibility.OrganizationDataService::InitializeRootUri`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e40`

## callees

- `0x72b0`
- `0x7320`

## string_xrefs

- `0x72c8`: `MicrosoftDataServicesRootUri`
- `0x72f5`: `MicrosoftDataServicesRequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x72b0  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x72b5  brfalse.s loc_7313
0x72b7  call     bool [Microsoft.Xrm.Service]Microsoft.Crm.Extensibility.SdkServiceEndpointBuilder::get_OffloadingEnabled()
0x72bc  brfalse.s loc_7313
0x72be  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x72c3  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageProperties [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageProperties()
0x72c8  ldstr    aMicrosoftdatas// "MicrosoftDataServicesRootUri"
0x72cd  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x72d2  callvirt instance class [System.ServiceModel]System.ServiceModel.IContextChannel [System.ServiceModel]System.ServiceModel.OperationContext::get_Channel()
0x72d7  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.IContextChannel::get_LocalAddress()
0x72dc  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x72e1  call     class [System]System.Uri Microsoft.Crm.Extensibility.OrganizationDataService::AdjustUriForSslOffloading(class [System]System.Uri originalUri)
0x72e6  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageProperties::set_Item(string, object)
0x72eb  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x72f0  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageProperties [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageProperties()
0x72f5  ldstr    aMicrosoftdatas_0// "MicrosoftDataServicesRequestUri"
0x72fa  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x72ff  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7304  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x7309  call     class [System]System.Uri Microsoft.Crm.Extensibility.OrganizationDataService::AdjustUriForSslOffloading(class [System]System.Uri originalUri)
0x730e  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageProperties::set_Item(string, object)
0x7313  ret
```
