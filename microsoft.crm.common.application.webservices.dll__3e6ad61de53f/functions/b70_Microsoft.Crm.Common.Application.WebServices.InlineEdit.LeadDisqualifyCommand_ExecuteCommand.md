# Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::ExecuteCommand

- ea: `0xb70`
- end: `0xc26`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::ExecuteCommand`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb70`

## pseudocode

```c

```

## disassembly

```asm
0xb70  ldarg.1
0xb71  brtrue.s loc_B75
0xb73  ldnull
0xb74  ret
0xb75  ldarg.0
0xb76  ldarg.1
0xb77  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter>::Deserialize(!!T0)
0xb7c  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xb81  ldarg.0
0xb82  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xb87  brtrue.s loc_B9A
0xb89  ldc.i4   0x80047101
0xb8e  ldc.i4.0
0xb8f  newarr   [mscorlib]System.Object
0xb94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xb99  throw
0xb9a  ldarg.0
0xb9b  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xba0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_FormId()
0xba5  stloc.0
0xba6  ldloca.s 0
0xba8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbad  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbb2  brfalse.s loc_BCD
0xbb4  ldc.i4   0x80040356
0xbb9  ldc.i4.1
0xbba  newarr   [mscorlib]System.Object
0xbbf  dup
0xbc0  ldc.i4.0
0xbc1  ldstr    aFormIdIsNullOr// "Form Id is null or empty"
0xbc6  stelem.ref
0xbc7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xbcc  throw
0xbcd  ldarg.0
0xbce  callvirt instance class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_InputParameter()
0xbd3  call     void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::SaveEntityDataReceivedFromClient(class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter)
0xbd8  ldarg.0
0xbd9  ldarg.0
0xbda  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xbdf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xbe4  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0xbe9  ldarg.0
0xbea  ldarg.0
0xbeb  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xbf0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_EntityMetadata()
0xbf5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xbfa  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0xbff  ldarg.0
0xc00  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xc05  callvirt instance int32 [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter::get_NewStatusCode()
0xc0a  ldarg.0
0xc0b  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadDisqualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::_leadDisqualifyInputParameter
0xc10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xc15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc1a  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadDisqualify(int32, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc1f  ldarg.0
0xc20  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::RetrieveEntity()
0xc25  ret
```
