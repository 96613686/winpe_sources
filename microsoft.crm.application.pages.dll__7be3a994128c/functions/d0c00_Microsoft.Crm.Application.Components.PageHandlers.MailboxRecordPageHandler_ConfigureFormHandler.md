# Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::ConfigureFormHandler

- ea: `0xd0c00`
- end: `0xd0dc5`
- name: `Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::ConfigureFormHandler`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xd0dd0`
- `0xd11c0`
- `0xd2150`

## string_xrefs

- `0xd0cd1`: `incomingemaildeliverymethod`
- `0xd0cbb`: `enabledforincomingemail`
- `0xd0c0b`: `testemailconfigurationscheduled`
- `0xd0c8f`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0xd0c00  ldarg.0
0xd0c01  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c06  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c0b  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0xd0c10  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c15  pop
0xd0c16  ldarg.0
0xd0c17  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c1c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c21  ldstr    aHostid// "hostid"
0xd0c26  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c2b  pop
0xd0c2c  ldarg.0
0xd0c2d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c32  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c37  ldstr    aIspasswordset// "ispasswordset"
0xd0c3c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c41  pop
0xd0c42  ldarg.0
0xd0c43  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c48  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c4d  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0xd0c52  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c57  pop
0xd0c58  ldarg.0
0xd0c59  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c5e  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c63  ldstr    aRegardingobjec// "regardingobjectid"
0xd0c68  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c6d  pop
0xd0c6e  ldarg.0
0xd0c6f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c74  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c79  ldstr    aEmailserverpro// "emailserverprofile"
0xd0c7e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c83  pop
0xd0c84  ldarg.0
0xd0c85  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0c8a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0c8f  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd0c94  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0c99  pop
0xd0c9a  ldarg.0
0xd0c9b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0ca0  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0ca5  ldstr    aIsforwardmailb// "isforwardmailbox"
0xd0caa  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0caf  pop
0xd0cb0  ldarg.0
0xd0cb1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0cb6  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0cbb  ldstr    aEnabledforinco// "enabledforincomingemail"
0xd0cc0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0cc5  pop
0xd0cc6  ldarg.0
0xd0cc7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0ccc  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0cd1  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xd0cd6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0cdb  pop
0xd0cdc  ldarg.0
0xd0cdd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0ce2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0ce7  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0xd0cec  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0cf1  pop
0xd0cf2  ldarg.0
0xd0cf3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0cf8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0cfd  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0xd0d02  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d07  pop
0xd0d08  ldarg.0
0xd0d09  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0d0e  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0d13  ldstr    aActdeliverymet// "actdeliverymethod"
0xd0d18  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d1d  pop
0xd0d1e  ldarg.0
0xd0d1f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0d24  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0d29  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0xd0d2e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d33  pop
0xd0d34  ldarg.0
0xd0d35  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0d3a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0d3f  ldstr    aUsername_0// "username"
0xd0d44  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d49  pop
0xd0d4a  ldarg.0
0xd0d4b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0d50  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0d55  ldstr    aPassword// "password"
0xd0d5a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d5f  pop
0xd0d60  ldarg.0
0xd0d61  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0d66  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0xd0d6b  ldstr    aEnabledforact// "enabledforact"
0xd0d70  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd0d75  pop
0xd0d76  ldarg.0
0xd0d77  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd0d7c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0xd0d81  stloc.0
0xd0d82  ldloc.0
0xd0d83  ldarg.0
0xd0d84  ldftn    instance void Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::OnObjectModelReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0xd0d8a  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm/ObjectModelReadyEventHandler::.ctor(object, native int)
0xd0d8f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::add_ObjectModelReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm/ObjectModelReadyEventHandler)
0xd0d94  ldloc.0
0xd0d95  ldarg.0
0xd0d96  ldftn    instance void Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::CustomFields_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0xd0d9c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0xd0da1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0xd0da6  ldarg.0
0xd0da7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd0dac  ldarg.0
0xd0dad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd0db2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xd0db7  ldarg.0
0xd0db8  ldloc.0
0xd0db9  call     instance void Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::DisableACTDeliveryMethod(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm customizableForm)
0xd0dbe  ldarg.0
0xd0dbf  call     instance void Microsoft.Crm.Application.Components.PageHandlers.MailboxRecordPageHandler::SetClientVariables()
0xd0dc4  ret
```
