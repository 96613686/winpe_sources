# Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody

- ea: `0x3ad0`
- end: `0x3d21`
- name: `Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody`
- size: `593`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3790`
- `0x3810`
- `0x3890`

## callees

- `0x3ad0`
- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3ad5  stloc.0
0x3ad6  ldloc.0
0x3ad7  ldstr    aPP// "<p></p>"
0x3adc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3ae1  pop
0x3ae2  ldloc.0
0x3ae3  ldstr    aSpanStyleFontF// "<span style=\"font-family:"
0x3ae8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3aed  pop
0x3aee  ldloc.0
0x3aef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3af4  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0x3af9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3afe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b08  pop
0x3b09  ldloc.0
0x3b0a  ldstr    aFontSize14px// ";font-size:14px\">"
0x3b0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b14  pop
0x3b15  ldloc.0
0x3b16  ldstr    aBr// "<br>"
0x3b1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b20  pop
0x3b21  ldloc.0
0x3b22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b27  ldstr    aEmailFollowupH// "Email_Followup_Header"
0x3b2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3b31  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b36  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3b3b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b40  pop
0x3b41  ldloc.0
0x3b42  ldstr    aBr// "<br>"
0x3b47  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b4c  pop
0x3b4d  ldarg.0
0x3b4e  ldstr    aFrom// "from"
0x3b53  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3b58  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3b5d  stloc.1
0x3b5e  ldloc.1
0x3b5f  brfalse.s loc_3B8B
0x3b61  ldloc.1
0x3b62  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3b67  ldc.i4.0
0x3b68  ble.s    loc_3B8B
0x3b6a  ldloc.0
0x3b6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b70  ldstr    aEmailFollowupS// "Email_Followup_Sender"
0x3b75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3b7a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b7f  ldloc.1
0x3b80  call     string Microsoft.Crm.Common.Application.Platform.Email::AddPartyToHeader(string partyName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection)
0x3b85  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b8a  pop
0x3b8b  ldloc.0
0x3b8c  ldstr    aB// "<b>"
0x3b91  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b96  pop
0x3b97  ldloc.0
0x3b98  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b9d  ldstr    aEmailFollowupR// "Email_Followup_ReceivedDate"
0x3ba2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3ba7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bac  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3bb1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3bb6  pop
0x3bb7  ldloc.0
0x3bb8  ldstr    aB_0// "</b> "
0x3bbd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3bc2  pop
0x3bc3  ldarg.0
0x3bc4  ldstr    aActualend// "actualend"
0x3bc9  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3bce  brfalse.s loc_3C0A
0x3bd0  ldloc.0
0x3bd1  ldarg.0
0x3bd2  ldstr    aActualend// "actualend"
0x3bd7  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3bdc  unbox.any [mscorlib]System.DateTime
0x3be1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3be6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x3beb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bf0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3bf5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3bfa  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDateAndTime(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bff  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3c04  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c09  pop
0x3c0a  ldloc.0
0x3c0b  ldstr    aBr// "<br>"
0x3c10  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c15  pop
0x3c16  ldarg.0
0x3c17  ldstr    aTo// "to"
0x3c1c  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3c21  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3c26  stloc.2
0x3c27  ldloc.2
0x3c28  brfalse.s loc_3C54
0x3c2a  ldloc.2
0x3c2b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3c30  ldc.i4.0
0x3c31  ble.s    loc_3C54
0x3c33  ldloc.0
0x3c34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c39  ldstr    aEmailFollowupT// "Email_Followup_ToRecipients"
0x3c3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3c43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3c48  ldloc.2
0x3c49  call     string Microsoft.Crm.Common.Application.Platform.Email::AddPartyToHeader(string partyName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection)
0x3c4e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c53  pop
0x3c54  ldarg.0
0x3c55  ldstr    aCc// "cc"
0x3c5a  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3c5f  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3c64  stloc.3
0x3c65  ldloc.3
0x3c66  brfalse.s loc_3C92
0x3c68  ldloc.3
0x3c69  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3c6e  ldc.i4.0
0x3c6f  ble.s    loc_3C92
0x3c71  ldloc.0
0x3c72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c77  ldstr    aEmailFollowupC// "Email_Followup_CcRecipients"
0x3c7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3c81  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3c86  ldloc.3
0x3c87  call     string Microsoft.Crm.Common.Application.Platform.Email::AddPartyToHeader(string partyName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection)
0x3c8c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c91  pop
0x3c92  ldloc.0
0x3c93  ldstr    aB// "<b>"
0x3c98  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c9d  pop
0x3c9e  ldloc.0
0x3c9f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3ca4  ldstr    aEmailFollowupS_0// "Email_Followup_Subject"
0x3ca9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3cae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3cb3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3cb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3cbd  pop
0x3cbe  ldloc.0
0x3cbf  ldstr    aB_0// "</b> "
0x3cc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3cc9  pop
0x3cca  ldloc.0
0x3ccb  ldarg.0
0x3ccc  ldstr    aSubject// "subject"
0x3cd1  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3cd6  castclass [mscorlib]System.String
0x3cdb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3ce0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3ce5  pop
0x3ce6  ldloc.0
0x3ce7  ldstr    aBrBr// "<br><br>"
0x3cec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3cf1  pop
0x3cf2  ldarg.0
0x3cf3  ldstr    aDescription// "description"
0x3cf8  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3cfd  stloc.s  4
0x3cff  ldloc.s  4
0x3d01  brfalse.s loc_3D1A
0x3d03  ldloc.s  4
0x3d05  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x3d0a  beq.s    loc_3D1A
0x3d0c  ldloc.0
0x3d0d  ldloc.s  4
0x3d0f  castclass [mscorlib]System.String
0x3d14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d19  pop
0x3d1a  ldloc.0
0x3d1b  callvirt instance string [mscorlib]System.Object::ToString()
0x3d20  ret
```
