# Microsoft.Crm.Web.Tools.Solution.AreaPage::AddButtonItem

- ea: `0x53080`
- end: `0x532d5`
- name: `Microsoft.Crm.Web.Tools.Solution.AreaPage::AddButtonItem`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x52be0`

## callees

- `0x53080`
- `0x532e0`

## string_xrefs

- `0x53222`: `Mscrm.SolutionComponentList.add`
- `0x53102`: `OpenPluginAssembly()`
- `0x53125`: `OpenSdkMessageProcessingStep()`
- `0x53144`: `Solution.Editor.UIGuidance.ServiceEndpoint.Title`
- `0x53154`: `OpenServiceEndpoint()`

## pseudocode

```c

```

## disassembly

```asm
0x53080  ldarg.0
0x53081  ldarg.2
0x53082  ldarg.3
0x53083  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::EnableActionType(int32 typeCode, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x53088  brtrue.s loc_5308B
0x5308a  ret
0x5308b  ldarg.1
0x5308c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x53091  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x53096  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x5309b  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x530a0  stloc.0
0x530a1  ldarg.3
0x530a2  brtrue   loc_531BA
0x530a7  ldarg.2
0x530a8  ldc.i4   0x11FD
0x530ad  beq.s    loc_530C2
0x530af  ldarg.2
0x530b0  ldc.i4   0x1200
0x530b5  beq.s    loc_530C2
0x530b7  ldarg.2
0x530b8  ldc.i4   0x120A
0x530bd  bne.un   loc_531BA
0x530c2  ldarg.2
0x530c3  ldc.i4   0x11FD
0x530c8  beq.s    loc_530DF
0x530ca  ldarg.2
0x530cb  ldc.i4   0x1200
0x530d0  beq.s    loc_5310E
0x530d2  ldarg.2
0x530d3  ldc.i4   0x120A
0x530d8  beq.s    loc_5313D
0x530da  br       loc_5316A
0x530df  ldloc.0
0x530e0  ldarg.0
0x530e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x530e6  ldstr    aSolutionEditor// "Solution.Editor.UIGuidance.Assembly.Tit"...
0x530eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x530f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x530f5  ldloc.0
0x530f6  ldloc.0
0x530f7  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x530fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x53101  ldloc.0
0x53102  ldstr    aOpenpluginasse// "OpenPluginAssembly()"
0x53107  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5310c  br.s     loc_5316A
0x5310e  ldloc.0
0x5310f  ldarg.0
0x53110  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x53115  ldstr    aSolutionEditor_0// "Solution.Editor.UIGuidance.ProcessingSt"...
0x5311a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5311f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x53124  ldloc.0
0x53125  ldstr    aOpensdkmessage// "OpenSdkMessageProcessingStep()"
0x5312a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5312f  ldloc.0
0x53130  ldloc.0
0x53131  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x53136  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x5313b  br.s     loc_5316A
0x5313d  ldloc.0
0x5313e  ldarg.0
0x5313f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x53144  ldstr    aSolutionEditor_1// "Solution.Editor.UIGuidance.ServiceEndpo"...
0x53149  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5314e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x53153  ldloc.0
0x53154  ldstr    aOpenserviceend// "OpenServiceEndpoint()"
0x53159  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5315e  ldloc.0
0x5315f  ldloc.0
0x53160  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x53165  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x5316a  ldloc.0
0x5316b  ldarg.2
0x5316c  ldc.i4.0
0x5316d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x53172  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53177  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5317c  ldloc.0
0x5317d  ldstr    aMbadd// "_MBAdd"
0x53182  ldtoken  Microsoft.Crm.Web.Tools.Solution.ActionType
0x53187  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5318c  ldarg.3
0x5318d  box      Microsoft.Crm.Web.Tools.Solution.ActionType
0x53192  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x53197  ldstr    asc_12B0EE// "_"
0x5319c  ldarga.s 2
0x5319e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x531a3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x531a8  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x531ad  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x531b2  ldloc.0
0x531b3  ldc.i4.1
0x531b4  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x531b9  ret
0x531ba  ldloca.s 1
0x531bc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x531c2  ldarg.0
0x531c3  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x531c8  brfalse.s loc_531DC
0x531ca  ldarg.2
0x531cb  ldc.i4.1
0x531cc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.ComponentTypeSubcode::FormatAsString(int32, int32)
0x531d1  stloc.2
0x531d2  ldloca.s 1
0x531d4  ldc.i4.8
0x531d5  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x531da  br.s     loc_531E9
0x531dc  ldarga.s 2
0x531de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x531e3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x531e8  stloc.2
0x531e9  ldloc.0
0x531ea  ldarg.0
0x531eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x531f0  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x531f5  ldtoken  Microsoft.Crm.Web.Tools.Solution.ActionType
0x531fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x531ff  ldarg.3
0x53200  box      Microsoft.Crm.Web.Tools.Solution.ActionType
0x53205  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x5320a  call     string [mscorlib]System.String::Concat(string, string)
0x5320f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53214  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x53219  ldloc.0
0x5321a  ldc.i4.5
0x5321b  newarr   [mscorlib]System.String
0x53220  dup
0x53221  ldc.i4.0
0x53222  ldstr    aMscrmSolutionc_14// "Mscrm.SolutionComponentList.add"
0x53227  stelem.ref
0x53228  dup
0x53229  ldc.i4.1
0x5322a  ldtoken  Microsoft.Crm.Web.Tools.Solution.ActionType
0x5322f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53234  ldarg.3
0x53235  box      Microsoft.Crm.Web.Tools.Solution.ActionType
0x5323a  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x5323f  stelem.ref
0x53240  dup
0x53241  ldc.i4.2
0x53242  ldstr    asc_15D042// "('"
0x53247  stelem.ref
0x53248  dup
0x53249  ldc.i4.3
0x5324a  ldloc.2
0x5324b  stelem.ref
0x5324c  dup
0x5324d  ldc.i4.4
0x5324e  ldstr    asc_142D92// "');"
0x53253  stelem.ref
0x53254  call     string [mscorlib]System.String::Concat(string[])
0x53259  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5325e  ldloc.0
0x5325f  ldarg.2
0x53260  ldc.i4.0
0x53261  ldc.i4.1
0x53262  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x53267  ldloc.1
0x53268  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Nullable`1<int32>)
0x5326d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x53272  ldloc.0
0x53273  ldarg.0
0x53274  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x53279  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x5327e  ldtoken  Microsoft.Crm.Web.Tools.Solution.ActionType
0x53283  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53288  ldarg.3
0x53289  box      Microsoft.Crm.Web.Tools.Solution.ActionType
0x5328e  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x53293  call     string [mscorlib]System.String::Concat(string, string)
0x53298  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5329d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x532a2  ldloc.0
0x532a3  ldstr    aMbadd// "_MBAdd"
0x532a8  ldtoken  Microsoft.Crm.Web.Tools.Solution.ActionType
0x532ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x532b2  ldarg.3
0x532b3  box      Microsoft.Crm.Web.Tools.Solution.ActionType
0x532b8  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x532bd  ldstr    asc_12B0EE// "_"
0x532c2  ldloc.2
0x532c3  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x532c8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x532cd  ldloc.0
0x532ce  ldc.i4.1
0x532cf  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x532d4  ret
```
