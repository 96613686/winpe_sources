# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::get_ServiceInstance

- ea: `0xd30`
- end: `0xd60`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::get_ServiceInstance`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xa50`

## callees

- `0xd30`

## string_xrefs

- `0xd37`: `Microsoft.Crm.Service.ObjectModel`
- `0xd41`: `Microsoft.Crm.Service.ObjectModel.TemplateServiceFactory`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_serviceInstance
0xd35  brtrue.s loc_D5A
0xd37  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.ObjectModel"
0xd3c  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0xd41  ldstr    aMicrosoftCrmSe_0// "Microsoft.Crm.Service.ObjectModel.Templ"...
0xd46  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0xd4b  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0xd50  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory
0xd55  stsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_serviceInstance
0xd5a  ldsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_serviceInstance
0xd5f  ret
```
