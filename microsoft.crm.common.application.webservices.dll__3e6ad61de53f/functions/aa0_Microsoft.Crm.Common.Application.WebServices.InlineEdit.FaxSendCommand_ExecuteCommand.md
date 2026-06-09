# Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::ExecuteCommand

- ea: `0xaa0`
- end: `0xb36`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::ExecuteCommand`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  ldarg.1
0xaa2  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.FaxSendInputParameter>::Deserialize(!!T0)
0xaa7  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.FaxSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::_faxSendInputParameter
0xaac  ldarg.0
0xaad  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::ValidateInputParameters()
0xab2  ldarg.0
0xab3  ldarg.0
0xab4  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.FaxSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::_faxSendInputParameter
0xab9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xabe  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0xac3  ldarg.0
0xac4  ldarg.0
0xac5  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.FaxSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::_faxSendInputParameter
0xaca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_EntityMetadata()
0xacf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xad4  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0xad9  ldc.i4   0x106C
0xade  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xae3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xae8  stloc.0
0xae9  ldloc.0
0xaea  ldarg.0
0xaeb  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.FaxSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::_faxSendInputParameter
0xaf0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xaf5  stloc.2
0xaf6  ldloca.s 2
0xaf8  ldstr    aB// "B"
0xafd  call     instance string [mscorlib]System.Guid::ToString(string)
0xb02  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xb07  ldc.i4.1
0xb08  newarr   [mscorlib]System.String
0xb0d  dup
0xb0e  ldc.i4.0
0xb0f  ldstr    aFaxnumber// "faxnumber"
0xb14  stelem.ref
0xb15  stloc.1
0xb16  ldloc.0
0xb17  ldloc.1
0xb18  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::UpdateAndRetrieve(string[])
0xb1d  leave.s  loc_B29
0xb1f  pop
0xb20  ldloc.0
0xb21  ldloc.1
0xb22  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::CreateAndRetrieve(string[])
0xb27  leave.s  loc_B29
0xb29  ldloc.0
0xb2a  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFaxCommand(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xb2f  ldarg.0
0xb30  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::RetrieveEntity()
0xb35  ret
```
