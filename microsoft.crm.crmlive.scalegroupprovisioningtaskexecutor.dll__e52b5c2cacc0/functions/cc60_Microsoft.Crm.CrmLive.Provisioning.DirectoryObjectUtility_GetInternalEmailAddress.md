# Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::GetInternalEmailAddress

- ea: `0xcc60`
- end: `0xcd25`
- name: `Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::GetInternalEmailAddress`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xcc00`

## callees

- `0xcc60`
- `0xcd30`

## string_xrefs

- `0xcc90`: `emailrouteraccessapproval`
- `0xccd0`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0xcc60  ldarg.2
0xcc61  ldarg.1
0xcc62  ldstr    aMail// "Mail"
0xcc67  call     string Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::RetrieveStringValueFromProvider(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, string propertyName)
0xcc6c  stloc.0
0xcc6d  ldarg.2
0xcc6e  ldarg.1
0xcc6f  ldstr    aUsertype// "UserType"
0xcc74  callvirt T0x2B000042
0xcc79  brtrue.s loc_CCE1
0xcc7b  ldloc.0
0xcc7c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcc81  brtrue.s loc_CCA1
0xcc83  ldarg.0
0xcc84  ldstr    aInternalemaila// "internalemailaddress"
0xcc89  ldloc.0
0xcc8a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcc8f  ldarg.0
0xcc90  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xcc95  ldc.i4.1
0xcc96  box      [mscorlib]System.Int32
0xcc9b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcca0  ret
0xcca1  ldarg.2
0xcca2  ldarg.1
0xcca3  ldstr    aUserprincipaln// "UserPrincipalName"
0xcca8  call     string Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::RetrieveStringValueFromProvider(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, string propertyName)
0xccad  stloc.1
0xccae  ldloc.1
0xccaf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xccb4  brtrue.s loc_CD24
0xccb6  ldloc.1
0xccb7  ldstr    aExt// "#EXT#"
0xccbc  callvirt instance bool [mscorlib]System.String::Contains(string)
0xccc1  brtrue.s loc_CD24
0xccc3  ldarg.0
0xccc4  ldstr    aInternalemaila// "internalemailaddress"
0xccc9  ldloc.1
0xccca  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcccf  ldarg.0
0xccd0  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xccd5  ldc.i4.1
0xccd6  box      [mscorlib]System.Int32
0xccdb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcce0  ret
0xcce1  ldarg.2
0xcce2  ldarg.1
0xcce3  ldstr    aOthermail// "OtherMail"
0xcce8  call     string Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::RetrieveStringValueFromProvider(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, string propertyName)
0xcced  stloc.2
0xccee  ldloc.2
0xccef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xccf4  brtrue.s loc_CD03
0xccf6  ldarg.0
0xccf7  ldstr    aInternalemaila// "internalemailaddress"
0xccfc  ldloc.2
0xccfd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcd02  ret
0xcd03  ldloc.0
0xcd04  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcd09  brtrue.s loc_CD24
0xcd0b  ldloc.0
0xcd0c  ldstr    aExt// "#EXT#"
0xcd11  callvirt instance bool [mscorlib]System.String::Contains(string)
0xcd16  brtrue.s loc_CD24
0xcd18  ldarg.0
0xcd19  ldstr    aInternalemaila// "internalemailaddress"
0xcd1e  ldloc.0
0xcd1f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcd24  ret
```
