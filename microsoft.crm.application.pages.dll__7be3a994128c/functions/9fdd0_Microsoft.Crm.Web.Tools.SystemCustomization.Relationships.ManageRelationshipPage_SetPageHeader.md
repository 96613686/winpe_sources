# Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::SetPageHeader

- ea: `0x9fdd0`
- end: `0xa0251`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::SetPageHeader`
- size: `1153`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9f460`

## callees

- `0x9f410`
- `0x9fdd0`
- `0xa0260`
- `0xa1c70`
- `0xa2150`
- `0xa2170`

## string_xrefs

- `0x9fe46`: `/_static/_common/styles/AutoToolTip.js`
- `0x9fed0`: `RelationshipUtil.Messages.CannotDeleteSystemRelationship`
- `0x9feec`: `RelationshipUtil.Messages.ConfirmRelationshipDelete`
- `0x9ffea`: `_bCreate`
- `0xa0230`: `txtCascadeDeleteLabel`

## pseudocode

```c

```

## disassembly

```asm
0x9fdd0  ldarg.0
0x9fdd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fdd6  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x9fddb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9fde0  ldarg.0
0x9fde1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fde6  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0x9fdeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9fdf0  ldarg.0
0x9fdf1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fdf6  ldstr    aToolsSystemcus_6// "/tools/systemcustomization/relationship"...
0x9fdfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9fe00  ldarg.0
0x9fe01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe06  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0x9fe0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe10  ldarg.0
0x9fe11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe16  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x9fe1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe20  ldarg.0
0x9fe21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe26  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0x9fe2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe30  ldarg.0
0x9fe31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe36  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x9fe3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe40  ldarg.0
0x9fe41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe46  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x9fe4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe50  ldarg.0
0x9fe51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe56  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0x9fe5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fe60  ldarg.0
0x9fe61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe66  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x9fe6b  ldarg.0
0x9fe6c  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0x9fe71  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9fe76  ldc.i4.0
0x9fe77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9fe7c  ldarg.0
0x9fe7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe82  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x9fe87  ldarg.0
0x9fe88  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0x9fe8d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9fe92  ldc.i4.0
0x9fe93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9fe98  ldarg.0
0x9fe99  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fe9e  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x9fea3  ldarg.0
0x9fea4  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0x9fea9  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9feae  ldc.i4.0
0x9feaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9feb4  ldarg.0
0x9feb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9feba  ldstr    aStaticToolsSys_13// "/_static/tools/systemcustomization/rela"...
0x9febf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9fec4  ldarg.0
0x9fec5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9feca  ldstr    aLocidRelutlCan// "LOCID_RELUTL_CANTDELSYSREL"
0x9fecf  ldarg.0
0x9fed0  ldstr    aRelationshiput// "RelationshipUtil.Messages.CannotDeleteS"...
0x9fed5  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9feda  ldc.i4.0
0x9fedb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9fee0  ldarg.0
0x9fee1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fee6  ldstr    aLocidRelutlCon// "LOCID_RELUTL_CONFIRMDELREL"
0x9feeb  ldarg.0
0x9feec  ldstr    aRelationshiput_0// "RelationshipUtil.Messages.ConfirmRelati"...
0x9fef1  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9fef6  ldc.i4.0
0x9fef7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9fefc  ldarg.0
0x9fefd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff02  ldstr    aLocidRelutlCre// "LOCID_RELUTL_CREATINGREL"
0x9ff07  ldarg.0
0x9ff08  ldstr    aRelationshiput_1// "RelationshipUtil.Messages.CreatingRelat"...
0x9ff0d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9ff12  ldc.i4.0
0x9ff13  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ff18  ldarg.0
0x9ff19  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff1e  ldstr    aLocidRelutlUpd// "LOCID_RELUTL_UPDATINGREL"
0x9ff23  ldarg.0
0x9ff24  ldstr    aRelationshiput_2// "RelationshipUtil.Messages.UpdatingRelat"...
0x9ff29  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9ff2e  ldc.i4.0
0x9ff2f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ff34  ldarg.0
0x9ff35  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff3a  ldstr    aLocidRelutlDel// "LOCID_RELUTL_DELETINGREL"
0x9ff3f  ldarg.0
0x9ff40  ldstr    aRelationshiput_3// "RelationshipUtil.Messages.DeletingRelat"...
0x9ff45  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetSCString(string name)
0x9ff4a  ldc.i4.0
0x9ff4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ff50  ldarg.0
0x9ff51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff56  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0x9ff5b  ldarg.0
0x9ff5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ff61  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x9ff66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ff6b  ldc.i4.0
0x9ff6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ff71  ldarg.0
0x9ff72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff77  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0x9ff7c  ldarg.0
0x9ff7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ff82  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x9ff87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ff8c  ldc.i4.0
0x9ff8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ff92  ldarg.0
0x9ff93  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ff98  ldstr    aStaticToolsSys_14// "/_static/tools/systemcustomization/rela"...
0x9ff9d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ffa2  ldarg.0
0x9ffa3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ffa8  ldstr    aLocidManrelCon// "LOCID_MANREL_CONFIRMHIRTURNOFF"
0x9ffad  ldarg.0
0x9ffae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ffb3  ldstr    aSystemcustomiz_308// "SystemCustomization.ManageRelationshipP"...
0x9ffb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ffbd  ldc.i4.0
0x9ffbe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ffc3  ldarg.0
0x9ffc4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ffc9  ldstr    aLocidManrelCon_0// "LOCID_MANREL_CONFIRMHIRTURNON"
0x9ffce  ldarg.0
0x9ffcf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ffd4  ldstr    aSystemcustomiz// "SystemCustomization.ManageRelationshipP"...
0x9ffd9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ffde  ldc.i4.0
0x9ffdf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ffe4  ldarg.0
0x9ffe5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ffea  ldstr    aBcreate// "_bCreate"
0x9ffef  ldarg.0
0x9fff0  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_mode
0x9fff5  ldc.i4.0
0x9fff6  ceq
0x9fff8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x9fffd  ldarg.0
0x9fffe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0003  ldstr    aBmode// "_bMode"
0xa0008  ldarg.0
0xa0009  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_mode
0xa000e  conv.i8
0xa000f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xa0014  ldarg.0
0xa0015  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa001a  ldstr    aSrelationshipi// "_sRelationshipId"
0xa001f  ldarg.0
0xa0020  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationshipId
0xa0025  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa002a  ldarg.0
0xa002b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0030  ldstr    aBcustom// "_bCustom"
0xa0035  ldarg.0
0xa0036  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa003b  brfalse.s loc_A004A
0xa003d  ldarg.0
0xa003e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa0043  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_IsCustomRelationship()
0xa0048  br.s     loc_A004B
0xa004a  ldc.i4.1
0xa004b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xa0050  ldarg.0
0xa0051  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0056  ldstr    aSentityid// "_sEntityId"
0xa005b  ldarg.0
0xa005c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityMD
0xa0061  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa0066  stloc.0
0xa0067  ldloca.s 0
0xa0069  constrained. [mscorlib]System.Guid
0xa006f  callvirt instance string [mscorlib]System.Object::ToString()
0xa0074  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa0079  ldarg.0
0xa007a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa007f  ldstr    aBmanytomany// "_bManyToMany"
0xa0084  ldarg.0
0xa0085  call     instance bool Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::IsManyToMany()
0xa008a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xa008f  ldarg.0
0xa0090  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0095  ldstr    aDataproviderid// "_dataProviderId"
0xa009a  ldarg.0
0xa009b  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_dataProviderId
0xa00a0  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xa00a5  call     string [mscorlib]System.Convert::ToString(object)
0xa00aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa00af  ldarg.0
0xa00b0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa00b5  ldstr    aEntityrole// "_entityRole"
0xa00ba  ldarg.0
0xa00bb  ldflda   valuetype EntityRole Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRole
0xa00c0  constrained. EntityRole
0xa00c6  callvirt instance string [mscorlib]System.Object::ToString()
0xa00cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa00d0  ldarg.0
0xa00d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa00d6  ldstr    aSentityrole// "_sEntityRole"
0xa00db  ldarg.0
0xa00dc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xa00e1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xa00e6  ldsfld   string PageParameters::entityRole
0xa00eb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa00f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa00f5  ldarg.0
0xa00f6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationship
0xa00fb  brfalse.s loc_A014D
0xa00fd  ldarg.0
0xa00fe  ldarg.0
0xa00ff  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationship
0xa0104  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipId()
0xa0109  stloc.0
0xa010a  ldloca.s 0
0xa010c  constrained. [mscorlib]System.Guid
0xa0112  callvirt instance string [mscorlib]System.Object::ToString()
0xa0117  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationshipId
0xa011c  ldarg.0
0xa011d  ldfld    valuetype EntityRole Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRole
0xa0122  brtrue.s loc_A014D
0xa0124  ldarg.0
0xa0125  ldarg.0
0xa0126  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationship
0xa012b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0xa0130  ldc.i4.0
0xa0131  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0xa0136  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xa013b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataProviderId()
0xa0140  stloc.1
0xa0141  ldloca.s 1
0xa0143  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xa0148  stfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_isReferencingEntityVE
0xa014d  ldarg.0
0xa014e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0153  ldstr    aSentityrelatio// "_sEntityRelationshipId"
0xa0158  ldarg.0
0xa0159  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationshipId
0xa015e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa0163  ldarg.0
0xa0164  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0169  ldstr    aSexistinghiera// "_sExistingHierarchicalRelationship"
0xa016e  ldarg.0
0xa016f  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetEntityHierarchicalRelationship()
0xa0174  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa0179  ldarg.0
0xa017a  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::CreateClientObjectVariables()
0xa017f  ldarg.0
0xa0180  ldstr    aSelreferencede// "selReferencedEntityNameLabel"
0xa0185  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa018a  ldarg.0
0xa018b  ldstr    aSelreferencing// "selReferencingEntityNameLabel"
0xa0190  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa0195  ldarg.0
0xa0196  ldstr    aTxtschemanamel// "txtSchemaNameLabel"
0xa019b  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01a0  ldarg.0
0xa01a1  ldstr    aSelectisvalidf// "selectIsValidForAdvancedFindLabel"
0xa01a6  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01ab  ldarg.0
0xa01ac  ldstr    aSelectishierar// "selectIsHierarchicalLabel"
0xa01b1  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01b6  ldarg.0
0xa01b7  ldstr    aTxtintersecten// "txtIntersectEntityNameLabel"
0xa01bc  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01c1  ldarg.0
0xa01c2  ldstr    aTxtreferencedi// "txtReferencedInstanceNameLabel"
0xa01c7  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01cc  ldarg.0
0xa01cd  ldstr    aSelreqlevellab// "selReqLevelLabel"
0xa01d2  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01d7  ldarg.0
0xa01d8  ldstr    aTxtattributesc// "txtAttributeSchemaNameLabel"
0xa01dd  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01e2  ldarg.0
0xa01e3  ldstr    aTxtattributeex// "txtAttributeExternalNameLabel"
0xa01e8  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01ed  ldarg.0
0xa01ee  ldstr    aTxtcustomlabel// "txtCustomLabelLabel"
0xa01f3  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa01f8  ldarg.0
0xa01f9  ldstr    aSeltypelabel// "selTypeLabel"
0xa01fe  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa0203  ldarg.0
0xa0204  ldstr    aSelcascadeassi// "selCascadeAssignLabel"
0xa0209  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddAutoToolTipControl(string elementId)
0xa020e  ldarg.0
  ... truncated ...
```
