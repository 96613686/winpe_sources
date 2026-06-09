# Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::ExecuteCommand

- ea: `0x8e0`
- end: `0xa68`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::ExecuteCommand`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8e0`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  ldarg.0
0x8e1  ldarg.1
0x8e2  call     var<u1> class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter`1<class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter>::Deserialize(!!T0)
0x8e7  stfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x8ec  ldarg.0
0x8ed  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x8f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0x8f7  stloc.3
0x8f8  ldloca.s 3
0x8fa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ff  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x904  stloc.0
0x905  ldarg.0
0x906  ldloc.0
0x907  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::ValidateInputParameters(bool)
0x90c  ldarg.0
0x90d  ldarg.0
0x90e  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x913  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_Id()
0x918  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityId(valuetype [mscorlib]System.Guid)
0x91d  ldarg.0
0x91e  ldarg.0
0x91f  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x924  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_EntityMetadata()
0x929  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x92e  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::set_EntityLogicalName(string)
0x933  ldc.i4   0x106A
0x938  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x942  stloc.1
0x943  ldloc.1
0x944  ldarg.0
0x945  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x94a  callvirt instance string [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InputParameter::get_DataXml()
0x94f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x954  ldloc.1
0x955  ldloc.0
0x956  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0x95b  ldloc.1
0x95c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x961  brtrue.s loc_97C
0x963  ldloc.1
0x964  ldarg.0
0x965  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_EntityId()
0x96a  stloc.3
0x96b  ldloca.s 3
0x96d  ldstr    aB// "B"
0x972  call     instance string [mscorlib]System.Guid::ToString(string)
0x977  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x97c  ldloc.1
0x97d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_HasData()
0x982  brfalse.s loc_98D
0x984  ldarg.0
0x985  ldloc.1
0x986  ldc.i4.1
0x987  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::UpdateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, bool)
0x98c  pop
0x98d  ldstr    aEmail// "email"
0x992  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x997  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x99c  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9a1  stloc.2
0x9a2  ldarg.0
0x9a3  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0x9a8  callvirt instance string [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter::get_SendType()
0x9ad  stloc.s  4
0x9af  ldloc.s  4
0x9b1  ldstr    aSend// "send"
0x9b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bb  brtrue.s loc_9E9
0x9bd  ldloc.s  4
0x9bf  ldstr    aReply// "reply"
0x9c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c9  brtrue.s loc_A16
0x9cb  ldloc.s  4
0x9cd  ldstr    aReplyall// "replyall"
0x9d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9d7  brtrue.s loc_A24
0x9d9  ldloc.s  4
0x9db  ldstr    aForward// "forward"
0x9e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9e5  brtrue.s loc_A32
0x9e7  br.s     loc_A40
0x9e9  ldloc.2
0x9ea  ldloc.1
0x9eb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x9f0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_InnerEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x9f5  ldarg.0
0x9f6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_Parameters()
0x9fb  ldstr    aSendsucceed// "sendSucceed"
0xa00  ldloc.2
0xa01  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::Send()
0xa06  stloc.s  5
0xa08  ldloca.s 5
0xa0a  call     instance string [mscorlib]System.Boolean::ToString()
0xa0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa14  br.s     loc_A4B
0xa16  ldloc.2
0xa17  ldloc.1
0xa18  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xa1d  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::CreateReply(string)
0xa22  br.s     loc_A4B
0xa24  ldloc.2
0xa25  ldloc.1
0xa26  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xa2b  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAll(string)
0xa30  br.s     loc_A4B
0xa32  ldloc.2
0xa33  ldloc.1
0xa34  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xa39  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::CreateForward(string)
0xa3e  br.s     loc_A4B
0xa40  ldstr    aEmailSendTypeN// "Email send type not recognized"
0xa45  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xa4a  throw
0xa4b  ldarg.0
0xa4c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CommandBase::get_Parameters()
0xa51  ldstr    aSendtype// "sendType"
0xa56  ldarg.0
0xa57  ldfld    class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::_entityParameter
0xa5c  callvirt instance string [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.EmailSendInputParameter::get_SendType()
0xa61  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa66  ldloc.2
0xa67  ret
```
