# Microsoft.Crm.Application.Controls.ResourceUtility::SetAppHeaderResources

- ea: `0x97d00`
- end: `0x984cb`
- name: `Microsoft.Crm.Application.Controls.ResourceUtility::SetAppHeaderResources`
- size: `1995`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x95630`

## callees

- `0x97d00`

## string_xrefs

- `0x97d9c`: `LOCID_FORMED_BUSINESSRECOMNDED`
- `0x98042`: `LOCID_FORMED_REMOVESECLOCKEDTAB`
- `0x98059`: `LOCID_FORMED_REMOVESECLOCKED`
- `0x98070`: `LOCID_FORMED_REMOVESECLOCKEDFLD`
- `0x98087`: `LOCID_FORMED_REMOVESECQUICKCRT`
- `0x9809e`: `LOCID_FORMED_REMOVESECCARDCRT`
- `0x9821f`: `LOCID_FORMED_REMOVETABLOCKED`
- `0x98236`: `LOCID_FORMED_REMOVETABLOCKEDSEC`
- `0x9824d`: `LOCID_FORMED_REMOVETABLOCKEDFLD`
- `0x98316`: `LOCID_FORMED_CONFIRMREMOVETAB`
- `0x9831c`: `Web.Tools.FormEditor.Scripts.Util.js.RemoveTab`
- `0x9832d`: `LOCID_FORMED_CONFIRMREMOVESEC`
- `0x98333`: `Web.Tools.FormEditor.Scripts.Util.js.RemoveSection`
- `0x98344`: `LOCID_FORMED_CONFIRMREMOVEFLD`
- `0x9834a`: `Web.Tools.FormEditor.Scripts.Util.js.RemoveCell`
- `0x983d4`: `Form_Editor_Command_Group_Tab`

## pseudocode

```c

