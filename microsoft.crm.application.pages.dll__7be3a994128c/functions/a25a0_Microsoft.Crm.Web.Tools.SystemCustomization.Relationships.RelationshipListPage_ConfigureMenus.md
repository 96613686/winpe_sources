# Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::ConfigureMenus

- ea: `0xa25a0`
- end: `0xa2adc`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::ConfigureMenus`
- size: `1340`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0xa25a0`
- `0xa2d70`

## string_xrefs

- `0xa2813`: `/_imgs/ico_16_delete.gif`
- `0xa286f`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xa28aa`: `/_imgs/solution/removecomponent.gif`
- `0xa28f5`: `MenuItem_Label_AddSubcomponents`
- `0xa2992`: `MenuItem_Label_AddSubcomponents`
- `0xa2907`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xa2982`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xa299c`: `btnAddSubcomponents`
- `0xa2865`: `MenuItem_Label_RemoveComponent`
- `0xa28bf`: `btnRemoveComponent`
- `0xa281e`: `Buttons.Delete.Tooltip`
- `0xa2828`: `btnDeleteViews`
- `0xa28b5`: `Buttons.RemoveComponent.Tooltip`
- `0xa262f`: `Buttons.CreateReferenced.Title`
- `0xa2639`: `createRelationshipAction(0);`
- `0xa265e`: `Buttons.CreateReferenced.Tooltip`
- `0xa2668`: `btnCreateReferencedRelationship`
- `0xa26ac`: `Buttons.CreateReferencing.Title`
- `0xa26b6`: `createRelationshipAction(1);`
- `0xa26db`: `Buttons.CreateReferencing.Tooltip`
- `0xa26e5`: `btnCreateReferencingRelationship`
- `0xa272b`: `Buttons.CreateManyToMany.Title`
- `0xa275a`: `Buttons.CreateManyToMany.Title`
- `0xa2735`: `createRelationshipAction(2);`
- `0xa2764`: `btnCreateManyToManyRelationship`
- `0xa27f9`: `dispatchAction(getSelectedRelationshipOid(), _oConst.sDeleteAction);`
- `0xa2a4c`: `dispatchAction(getSelectedRelationshipOid(), _oConst.sUpdateAction);`

## pseudocode

```c

