# Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.AppointmentConflictNotificationGenerator::AddNotificationIfNecessary

- ea: `0x6af0`
- end: `0x6c43`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.AppointmentConflictNotificationGenerator::AddNotificationIfNecessary`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x6af0`

## string_xrefs

- `0x6b21`: `scheduledstart`
- `0x6b31`: `scheduledend`
- `0x6c06`: `serviceactivity_edit_aspx_genericservererror`
- `0x6c33`: `PrivilegeCheck`

## pseudocode

```c

```

## disassembly

```asm
0x6af0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x6af5  brtrue.s loc_6B15
0x6af7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6afc  ldstr    aNotificationOu// "Notification_OutlookIsOffline"
0x6b01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6b06  stloc.0
0x6b07  ldarg.2
0x6b08  ldc.i4.1
0x6b09  ldloc.0
0x6b0a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6b0f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6b14  ret
0x6b15  ldarg.1
0x6b16  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x6b1b  brtrue   loc_6C42
0x6b20  ldarg.1
0x6b21  ldstr    aScheduledstart// "scheduledstart"
0x6b26  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6b2b  brfalse  loc_6C42
0x6b30  ldarg.1
0x6b31  ldstr    aScheduledend// "scheduledend"
0x6b36  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6b3b  brfalse  loc_6C42
0x6b40  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_SearchAvailability()
0x6b45  ldarg.0
0x6b46  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator::get_Context()
0x6b4b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b50  brfalse  loc_6C20
0x6b55  ldloca.s 1
0x6b57  ldarg.1
0x6b58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x6b5d  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6b62  ldarg.1
0x6b63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x6b68  ldloc.1
0x6b69  ldarg.0
0x6b6a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator::get_Context()
0x6b6f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ValidateCommand::.ctor(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b74  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ValidateCommand::Execute()
0x6b79  ldc.i4.0
0x6b7a  ldelem.ref
0x6b7b  stloc.2
0x6b7c  ldloc.2
0x6b7d  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult::get_ValidationSuccess()
0x6b82  brtrue.s loc_6B9A
0x6b84  ldarg.2
0x6b85  ldloc.2
0x6b86  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TraceInfo [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult::get_TraceInfo()
0x6b8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ErrorInfo[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TraceInfo::get_ErrorInfoList()
0x6b90  ldstr    aValidate// "Validate"
0x6b95  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotificationCollection::AddNotifications(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotificationCollection, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ErrorInfo[], string)
0x6b9a  leave    loc_6C42
0x6b9f  ldarg.0
0x6ba0  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator::get_Context()
0x6ba5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6baa  stloc.3
0x6bab  ldloc.3
0x6bac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Code()
0x6bb1  brfalse.s loc_6C01
0x6bb3  ldloc.3
0x6bb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Code()
0x6bb9  ldc.i4.2
0x6bba  ldloc.3
0x6bbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_Code()
0x6bc0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6bc5  ldc.i4.2
0x6bc6  sub
0x6bc7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6bcc  ldc.i4   0x203
0x6bd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6bd6  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x6bdb  ldc.i4   0x80048408
0x6be0  bne.un.s loc_6C01
0x6be2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6be7  ldstr    aErrorTitle0x80// "Error_Title_0x80048408"
0x6bec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6bf1  stloc.0
0x6bf2  ldarg.2
0x6bf3  ldc.i4.1
0x6bf4  ldloc.0
0x6bf5  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6bfa  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6bff  leave.s  loc_6C42
0x6c01  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6c06  ldstr    aServiceactivit// "serviceactivity_edit_aspx_genericserver"...
0x6c0b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c10  stloc.0
0x6c11  ldarg.2
0x6c12  ldc.i4.1
0x6c13  ldloc.0
0x6c14  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6c19  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6c1e  leave.s  loc_6C42
0x6c20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6c25  ldstr    aCannotValidate// "Cannot_Validate_Activity"
0x6c2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c2f  stloc.0
0x6c30  ldarg.2
0x6c31  ldc.i4.1
0x6c32  ldloc.0
0x6c33  ldstr    aPrivilegecheck// "PrivilegeCheck"
0x6c38  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string, string)
0x6c3d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6c42  ret
```
