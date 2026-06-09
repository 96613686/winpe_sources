# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::get_ServiceInstance

- ea: `0x990`
- end: `0x9c0`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::get_ServiceInstance`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6d0`

## callees

- `0x990`

## string_xrefs

- `0x997`: `Microsoft.Crm.Service.ObjectModel`
- `0x9a1`: `Microsoft.Crm.Service.ObjectModel.TemplateServiceFactory`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_serviceInstance
0x995  brtrue.s loc_9BA
0x997  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.ObjectModel"
0x99c  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x9a1  ldstr    aMicrosoftCrmSe_0// "Microsoft.Crm.Service.ObjectModel.Templ"...
0x9a6  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x9ab  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x9b0  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory
0x9b5  stsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_serviceInstance
0x9ba  ldsfld   class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_serviceInstance
0x9bf  ret
```