```

## disassembly

```asm
0xa25a0  ldarg.0
0xa25a1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa25a6  ldnull
0xa25a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0xa25ac  ldarg.0
0xa25ad  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa25b2  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0xa25b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0xa25bc  ldarg.0
0xa25bd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xa25c2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xa25c7  brtrue.s loc_A25D6
0xa25c9  ldarg.0
0xa25ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xa25cf  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xa25d4  brfalse.s loc_A25E2
0xa25d6  ldarg.0
0xa25d7  ldstr    a1// "1"
0xa25dc  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::disableDoubleClick
0xa25e1  ret
0xa25e2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateRelationship()
0xa25e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa25ec  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa25f1  brfalse  loc_A276F
0xa25f6  ldarg.0
0xa25f7  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa25fc  ldc.i4   0x100
0xa2601  bne.un.s loc_A2673
0xa2603  ldarg.0
0xa2604  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa2609  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa260e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeReferencedEntity(string)
0xa2613  brfalse.s loc_A2673
0xa2615  ldarg.0
0xa2616  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa261b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa2620  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::GetAllowedReferencingEntities(valuetype [mscorlib]System.Guid)
0xa2625  ldlen
0xa2626  brfalse.s loc_A2673
0xa2628  ldarg.0
0xa2629  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa262e  ldarg.0
0xa262f  ldstr    aButtonsCreater// "Buttons.CreateReferenced.Title"
0xa2634  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa2639  ldstr    aCreaterelation// "createRelationshipAction(0);"
0xa263e  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa2643  ldc.i4.1
0xa2644  newarr   [mscorlib]System.Char
0xa2649  dup
0xa264a  ldc.i4.0
0xa264b  ldc.i4.s 0x2F
0xa264d  stelem.i2
0xa264e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa2653  ldstr    aImgsIco16Syste// "/_imgs/ico_16_systemrelationship.gif"
0xa2658  call     string [mscorlib]System.String::Concat(string, string)
0xa265d  ldarg.0
0xa265e  ldstr    aButtonsCreater_0// "Buttons.CreateReferenced.Tooltip"
0xa2663  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa2668  ldstr    aBtncreaterefer// "btnCreateReferencedRelationship"
0xa266d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa2672  pop
0xa2673  ldarg.0
0xa2674  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa2679  ldc.i4   0x200
0xa267e  bne.un.s loc_A26F0
0xa2680  ldarg.0
0xa2681  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa2686  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa268b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeReferencingEntity(string)
0xa2690  brfalse.s loc_A26F0
0xa2692  ldarg.0
0xa2693  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa2698  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa269d  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::GetAllowedReferencedEntities(valuetype [mscorlib]System.Guid)
0xa26a2  ldlen
0xa26a3  brfalse.s loc_A26F0
0xa26a5  ldarg.0
0xa26a6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa26ab  ldarg.0
0xa26ac  ldstr    aButtonsCreater_1// "Buttons.CreateReferencing.Title"
0xa26b1  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa26b6  ldstr    aCreaterelation_0// "createRelationshipAction(1);"
0xa26bb  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa26c0  ldc.i4.1
0xa26c1  newarr   [mscorlib]System.Char
0xa26c6  dup
0xa26c7  ldc.i4.0
0xa26c8  ldc.i4.s 0x2F
0xa26ca  stelem.i2
0xa26cb  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa26d0  ldstr    aImgsIco16Relat// "/_imgs/ico_16_relationshipsn21.gif"
0xa26d5  call     string [mscorlib]System.String::Concat(string, string)
0xa26da  ldarg.0
0xa26db  ldstr    aButtonsCreater_2// "Buttons.CreateReferencing.Tooltip"
0xa26e0  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa26e5  ldstr    aBtncreaterefer_0// "btnCreateReferencingRelationship"
0xa26ea  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa26ef  pop
0xa26f0  ldarg.0
0xa26f1  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa26f6  ldc.i4   0x400
0xa26fb  bne.un.s loc_A276F
0xa26fd  ldarg.0
0xa26fe  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa2703  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa2708  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeAssociationEntity(string)
0xa270d  brfalse.s loc_A276F
0xa270f  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::GetAllowedAssociationEntities()
0xa2714  ldlen
0xa2715  brfalse.s loc_A276F
0xa2717  ldarg.0
0xa2718  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa271d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::IsEntityTaskOrPhoneCall(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0xa2722  brtrue.s loc_A276F
0xa2724  ldarg.0
0xa2725  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa272a  ldarg.0
0xa272b  ldstr    aButtonsCreatem// "Buttons.CreateManyToMany.Title"
0xa2730  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa2735  ldstr    aCreaterelation_1// "createRelationshipAction(2);"
0xa273a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa273f  ldc.i4.1
0xa2740  newarr   [mscorlib]System.Char
0xa2745  dup
0xa2746  ldc.i4.0
0xa2747  ldc.i4.s 0x2F
0xa2749  stelem.i2
0xa274a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa274f  ldstr    aImgsIco16Relat_0// "/_imgs/ico_16_relationshipsn2n.gif"
0xa2754  call     string [mscorlib]System.String::Concat(string, string)
0xa2759  ldarg.0
0xa275a  ldstr    aButtonsCreatem// "Buttons.CreateManyToMany.Title"
0xa275f  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa2764  ldstr    aBtncreatemanyt// "btnCreateManyToManyRelationship"
0xa2769  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa276e  pop
0xa276f  ldarg.0
0xa2770  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa2775  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xa277a  ldarg.0
0xa277b  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa2780  ldc.i4   0x200
0xa2785  bne.un.s loc_A2799
0xa2787  ldarg.0
0xa2788  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa278d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa2792  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeReferencingEntity(string)
0xa2797  brtrue.s loc_A27DA
0xa2799  ldarg.0
0xa279a  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa279f  ldc.i4   0x100
0xa27a4  bne.un.s loc_A27B8
0xa27a6  ldarg.0
0xa27a7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa27ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa27b1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeReferencedEntity(string)
0xa27b6  brtrue.s loc_A27DA
0xa27b8  ldarg.0
0xa27b9  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa27be  ldc.i4   0x400
0xa27c3  bne.un.s loc_A27D7
0xa27c5  ldarg.0
0xa27c6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa27cb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa27d0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeAssociationEntity(string)
0xa27d5  br.s     loc_A27DB
0xa27d7  ldc.i4.0
0xa27d8  br.s     loc_A27DB
0xa27da  ldc.i4.1
0xa27db  brfalse.s loc_A2833
0xa27dd  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteRelationship()
0xa27e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa27e7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa27ec  brfalse.s loc_A2833
0xa27ee  ldarg.0
0xa27ef  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa27f4  ldsfld   string [mscorlib]System.String::Empty
0xa27f9  ldstr    aDispatchaction_11// "dispatchAction(getSelectedRelationshipO"...
0xa27fe  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa2803  ldc.i4.1
0xa2804  newarr   [mscorlib]System.Char
0xa2809  dup
0xa280a  ldc.i4.0
0xa280b  ldc.i4.s 0x2F
0xa280d  stelem.i2
0xa280e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa2813  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xa2818  call     string [mscorlib]System.String::Concat(string, string)
0xa281d  ldarg.0
0xa281e  ldstr    aButtonsDeleteT// "Buttons.Delete.Tooltip"
0xa2823  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa2828  ldstr    aBtndeleteviews// "btnDeleteViews"
0xa282d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa2832  pop
0xa2833  ldarg.0
0xa2834  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xa2839  ldarg.0
0xa283a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa283f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa2844  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xa2849  brfalse  loc_A29A7
0xa284e  ldarg.0
0xa284f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa2854  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xa2859  ldarg.0
0xa285a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa285f  ldarg.0
0xa2860  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa2865  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xa286a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa286f  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xa2874  ldc.i4   0x264D
0xa2879  stloc.1
0xa287a  ldloca.s 1
0xa287c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa2881  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa2886  callvirt instance string [mscorlib]System.Object::ToString()
0xa288b  ldstr    asc_14E862// ")"
0xa2890  call     string [mscorlib]System.String::Concat(string, string, string)
0xa2895  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa289a  ldc.i4.1
0xa289b  newarr   [mscorlib]System.Char
0xa28a0  dup
0xa28a1  ldc.i4.0
0xa28a2  ldc.i4.s 0x2F
0xa28a4  stelem.i2
0xa28a5  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa28aa  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xa28af  call     string [mscorlib]System.String::Concat(string, string)
0xa28b4  ldarg.0
0xa28b5  ldstr    aButtonsRemovec// "Buttons.RemoveComponent.Tooltip"
0xa28ba  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::GetString(string name)
0xa28bf  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xa28c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa28c9  pop
0xa28ca  ldarg.0
0xa28cb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa28d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xa28d5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xa28da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa28df  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa28e4  brfalse  loc_A29A7
0xa28e9  ldarg.0
0xa28ea  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::menuBar
0xa28ef  ldarg.0
0xa28f0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa28f5  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xa28fa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa28ff  ldc.i4.7
0xa2900  newarr   [mscorlib]System.Object
0xa2905  dup
0xa2906  ldc.i4.0
0xa2907  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xa290c  stelem.ref
0xa290d  dup
0xa290e  ldc.i4.1
0xa290f  ldc.i4   0x2649
0xa2914  stloc.1
0xa2915  ldloca.s 1
0xa2917  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa291c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa2921  callvirt instance string [mscorlib]System.Object::ToString()
0xa2926  stelem.ref
0xa2927  dup
0xa2928  ldc.i4.2
0xa2929  ldstr    asc_15BF70// ",'"
0xa292e  stelem.ref
0xa292f  dup
0xa2930  ldc.i4.3
0xa2931  ldarg.0
0xa2932  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_entityMD
0xa2937  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa293c  box      [mscorlib]System.Guid
0xa2941  stelem.ref
0xa2942  dup
0xa2943  ldc.i4.4
0xa2944  ldstr    asc_14EC6A// "','"
0xa2949  stelem.ref
0xa294a  dup
0xa294b  ldc.i4.5
0xa294c  ldarg.0
0xa294d  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.RelationshipGridDataProviderFilters Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.RelationshipListPage::_relationshipRole
0xa2952  stloc.1
0xa2953  ldloca.s 1
0xa2955  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa295a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa295f  stelem.ref
0xa2960  dup
0xa2961  ldc.i4.6
0xa2962  ldstr    asc_1235BC// "')"
0xa2967  stelem.ref
0xa2968  call     string [mscorlib]System.String::Concat(object[])
0xa296d  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa2972  ldc.i4.1
0xa2973  newarr   [mscorlib]System.Char
0xa2978  dup
0xa2979  ldc.i4.0
0xa297a  ldc.i4.s 0x2F
0xa297c  stelem.i2
0xa297d  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
  ... truncated ...
```
