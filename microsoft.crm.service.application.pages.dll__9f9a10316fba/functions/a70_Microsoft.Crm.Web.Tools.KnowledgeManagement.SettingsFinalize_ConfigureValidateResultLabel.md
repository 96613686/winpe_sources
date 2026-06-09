# Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigureValidateResultLabel

- ea: `0xa70`
- end: `0xe05`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigureValidateResultLabel`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xee0`

## callees

- `0xa70`
- `0x14280`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.1
0xa71  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xa76  stloc.0
0xa77  ldloc.0
0xa78  ldc.i4   0x350CA8AF
0xa7d  bgt.un   loc_B11
0xa82  ldloc.0
0xa83  ldc.i4   0x22BDC987
0xa88  bgt.un.s loc_AC8
0xa8a  ldloc.0
0xa8b  ldc.i4   0x1EBDC33B
0xa90  bgt.un.s loc_AAD
0xa92  ldloc.0
0xa93  ldc.i4   0x1DBDC1A8
0xa98  beq      loc_C6F
0xa9d  ldloc.0
0xa9e  ldc.i4   0x1EBDC33B
0xaa3  beq      loc_CED
0xaa8  br       loc_DF4
0xaad  ldloc.0
0xaae  ldc.i4   0x1FBDC4CE
0xab3  beq      loc_D02
0xab8  ldloc.0
0xab9  ldc.i4   0x22BDC987
0xabe  beq      loc_C30
0xac3  br       loc_DF4
0xac8  ldloc.0
0xac9  ldc.i4   0x24BDCCAD
0xace  bgt.un.s loc_AEB
0xad0  ldloc.0
0xad1  ldc.i4   0x23BDCB1A
0xad6  beq      loc_C45
0xadb  ldloc.0
0xadc  ldc.i4   0x24BDCCAD
0xae1  beq      loc_C5A
0xae6  br       loc_DF4
0xaeb  ldloc.0
0xaec  ldc.i4   0x2B98A2B0
0xaf1  beq      loc_C99
0xaf6  ldloc.0
0xaf7  ldc.i4   0x340CA71C
0xafc  beq      loc_CC3
0xb01  ldloc.0
0xb02  ldc.i4   0x350CA8AF
0xb07  beq      loc_B9D
0xb0c  br       loc_DF4
0xb11  ldloc.0
0xb12  ldc.i4   0x6733D49C
0xb17  bgt.un.s loc_B54
0xb19  ldloc.0
0xb1a  ldc.i4   0x370CABD5
0xb1f  bgt.un.s loc_B3C
0xb21  ldloc.0
0xb22  ldc.i4   0x360CAA42
0xb27  beq      loc_BDC
0xb2c  ldloc.0
0xb2d  ldc.i4   0x370CABD5
0xb32  beq      loc_BC7
0xb37  br       loc_DF4
0xb3c  ldloc.0
0xb3d  ldc.i4   0x6333CE50
0xb42  beq      loc_C1B
0xb47  ldloc.0
0xb48  ldc.i4   0x6733D49C
0xb4d  beq.s    loc_BB2
0xb4f  br       loc_DF4
0xb54  ldloc.0
0xb55  ldc.i4   0x6A33D955
0xb5a  bgt.un.s loc_B77
0xb5c  ldloc.0
0xb5d  ldc.i4   0x6933D7C2
0xb62  beq      loc_BF1
0xb67  ldloc.0
0xb68  ldc.i4   0x6A33D955
0xb6d  beq      loc_C06
0xb72  br       loc_DF4
0xb77  ldloc.0
0xb78  ldc.i4   0xA22FFC43
0xb7d  beq      loc_CD8
0xb82  ldloc.0
0xb83  ldc.i4   0xAA3008DB
0xb88  beq      loc_C84
0xb8d  ldloc.0
0xb8e  ldc.i4   0xD291D247
0xb93  beq      loc_CAE
0xb98  br       loc_DF4
0xb9d  ldarg.1
0xb9e  ldstr    a0// "0"
0xba3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba8  brtrue   loc_D17
0xbad  br       loc_DF4
0xbb2  ldarg.1
0xbb3  ldstr    a100// "100"
0xbb8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbbd  brtrue   loc_D28
0xbc2  br       loc_DF4
0xbc7  ldarg.1
0xbc8  ldstr    a2// "2"
0xbcd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd2  brtrue   loc_D39
0xbd7  br       loc_DF4
0xbdc  ldarg.1
0xbdd  ldstr    a3// "3"
0xbe2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbe7  brtrue   loc_D4A
0xbec  br       loc_DF4
0xbf1  ldarg.1
0xbf2  ldstr    a102// "102"
0xbf7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbfc  brtrue   loc_D5B
0xc01  br       loc_DF4
0xc06  ldarg.1
0xc07  ldstr    a103// "103"
0xc0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc11  brtrue   loc_D6C
0xc16  br       loc_DF4
0xc1b  ldarg.1
0xc1c  ldstr    a104// "104"
0xc21  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc26  brtrue   loc_D7D
0xc2b  br       loc_DF4
0xc30  ldarg.1
0xc31  ldstr    aC6001// "C6001"
0xc36  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc3b  brtrue   loc_D8E
0xc40  br       loc_DF4
0xc45  ldarg.1
0xc46  ldstr    aC6002// "C6002"
0xc4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc50  brtrue   loc_D9F
0xc55  br       loc_DF4
0xc5a  ldarg.1
0xc5b  ldstr    aC6003// "C6003"
0xc60  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc65  brtrue   loc_DB0
0xc6a  br       loc_DF4
0xc6f  ldarg.1
0xc70  ldstr    aC6004// "C6004"
0xc75  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc7a  brtrue   loc_DC1
0xc7f  br       loc_DF4
0xc84  ldarg.1
0xc85  ldstr    a400// "400"
0xc8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc8f  brtrue   loc_DD2
0xc94  br       loc_DF4
0xc99  ldarg.1
0xc9a  ldstr    a500// "500"
0xc9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca4  brtrue   loc_DE3
0xca9  br       loc_DF4
0xcae  ldarg.1
0xcaf  ldstr    aC5000// "C5000"
0xcb4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcb9  brtrue   loc_DE3
0xcbe  br       loc_DF4
0xcc3  ldarg.1
0xcc4  ldstr    a1// "1"
0xcc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcce  brtrue   loc_DF4
0xcd3  br       loc_DF4
0xcd8  ldarg.1
0xcd9  ldstr    a408// "408"
0xcde  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce3  brtrue   loc_DF4
0xce8  br       loc_DF4
0xced  ldarg.1
0xcee  ldstr    aC6005// "C6005"
0xcf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcf8  brtrue   loc_DF4
0xcfd  br       loc_DF4
0xd02  ldarg.1
0xd03  ldstr    aC6006// "C6006"
0xd08  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0d  brtrue   loc_DF4
0xd12  br       loc_DF4
0xd17  ldarg.0
0xd18  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd1d  ldstr    aWebToolsKnowle_13// "Web.Tools.KnowledgeManagement.SettingsP"...
0xd22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd27  ret
0xd28  ldarg.0
0xd29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd2e  ldstr    aWebToolsKnowle_14// "Web.Tools.KnowledgeManagement.SettingsP"...
0xd33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd38  ret
0xd39  ldarg.0
0xd3a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd3f  ldstr    aWebToolsKmSett// "Web.Tools.KM.SettingsPage.WarningMessag"...
0xd44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd49  ret
0xd4a  ldarg.0
0xd4b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd50  ldstr    aWebToolsKmSett_0// "Web.Tools.KM.SettingsPage.WarningMessag"...
0xd55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd5a  ret
0xd5b  ldarg.0
0xd5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd61  ldstr    aWebToolsKmSett_1// "Web.Tools.KM.SettingsPage.WarningMessag"...
0xd66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6b  ret
0xd6c  ldarg.0
0xd6d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd72  ldstr    aWebToolsKmSett_2// "Web.Tools.KM.SettingsPage.WarningMessag"...
0xd77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd7c  ret
0xd7d  ldarg.0
0xd7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd83  ldstr    aWebToolsKmSett_3// "Web.Tools.KM.SettingsPage.WarningMessag"...
0xd88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd8d  ret
0xd8e  ldarg.0
0xd8f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd94  ldstr    aSearchwidgetPa_3// "SearchWidget.Parature.LoginFail.403.C60"...
0xd99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd9e  ret
0xd9f  ldarg.0
0xda0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda5  ldstr    aSearchwidgetPa_4// "SearchWidget.Parature.InvalidCredential"...
0xdaa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdaf  ret
0xdb0  ldarg.0
0xdb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdb6  ldstr    aSearchwidgetPa// "SearchWidget.Parature.InvalidDeptId.403"...
0xdbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdc0  ret
0xdc1  ldarg.0
0xdc2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdc7  ldstr    aSearchwidgetPa_0// "SearchWidget.Parature.InvalidAccountId."...
0xdcc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdd1  ret
0xdd2  ldarg.0
0xdd3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdd8  ldstr    aSearchwidgetPa_1// "SearchWidget.Parature.PerminssionError."...
0xddd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde2  ret
0xde3  ldarg.0
0xde4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xde9  ldstr    aSearchwidgetPa_5// "SearchWidget.Parature.InternalServer.50"...
0xdee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdf3  ret
0xdf4  ldarg.0
0xdf5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdfa  ldstr    aWebToolsDocume_2// "Web.Tools.DocumentManagement.SettingsPa"...
0xdff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe04  ret
```
