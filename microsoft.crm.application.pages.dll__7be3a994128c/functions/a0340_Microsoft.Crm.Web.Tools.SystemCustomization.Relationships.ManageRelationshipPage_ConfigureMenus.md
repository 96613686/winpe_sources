# Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::ConfigureMenus

- ea: `0xa0340`
- end: `0xa0525`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::ConfigureMenus`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xa0340`
- `0xa2030`
- `0xa2130`

## string_xrefs

- `0xa0371`: `CreateMode.Title`
- `0xa0393`: `CreateMode.Title.Line2`
- `0xa03c9`: `UpdateMode.Title`
- `0xa04ae`: `UpdateMode.Title`
- `0xa03f6`: `UpdateMode.Title.Line2`
- `0xa04c7`: `UpdateMode.Title.Line2`

## pseudocode

```c

```

## disassembly

```asm
0xa0340  ldarg.0
0xa0341  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xa0346  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar
0xa034b  stloc.0
0xa034c  ldarg.0
0xa034d  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_mode
0xa0352  stloc.1
0xa0353  ldloc.1
0xa0354  switch   loc_A036A, loc_A03A7, loc_A03A7
0xa0365  br       loc_A04DD
0xa036a  ldarg.0
0xa036b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa0370  ldarg.0
0xa0371  ldstr    aCreatemodeTitl// "CreateMode.Title"
0xa0376  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa037b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xa0380  ldloc.0
0xa0381  ldarg.0
0xa0382  ldstr    aTitleLine1// "Title.Line1"
0xa0387  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa038c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleType(string)
0xa0391  ldloc.0
0xa0392  ldarg.0
0xa0393  ldstr    aCreatemodeTitl_0// "CreateMode.Title.Line2"
0xa0398  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa039d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleName(string)
0xa03a2  br       loc_A04DD
0xa03a7  ldloc.0
0xa03a8  ldarg.0
0xa03a9  ldstr    aTitleLine1// "Title.Line1"
0xa03ae  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa03b3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleType(string)
0xa03b8  ldarg.0
0xa03b9  ldfld    valuetype EntityRole Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRole
0xa03be  ldc.i4.2
0xa03bf  beq.s    loc_A0436
0xa03c1  ldarg.0
0xa03c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa03c7  ldarg.0
0xa03c8  ldarg.0
0xa03c9  ldstr    aUpdatemodeTitl// "UpdateMode.Title"
0xa03ce  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa03d3  ldarg.0
0xa03d4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa03d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0xa03de  ldarg.0
0xa03df  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa03e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xa03e9  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddEntityDisplayNames(string format, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencedEntityMD, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencingEntityMD)
0xa03ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xa03f3  ldloc.0
0xa03f4  ldarg.0
0xa03f5  ldarg.0
0xa03f6  ldstr    aUpdatemodeTitl_0// "UpdateMode.Title.Line2"
0xa03fb  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa0400  ldarg.0
0xa0401  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa0406  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0xa040b  ldarg.0
0xa040c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_relationship
0xa0411  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xa0416  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddEntityDisplayNames(string format, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencedEntityMD, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencingEntityMD)
0xa041b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleName(string)
0xa0420  ldarg.0
0xa0421  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_powerAppsNavBar
0xa0426  ldloc.0
0xa0427  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::get_TitleName()
0xa042c  stfld    string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PowerAppsNavBar::ComponentName
0xa0431  br       loc_A04DD
0xa0436  ldnull
0xa0437  stloc.2
0xa0438  ldnull
0xa0439  stloc.3
0xa043a  ldarg.0
0xa043b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityRelationship
0xa0440  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRoles()
0xa0445  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0xa044a  stloc.s  4
0xa044c  br.s     loc_A048F
0xa044e  ldloc.s  4
0xa0450  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0xa0455  stloc.s  5
0xa0457  ldloc.s  5
0xa0459  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_RelationshipRoleType()
0xa045e  ldc.i4.2
0xa045f  bne.un.s loc_A048F
0xa0461  ldloc.s  5
0xa0463  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0xa0468  ldarg.0
0xa0469  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::_entityMD
0xa046e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa0473  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa0478  brfalse.s loc_A0487
0xa047a  ldloc.2
0xa047b  brtrue.s loc_A0487
0xa047d  ldloc.s  5
0xa047f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_Entity()
0xa0484  stloc.2
0xa0485  br.s     loc_A048F
0xa0487  ldloc.s  5
0xa0489  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_Entity()
0xa048e  stloc.3
0xa048f  ldloc.s  4
0xa0491  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa0496  brtrue.s loc_A044E
0xa0498  leave.s  loc_A04A6
0xa049a  ldloc.s  4
0xa049c  brfalse.s loc_A04A5
0xa049e  ldloc.s  4
0xa04a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa04a5  endfinally
0xa04a6  ldarg.0
0xa04a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa04ac  ldarg.0
0xa04ad  ldarg.0
0xa04ae  ldstr    aUpdatemodeTitl// "UpdateMode.Title"
0xa04b3  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa04b8  ldloc.2
0xa04b9  ldloc.3
0xa04ba  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddEntityDisplayNames(string format, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencedEntityMD, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencingEntityMD)
0xa04bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xa04c4  ldloc.0
0xa04c5  ldarg.0
0xa04c6  ldarg.0
0xa04c7  ldstr    aUpdatemodeTitl_0// "UpdateMode.Title.Line2"
0xa04cc  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::GetString(string name)
0xa04d1  ldloc.2
0xa04d2  ldloc.3
0xa04d3  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::AddEntityDisplayNames(string format, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencedEntityMD, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata referencingEntityMD)
0xa04d8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_TitleName(string)
0xa04dd  ldloc.0
0xa04de  ldc.i4   0x264D
0xa04e3  ldc.i4.7
0xa04e4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa04e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa04ee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGenericMenuBar::set_CustomIconPath(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa04f3  ldloc.0
0xa04f4  ldc.i4.1
0xa04f5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_ShowToolBar(bool)
0xa04fa  ldloc.0
0xa04fb  ldarg.0
0xa04fc  ldftn    instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::ToolBarReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0xa0502  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0xa0507  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnToolBarReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0xa050c  ldloc.0
0xa050d  ldarg.0
0xa050e  ldftn    instance void Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.ManageRelationshipPage::MenuReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0xa0514  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0xa0519  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnMenuReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0xa051e  ldloc.0
0xa051f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::Execute()
0xa0524  ret
```
