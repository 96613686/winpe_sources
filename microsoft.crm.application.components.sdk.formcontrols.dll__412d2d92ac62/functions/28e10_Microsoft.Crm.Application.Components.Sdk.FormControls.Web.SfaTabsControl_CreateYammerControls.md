# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateYammerControls

- ea: `0x28e10`
- end: `0x29033`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateYammerControls`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x28820`

## callees

- `0x17930`
- `0x19100`
- `0x19120`
- `0x19130`
- `0x196e0`
- `0x19700`
- `0x28640`
- `0x28800`
- `0x28e10`
- `0x290e0`
- `0x29e70`
- `0x29e90`
- `0x29eb0`
- `0x29ed0`
- `0x29f00`
- `0x29f60`

## string_xrefs

- `0x28e9a`: `CreateYammerControls`
- `0x28ee0`: `YammerConfigured`
- `0x28f79`: `SFATabsControl.SystemPosts`
- `0x29017`: `SFATabsControl.SystemPosts`

## pseudocode

```c

```

## disassembly

```asm
0x28e10  ldarg.0
0x28e11  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsRefreshForm()
0x28e16  brtrue.s loc_28E19
0x28e18  ret
0x28e19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28e1e  call     class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x28e23  stloc.0
0x28e24  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::.ctor()
0x28e29  dup
0x28e2a  ldstr    aActivityfeedsc// "activityfeedscontrol_"
0x28e2f  ldarg.0
0x28e30  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28e35  call     string [mscorlib]System.String::Concat(string, string)
0x28e3a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x28e3f  dup
0x28e40  ldstr    aActivityfeedst// "ActivityFeedsTab"
0x28e45  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::set_TabId(string value)
0x28e4a  dup
0x28e4b  ldarg.0
0x28e4c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28e51  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::set_MasterComponentId(string value)
0x28e56  dup
0x28e57  ldarg.0
0x28e58  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28e5d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::set_IsControlReadOnly(bool value)
0x28e62  dup
0x28e63  ldc.i4.0
0x28e64  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::set_LoadWallOnInit(bool value)
0x28e69  stloc.1
0x28e6a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28e6f  ldarg.1
0x28e70  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x28e75  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Utility.ActivityFeedsStateForEntity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.ActivityFeedUtility::GetActivityFeedsStateForEntity(valuetype [mscorlib]System.Guid, string)
0x28e7a  stloc.2
0x28e7b  ldloc.2
0x28e7c  ldfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Utility.ActivityFeedsStateForEntity::IsConfigured
0x28e81  brfalse.s loc_28E8E
0x28e83  ldloc.2
0x28e84  ldfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Utility.ActivityFeedsStateForEntity::IsWallEnabled
0x28e89  ldc.i4.0
0x28e8a  ceq
0x28e8c  br.s     loc_28E8F
0x28e8e  ldc.i4.1
0x28e8f  stloc.3
0x28e90  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x28e95  ldstr    aSfatabsInitial// "SFATabs.Initialization"
0x28e9a  ldstr    aCreateyammerco// "CreateYammerControls"
0x28e9f  ldnull
0x28ea0  ldloca.s 4
0x28ea2  initobj  [mscorlib]System.DateTime
0x28ea8  ldloc.s  4
0x28eaa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x28eaf  dup
0x28eb0  ldstr    aYammerandactiv// "YammerAndActivityFeedsHidden"
0x28eb5  ldloc.3
0x28eb6  box      [mscorlib]System.Boolean
0x28ebb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28ec0  dup
0x28ec1  ldstr    aIpaddevice// "iPadDevice"
0x28ec6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x28ecb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x28ed0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIPadDevice(class [System.Web]System.Web.HttpRequest)
0x28ed5  box      [mscorlib]System.Boolean
0x28eda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28edf  dup
0x28ee0  ldstr    aYammerconfigur// "YammerConfigured"
0x28ee5  ldloc.0
0x28ee6  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x28eeb  box      [mscorlib]System.Boolean
0x28ef0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28ef5  dup
0x28ef6  ldstr    aForm// "form"
0x28efb  ldarg.0
0x28efc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28f01  brfalse.s loc_28F10
0x28f03  ldarg.0
0x28f04  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28f09  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28f0e  br.s     loc_28F11
0x28f10  ldnull
0x28f11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28f16  dup
0x28f17  ldstr    aEntity_0// "entity"
0x28f1c  ldarg.0
0x28f1d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28f22  brfalse.s loc_28F31
0x28f24  ldarg.0
0x28f25  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28f2a  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityLogicalName()
0x28f2f  br.s     loc_28F32
0x28f31  ldnull
0x28f32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28f37  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, string, string, valuetype [mscorlib]System.DateTime, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x28f3c  pop
0x28f3d  ldloc.0
0x28f3e  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x28f43  brfalse.s loc_28F95
0x28f45  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x28f4a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x28f4f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIPadDevice(class [System.Web]System.Web.HttpRequest)
0x28f54  brfalse.s loc_28F95
0x28f56  ldarg.0
0x28f57  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28f5c  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28f61  dup
0x28f62  ldstr    aActivityfeedss// "ActivityFeedsSystemTab"
0x28f67  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28f6c  dup
0x28f6d  ldloc.1
0x28f6e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28f73  dup
0x28f74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28f79  ldstr    aSfatabscontrol_0// "SFATabsControl.SystemPosts"
0x28f7e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28f83  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28f88  dup
0x28f89  ldloc.3
0x28f8a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Hidden(bool value)
0x28f8f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28f94  ret
0x28f95  ldarg.0
0x28f96  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28f9b  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28fa0  dup
0x28fa1  ldstr    aActivityfeedst// "ActivityFeedsTab"
0x28fa6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28fab  dup
0x28fac  ldloc.1
0x28fad  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28fb2  dup
0x28fb3  ldloc.0
0x28fb4  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x28fb9  brtrue.s loc_28FC8
0x28fbb  ldarg.0
0x28fbc  ldstr    aPost// "post"
0x28fc1  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::GetTabName(string entityTypeName)
0x28fc6  br.s     loc_28FD7
0x28fc8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28fcd  ldstr    aSfatabscontrol_1// "SFATabsControl.YammerTab"
0x28fd2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28fd7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28fdc  dup
0x28fdd  ldloc.3
0x28fde  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Hidden(bool value)
0x28fe3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28fe8  ldloc.0
0x28fe9  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x28fee  brfalse.s loc_29032
0x28ff0  ldarg.0
0x28ff1  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28ff6  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28ffb  dup
0x28ffc  ldstr    aActivityfeedss// "ActivityFeedsSystemTab"
0x29001  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x29006  dup
0x29007  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor()
0x2900c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x29011  dup
0x29012  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x29017  ldstr    aSfatabscontrol_0// "SFATabsControl.SystemPosts"
0x2901c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x29021  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x29026  dup
0x29027  ldloc.3
0x29028  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Hidden(bool value)
0x2902d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x29032  ret
```
