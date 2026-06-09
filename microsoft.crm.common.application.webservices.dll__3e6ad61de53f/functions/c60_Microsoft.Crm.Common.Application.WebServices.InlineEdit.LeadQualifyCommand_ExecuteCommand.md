# Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::ExecuteCommand

- ea: `0xc60`
- end: `0xdcb`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::ExecuteCommand`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.1
0xc61  brtrue.s loc_C65
0xc63  ldnull
0xc64  ret
0xc65  ldarg.0
0xc66  ldarg.1
0xc67  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter>::Deserialize(!!T0)
0xc6c  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xc71  ldarg.0
0xc72  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xc77  brtrue.s loc_C8A
0xc79  ldc.i4   0x80047101
0xc7e  ldc.i4.0
0xc7f  newarr   [mscorlib]System.Object
0xc84  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xc89  throw
0xc8a  ldarg.0
0xc8b  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xc90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_FormId()
0xc95  stloc.2
0xc96  ldloca.s 2
0xc98  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc9d  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xca2  brfalse.s loc_CBD
0xca4  ldc.i4   0x80040356
0xca9  ldc.i4.1
0xcaa  newarr   [mscorlib]System.Object
0xcaf  dup
0xcb0  ldc.i4.0
0xcb1  ldstr    aFormIdIsNullOr// "Form Id is null or empty"
0xcb6  stelem.ref
0xcb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcbc  throw
0xcbd  ldarg.0
0xcbe  callvirt instance class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_InputParameter()
0xcc3  call     void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::SaveEntityDataReceivedFromClient(class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter)
0xcc8  ldarg.0
0xcc9  ldarg.0
0xcca  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xccf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xcd4  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0xcd9  ldarg.0
0xcda  ldarg.0
0xcdb  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xce0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_EntityMetadata()
0xce5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xcea  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0xcef  ldarg.0
0xcf0  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xcf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0xcfa  ldarg.0
0xcfb  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd00  callvirt instance bool [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_CreateAccount()
0xd05  ldarg.0
0xd06  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd0b  callvirt instance bool [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_CreateContact()
0xd10  ldarg.0
0xd11  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd16  callvirt instance bool [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_CreateOpportunity()
0xd1b  ldarg.0
0xd1c  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd21  callvirt instance int32 [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_NewStatusCode()
0xd26  ldarg.0
0xd27  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_OpportunityCurrencyId()
0xd31  stloc.2
0xd32  ldloca.s 2
0xd34  ldstr    aB// "B"
0xd39  call     instance string [mscorlib]System.Guid::ToString(string)
0xd3e  ldarg.0
0xd3f  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_OpportunityParentId()
0xd49  stloc.2
0xd4a  ldloca.s 2
0xd4c  ldstr    aB// "B"
0xd51  call     instance string [mscorlib]System.Guid::ToString(string)
0xd56  ldarg.0
0xd57  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd5c  callvirt instance int32 [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_OpportunityParentType()
0xd61  ldnull
0xd62  ldarg.0
0xd63  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::_leadQualifyInputParameter
0xd68  callvirt instance bool [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.LeadQualifyInputParameter::get_SuppressDuplicateDetection()
0xd6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd72  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference> [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Commands.ApplicationCommand::LeadQualify(valuetype [mscorlib]System.Guid, bool, bool, bool, int32, string, string, int32, string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd77  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, bool> <>c::<>9__3_0
0xd7c  dup
0xd7d  brtrue.s loc_D96
0xd7f  pop
0xd80  ldsfld   class <>c <>c::<>9
0xd85  ldftn    instance bool <>c::<ExecuteCommand>b__3_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference e)
0xd8b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, bool>::.ctor(object, native int)
0xd90  dup
0xd91  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, bool> <>c::<>9__3_0
0xd96  call     T0x2B000006
0xd9b  stloc.0
0xd9c  ldc.i4.3
0xd9d  ldc.i4.3
0xd9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda3  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetInstance(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda8  stloc.1
0xda9  ldarg.0
0xdaa  ldloc.0
0xdab  brtrue.s loc_DB4
0xdad  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdb2  br.s     loc_DBA
0xdb4  ldloc.0
0xdb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xdba  ldstr    aOpportunity// "opportunity"
0xdbf  ldloc.1
0xdc0  callvirt instance string[] [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.Mediators.FormMediator::GetColumns()
0xdc5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::RetrieveEntity(valuetype [mscorlib]System.Guid, string, string[])
0xdca  ret
```
