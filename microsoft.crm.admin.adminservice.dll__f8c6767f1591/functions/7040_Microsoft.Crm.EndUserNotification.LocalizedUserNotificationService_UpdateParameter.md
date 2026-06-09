# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::UpdateParameter

- ea: `0x7040`
- end: `0x70e8`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::UpdateParameter`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7020`

## callees

- `0x5370`
- `0x7040`

## string_xrefs

- `0x7089`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x70d0`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x7084`: `UpdateParameter`
- `0x70cb`: `UpdateParameter`
- `0x7097`: `Could not find parameter to update`

## pseudocode

```c

```

## disassembly

```asm
0x7040  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x7045  stloc.0
0x7046  ldloc.0
0x7047  ldstr    aName// "Name"
0x704c  ldarg.2
0x704d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7052  ldloc.0
0x7053  ldstr    aNotificationid_0// "NotificationId"
0x7058  ldarg.1
0x7059  box      [mscorlib]System.Guid
0x705e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x7063  ldarg.0
0x7064  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x7069  stloc.1
0x706a  ldloc.1
0x706b  ldstr    aEndusernotific_1// "EndUserNotificationParameters"
0x7070  ldc.i4.1
0x7071  newarr   [mscorlib]System.String
0x7076  dup
0x7077  ldc.i4.0
0x7078  ldstr    aId// "Id"
0x707d  stelem.ref
0x707e  ldloc.0
0x707f  ldc.i4   0x54E
0x7084  ldstr    aUpdateparamete// "UpdateParameter"
0x7089  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x708e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x7093  stloc.2
0x7094  ldloc.2
0x7095  brtrue.s loc_70A2
0x7097  ldstr    aCouldNotFindPa// "Could not find parameter to update"
0x709c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x70a1  throw
0x70a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x70a7  stloc.3
0x70a8  ldloc.3
0x70a9  ldstr    aValue_0// "Value"
0x70ae  ldarg.3
0x70af  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x70b4  ldloc.1
0x70b5  ldstr    aEndusernotific_1// "EndUserNotificationParameters"
0x70ba  ldloc.2
0x70bb  ldstr    aId// "Id"
0x70c0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x70c5  ldloc.3
0x70c6  ldc.i4   0x554
0x70cb  ldstr    aUpdateparamete// "UpdateParameter"
0x70d0  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x70d5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x70da  pop
0x70db  leave.s  loc_70E7
0x70dd  ldloc.1
0x70de  brfalse.s loc_70E6
0x70e0  ldloc.1
0x70e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70e6  endfinally
0x70e7  ret
```
