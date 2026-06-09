# Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::ExecuteCommand

- ea: `0xee0`
- end: `0xf2b`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::ExecuteCommand`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xee0  ldarg.0
0xee1  ldarg.1
0xee2  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter>::Deserialize(!!T0)
0xee7  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::_convertProductToKitInputParameter
0xeec  ldarg.0
0xeed  call     instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::ValidateInput()
0xef2  ldarg.0
0xef3  ldarg.0
0xef4  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::_convertProductToKitInputParameter
0xef9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xefe  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0xf03  ldarg.0
0xf04  ldarg.0
0xf05  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductToKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::_convertProductToKitInputParameter
0xf0a  callvirt instance string [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Name()
0xf0f  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0xf14  ldarg.0
0xf15  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_EntityId()
0xf1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf1f  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertProductToKit(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf24  ldarg.0
0xf25  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::RetrieveEntity()
0xf2a  ret
```
