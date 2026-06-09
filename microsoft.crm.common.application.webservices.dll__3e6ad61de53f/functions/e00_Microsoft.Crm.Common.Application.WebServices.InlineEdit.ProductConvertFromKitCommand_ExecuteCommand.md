# Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::ExecuteCommand

- ea: `0xe00`
- end: `0xe4b`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::ExecuteCommand`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xe50`

## pseudocode

```c

```

## disassembly

```asm
0xe00  ldarg.0
0xe01  ldarg.1
0xe02  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter>::Deserialize(!!T0)
0xe07  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::_convertProductFromKitInputParameter
0xe0c  ldarg.0
0xe0d  call     instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::ValidateInput()
0xe12  ldarg.0
0xe13  ldarg.0
0xe14  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::_convertProductFromKitInputParameter
0xe19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xe1e  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0xe23  ldarg.0
0xe24  ldarg.0
0xe25  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ConvertProductFromKitInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::_convertProductFromKitInputParameter
0xe2a  callvirt instance string [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Name()
0xe2f  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0xe34  ldarg.0
0xe35  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_EntityId()
0xe3a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe3f  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertKitToProduct(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe44  ldarg.0
0xe45  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::RetrieveEntity()
0xe4a  ret
```