```

## disassembly

```asm
0x97d00  ldarg.2
0x97d01  ldstr    aFielddialogsJs// "fielddialogs.js"
0x97d06  call     T0x2B00007B
0x97d0b  ldc.i4.0
0x97d0c  blt      loc_97DE0
0x97d11  ldarg.0
0x97d12  ldstr    aLocidFormedEnt// "LOCID_FORMED_ENTERDISPLAYNAME"
0x97d17  ldarg.1
0x97d18  ldstr    aWebToolsFormed_6// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x97d1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d22  ldc.i4.0
0x97d23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d28  ldarg.0
0x97d29  ldstr    aLocidFormedIll// "LOCID_FORMED_ILLEGALCHRINLABEL"
0x97d2e  ldarg.1
0x97d2f  ldstr    aWebToolsFormed_7// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x97d34  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d39  ldc.i4.0
0x97d3a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d3f  ldarg.0
0x97d40  ldstr    aLocidFormedIll_0// "LOCID_FORMED_ILLEGALCHRINFIELD"
0x97d45  ldarg.1
0x97d46  ldstr    aWebToolsFormed_8// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x97d4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d50  ldc.i4.0
0x97d51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d56  ldarg.0
0x97d57  ldstr    aLocidFormedDis// "LOCID_FORMED_DISPLAYNAMEINUSE"
0x97d5c  ldarg.1
0x97d5d  ldstr    aWebToolsFormed_9// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x97d62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d67  ldc.i4.0
0x97d68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d6d  ldarg.0
0x97d6e  ldstr    aLocidFormedSys// "LOCID_FORMED_SYSTEMREQUIRED"
0x97d73  ldarg.1
0x97d74  ldstr    a2531443dF63c45// "2531443D-F63C-45db-9B2D-23943C52308A"
0x97d79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d7e  ldc.i4.0
0x97d7f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d84  ldarg.0
0x97d85  ldstr    aLocidFormedBus// "LOCID_FORMED_BUSINESSREQUIRED"
0x97d8a  ldarg.1
0x97d8b  ldstr    a31dee51f671a49// "31DEE51F-671A-4926-9AF6-DA7F5F961B50"
0x97d90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97d95  ldc.i4.0
0x97d96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97d9b  ldarg.0
0x97d9c  ldstr    aLocidFormedBus_0// "LOCID_FORMED_BUSINESSRECOMNDED"
0x97da1  ldarg.1
0x97da2  ldstr    a1e6890f9F8da4c// "1E6890F9-F8DA-4C2F-8061-DF97DD1C3842"
0x97da7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97dac  ldc.i4.0
0x97dad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97db2  ldarg.0
0x97db3  ldstr    aLocidFormedNoc// "LOCID_FORMED_NOCONSTRAINT"
0x97db8  ldarg.1
0x97db9  ldstr    a29bef7063b774e// "29BEF706-3B77-4E80-80D3-D49784AA096E"
0x97dbe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97dc3  ldc.i4.0
0x97dc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97dc9  ldarg.0
0x97dca  ldstr    aLocidFormedOne// "LOCID_FORMED_ONEAUTOPERTAB"
0x97dcf  ldarg.1
0x97dd0  ldstr    aWebToolsFormed_1// "Web.Tools.FormEditor.scripts.Fielddialo"...
0x97dd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97dda  ldc.i4.0
0x97ddb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97de0  ldarg.2
0x97de1  ldstr    aFieldsJs// "fields.js"
0x97de6  call     T0x2B00007B
0x97deb  ldc.i4.0
0x97dec  blt      loc_97FBD
0x97df1  ldarg.0
0x97df2  ldstr    aLocidFormedFal// "LOCID_FORMED_FALSESTRING"
0x97df7  ldarg.1
0x97df8  ldstr    aWebToolsFormed_10// "Web.Tools.FormEditor.scripts.Fileds.js."...
0x97dfd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e02  ldc.i4.0
0x97e03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e08  ldarg.0
0x97e09  ldstr    aLocidFormedTru// "LOCID_FORMED_TRUESTRING"
0x97e0e  ldarg.1
0x97e0f  ldstr    aWebToolsFormed_11// "Web.Tools.FormEditor.scripts.Fileds.js."...
0x97e14  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e19  ldc.i4.0
0x97e1a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e1f  ldarg.0
0x97e20  ldstr    aLocidFormedDef// "LOCID_FORMED_DEFAULTVALUE"
0x97e25  ldarg.1
0x97e26  ldstr    aWebToolsFormed_12// "Web.Tools.FormEditor.scripts.Fileds.js."...
0x97e2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e30  ldc.i4.0
0x97e31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e36  ldarg.0
0x97e37  ldstr    aLocidFormedChf// "LOCID_FORMED_CHFLDLOCKEDSECTION"
0x97e3c  ldarg.1
0x97e3d  ldstr    aWebToolsFormed_13// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97e42  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e47  ldc.i4.0
0x97e48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e4d  ldarg.0
0x97e4e  ldstr    aLocidFormedChf_0// "LOCID_FORMED_CHFLDLOCKEDTAB"
0x97e53  ldarg.1
0x97e54  ldstr    aWebToolsFormed_14// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97e59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e5e  ldc.i4.0
0x97e5f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e64  ldarg.0
0x97e65  ldstr    aLocidFormedFie// "LOCID_FORMED_FIELDLOCKED"
0x97e6a  ldarg.1
0x97e6b  ldstr    aWebToolsFormed_15// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97e70  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e75  ldc.i4.0
0x97e76  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e7b  ldarg.0
0x97e7c  ldstr    aLocidFormedFie_0// "LOCID_FORMED_FIELDLOCKEDSECTION"
0x97e81  ldarg.1
0x97e82  ldstr    aWebToolsFormed_16// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97e87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97e8c  ldc.i4.0
0x97e8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97e92  ldarg.0
0x97e93  ldstr    aLocidFormedFie_1// "LOCID_FORMED_FIELDLOCKEDTAB"
0x97e98  ldarg.1
0x97e99  ldstr    aWebToolsFormed_17// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97e9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97ea3  ldc.i4.0
0x97ea4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97ea9  ldarg.0
0x97eaa  ldstr    aLocidFormedFie_2// "LOCID_FORMED_FIELDREQUIRED"
0x97eaf  ldarg.1
0x97eb0  ldstr    aWebToolsFormed_18// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97eb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97eba  ldc.i4.0
0x97ebb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97ec0  ldarg.0
0x97ec1  ldstr    aLocidFormedFie_3// "LOCID_FORMED_FIELDDEPENDENTHEAD"
0x97ec6  ldarg.1
0x97ec7  ldstr    aWebToolsFormed_19// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97ecc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97ed1  ldc.i4.0
0x97ed2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97ed7  ldarg.0
0x97ed8  ldstr    aLocidFormedFie_4// "LOCID_FORMED_FIELDDEPENDENTTITLE"
0x97edd  ldarg.1
0x97ede  ldstr    aWebToolsFormed_20// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97ee3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97ee8  ldc.i4.0
0x97ee9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97eee  ldarg.0
0x97eef  ldstr    aLocidFormedAdd// "LOCID_FORMED_ADDSECTIONFIRST"
0x97ef4  ldarg.1
0x97ef5  ldstr    aWebToolsFormed_21// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97efa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97eff  ldc.i4.0
0x97f00  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f05  ldarg.0
0x97f06  ldstr    aLocidFormedAll// "LOCID_FORMED_ALLSECTIONLOCKED"
0x97f0b  ldarg.1
0x97f0c  ldstr    aWebToolsFormed_22// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97f11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f16  ldc.i4.0
0x97f17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f1c  ldarg.0
0x97f1d  ldstr    aLocidFormedAdd_0// "LOCID_FORMED_ADDFIELDLOCKEDTAB"
0x97f22  ldarg.1
0x97f23  ldstr    aWebToolsFormed_23// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97f28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f2d  ldc.i4.0
0x97f2e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f33  ldarg.0
0x97f34  ldstr    aLocidFormedAdd_1// "LOCID_FORMED_ADDFIELDLOCKEDSEC"
0x97f39  ldarg.1
0x97f3a  ldstr    aWebToolsFormed_24// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97f3f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f44  ldc.i4.0
0x97f45  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f4a  ldarg.0
0x97f4b  ldstr    aLocidFormedAdd_2// "LOCID_FORMED_ADDFIELDREFPANSEC"
0x97f50  ldarg.1
0x97f51  ldstr    aWebToolsFormed_25// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97f56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f5b  ldc.i4.0
0x97f5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f61  ldarg.0
0x97f62  ldstr    aLocidFormedAdd_3// "LOCID_FORMED_ADDFIELDCARDFORMSEC"
0x97f67  ldarg.1
0x97f68  ldstr    aWebToolsFormed_26// "Web.Tools.FormEditor.scripts.Fields.js."...
0x97f6d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f72  ldc.i4.0
0x97f73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f78  ldarg.0
0x97f79  ldstr    aLocidFormedNot// "LOCID_FORMED_NOTES_LABEL"
0x97f7e  ldarg.1
0x97f7f  ldstr    aFormEditorNote// "Form_Editor_NotesControl_Label"
0x97f84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f89  ldc.i4.0
0x97f8a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97f8f  ldarg.0
0x97f90  ldstr    aLocidFormedRiL// "LOCID_FORMED_RI_LABEL"
0x97f95  ldarg.1
0x97f96  ldstr    aRibbonFormedit// "Ribbon.Formeditor.Button.RICards.LabelT"...
0x97f9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97fa0  ldc.i4.0
0x97fa1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97fa6  ldarg.0
0x97fa7  ldstr    aLocidFormedUns// "LOCID_FORMED_UNSAVED_PUBLISH"
0x97fac  ldarg.1
0x97fad  ldstr    aWebToolsFormed_27// "Web.Tools.FormEditor.Messages.PublishUn"...
0x97fb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97fb7  ldc.i4.0
0x97fb8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97fbd  ldarg.2
0x97fbe  ldstr    aSectionsJs// "sections.js"
0x97fc3  call     T0x2B00007B
0x97fc8  ldc.i4.0
0x97fc9  blt      loc_98127
0x97fce  ldarg.0
0x97fcf  ldstr    aLocidFormedAdd_4// "LOCID_FORMED_ADDSECLOCKEDTAB"
0x97fd4  ldarg.1
0x97fd5  ldstr    aWebToolsFormed_28// "Web.Tools.FormEditor.scripts.Sections.j"...
0x97fda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97fdf  ldc.i4.0
0x97fe0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97fe5  ldarg.0
0x97fe6  ldstr    aLocidFormedAdd_5// "LOCID_FORMED_ADDSECTION"
0x97feb  ldarg.1
0x97fec  ldstr    aWebToolsFormed_29// "Web.Tools.FormEditor.Scripts.sections.j"...
0x97ff1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97ff6  ldc.i4.0
0x97ff7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x97ffc  ldarg.0
0x97ffd  ldstr    aLocidFormedAdd_6// "LOCID_FORMED_ADDSECTIONDESC"
0x98002  ldarg.1
0x98003  ldstr    aWebToolsFormed_30// "Web.Tools.FormEditor.Scripts.sections.j"...
0x98008  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9800d  ldc.i4.0
0x9800e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x98013  ldarg.0
0x98014  ldstr    aLocidFormedSec// "LOCID_FORMED_SECPROPS"
0x98019  ldarg.1
0x9801a  ldstr    aWebToolsFormed_31// "Web.Tools.FormEditor.Scripts.sections.j"...
0x9801f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98024  ldc.i4.0
0x98025  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9802a  ldarg.0
0x9802b  ldstr    aLocidFormedMod// "LOCID_FORMED_MODIFYSECPROPS"
0x98030  ldarg.1
0x98031  ldstr    aWebToolsFormed_32// "Web.Tools.FormEditor.Scripts.sections.j"...
0x98036  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9803b  ldc.i4.0
0x9803c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x98041  ldarg.0
0x98042  ldstr    aLocidFormedRem// "LOCID_FORMED_REMOVESECLOCKEDTAB"
0x98047  ldarg.1
0x98048  ldstr    aWebToolsFormed_33// "Web.Tools.FormEditor.Scripts.sections.j"...
0x9804d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98052  ldc.i4.0
0x98053  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x98058  ldarg.0
0x98059  ldstr    aLocidFormedRem_0// "LOCID_FORMED_REMOVESECLOCKED"
0x9805e  ldarg.1
0x9805f  ldstr    aWebToolsFormed_34// "Web.Tools.FormEditor.Scripts.sections.j"...
0x98064  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98069  ldc.i4.0
0x9806a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9806f  ldarg.0
0x98070  ldstr    aLocidFormedRem_1// "LOCID_FORMED_REMOVESECLOCKEDFLD"
0x98075  ldarg.1
0x98076  ldstr    aWebToolsFormed_35// "Web.Tools.FormEditor.Scripts.sections.j"...
0x9807b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98080  ldc.i4.0
0x98081  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x98086  ldarg.0
0x98087  ldstr    aLocidFormedRem_2// "LOCID_FORMED_REMOVESECQUICKCRT"
0x9808c  ldarg.1
0x9808d  ldstr    aWebToolsFormed_36// "Web.Tools.FormEditor.Scripts.sections.j"...
0x98092  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98097  ldc.i4.0
0x98098  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9809d  ldarg.0
0x9809e  ldstr    aLocidFormedRem_3// "LOCID_FORMED_REMOVESECCARDCRT"
0x980a3  ldarg.1
0x980a4  ldstr    aWebToolsFormed_37// "Web.Tools.FormEditor.Scripts.sections.j"...
0x980a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x980ae  ldc.i4.0
0x980af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x980b4  ldarg.0
0x980b5  ldstr    aLocidFormedSec_0// "LOCID_FORMED_SECTABDEPENDENT_HD"
0x980ba  ldarg.1
0x980bb  ldstr    aWebToolsFormed_38// "Web.Tools.FormEditor.scripts.Sections.j"...
0x980c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x980c5  ldc.i4.0
0x980c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x980cb  ldarg.0
0x980cc  ldstr    aLocidFormedSec_1// "LOCID_FORMED_SECTABDEPENDENT_TL"
0x980d1  ldarg.1
0x980d2  ldstr    aWebToolsFormed_39// "Web.Tools.FormEditor.scripts.Sections.j"...
0x980d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
