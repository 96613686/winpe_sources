# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleContextualActions

- ea: `0xc7d0`
- end: `0xc90d`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleContextualActions`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0xbee0`

## callees

- `0xbca0`
- `0xbce0`
- `0xc1b0`
- `0xc620`
- `0xc7d0`
- `0xc910`
- `0xc980`
- `0xca90`
- `0xcd00`
- `0xcee0`
- `0xd0a0`
- `0xd290`
- `0xe480`
- `0x179b0`
- `0x1cb30`
- `0x1ce20`
- `0x1e720`
- `0x1e780`
- `0x1e7a0`
- `0x1e7c0`

## string_xrefs

- `0xc8ba`: `MoveUp`
- `0xc8c6`: `MoveDown`

## pseudocode

```c

```

## disassembly

```asm
0xc7d0  ldarg.0
0xc7d1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xc7d6  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsGridEnabled()
0xc7db  brfalse  loc_C90C
0xc7e0  ldarg.0
0xc7e1  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xc7e6  brtrue.s loc_C7F0
0xc7e8  ldarg.0
0xc7e9  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::InlineEditEnabledForLeadOrOpportunity()
0xc7ee  brtrue.s loc_C7F8
0xc7f0  ldarg.0
0xc7f1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRecordAssociatedSalesTeamGrid()
0xc7f6  brfalse.s loc_C814
0xc7f8  ldarg.0
0xc7f9  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasAddPrivileges()
0xc7fe  brfalse  loc_C89F
0xc803  ldarg.0
0xc804  ldarg.1
0xc805  ldstr    aQuickadd// "QuickAdd"
0xc80a  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string addActionType)
0xc80f  br       loc_C89F
0xc814  ldarg.0
0xc815  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsEntityBound()
0xc81a  brfalse.s loc_C855
0xc81c  ldarg.0
0xc81d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::GetFormDescriptor()
0xc822  brfalse.s loc_C855
0xc824  ldarg.0
0xc825  callvirt instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::get_CurrentEntityName()
0xc82a  ldstr    aList// "list"
0xc82f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc834  brfalse.s loc_C855
0xc836  ldarg.0
0xc837  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsMembersAccountSubGrid()
0xc83c  brtrue.s loc_C84E
0xc83e  ldarg.0
0xc83f  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsMembersContactSubGrid()
0xc844  brtrue.s loc_C84E
0xc846  ldarg.0
0xc847  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsMembersLeadSubGrid()
0xc84c  brfalse.s loc_C855
0xc84e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xc853  brfalse.s loc_C89F
0xc855  ldc.i4.1
0xc856  stloc.0
0xc857  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc85c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc861  brfalse.s loc_C888
0xc863  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc868  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc86d  ldarg.0
0xc86e  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc873  ldc.i4.1
0xc874  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc879  stloc.1
0xc87a  ldloc.1
0xc87b  brfalse.s loc_C888
0xc87d  ldloc.1
0xc87e  ldc.i4.8
0xc87f  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.MobileUtility::HasMobileAccessLevel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MobileAccessLevels)
0xc884  brtrue.s loc_C888
0xc886  ldc.i4.0
0xc887  stloc.0
0xc888  ldloc.0
0xc889  brfalse.s loc_C89F
0xc88b  ldarg.0
0xc88c  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsConnectionsSubGridForIncident()
0xc891  brtrue.s loc_C89F
0xc893  ldarg.0
0xc894  ldarg.1
0xc895  ldsfld   string [mscorlib]System.String::Empty
0xc89a  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string addActionType)
0xc89f  ldarg.0
0xc8a0  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsEntityBound()
0xc8a5  brtrue.s loc_C8A8
0xc8a7  ret
0xc8a8  ldarg.0
0xc8a9  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xc8ae  brtrue.s loc_C90C
0xc8b0  ldarg.0
0xc8b1  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsMoveUpAndDownEnabled()
0xc8b6  brfalse.s loc_C8D0
0xc8b8  ldarg.0
0xc8b9  ldarg.1
0xc8ba  ldstr    aMoveup// "MoveUp"
0xc8bf  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::MoveUpImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string upActionType)
0xc8c4  ldarg.0
0xc8c5  ldarg.1
0xc8c6  ldstr    aMovedown// "MoveDown"
0xc8cb  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::MoveDownImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string downActionType)
0xc8d0  ldarg.0
0xc8d1  callvirt instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::get_CurrentEntityName()
0xc8d6  ldstr    aSalesorder// "salesorder"
0xc8db  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc8e0  brtrue.s loc_C8F4
0xc8e2  ldarg.0
0xc8e3  callvirt instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::get_CurrentEntityName()
0xc8e8  ldstr    aInvoice// "invoice"
0xc8ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc8f2  brfalse.s loc_C90C
0xc8f4  ldarg.0
0xc8f5  ldarg.1
0xc8f6  ldstr    aLockprice// "LockPrice"
0xc8fb  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::LockImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string lockActionType)
0xc900  ldarg.0
0xc901  ldarg.1
0xc902  ldstr    aUnlockprice// "UnlockPrice"
0xc907  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UnlockImageButton(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer, string unlockActionType)
0xc90c  ret
```
