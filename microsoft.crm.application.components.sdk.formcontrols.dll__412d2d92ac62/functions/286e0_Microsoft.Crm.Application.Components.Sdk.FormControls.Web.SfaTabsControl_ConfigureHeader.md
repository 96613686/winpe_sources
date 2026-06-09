# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::ConfigureHeader

- ea: `0x286e0`
- end: `0x287f7`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::ConfigureHeader`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28400`
- `0x28420`
- `0x28440`
- `0x28460`
- `0x28480`
- `0x28640`
- `0x286e0`
- `0x29f40`
- `0x2a180`

## string_xrefs

- `0x286ed`: `masterComponentId`
- `0x2870e`: `isControlReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x286e0  ldarg.0
0x286e1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::ConfigureHeader()
0x286e6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x286eb  stloc.0
0x286ec  ldloc.0
0x286ed  ldstr    aMastercomponen// "masterComponentId"
0x286f2  ldarg.0
0x286f3  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_MasterComponentId()
0x286f8  brtrue.s loc_28702
0x286fa  ldarg.0
0x286fb  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28700  br.s     loc_28708
0x28702  ldarg.0
0x28703  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_MasterComponentId()
0x28708  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2870d  ldloc.0
0x2870e  ldstr    aIscontrolreado// "isControlReadOnly"
0x28713  ldarg.0
0x28714  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28719  box      [mscorlib]System.Boolean
0x2871e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28723  ldloc.0
0x28724  ldstr    aShowwallconten// "showWallContentOnLoad"
0x28729  ldarg.0
0x2872a  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_ShowWallContentOnLoad()
0x2872f  box      [mscorlib]System.Boolean
0x28734  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28739  ldarg.0
0x2873a  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_DefaultTabId()
0x2873f  brfalse.s loc_28752
0x28741  ldloc.0
0x28742  ldstr    aDefaulttabid// "defaultTabId"
0x28747  ldarg.0
0x28748  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_DefaultTabId()
0x2874d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28752  ldarg.0
0x28753  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_OrderByActivityWall()
0x28758  brfalse.s loc_2876B
0x2875a  ldloc.0
0x2875b  ldstr    aOrderbyactivit// "orderByActivityWall"
0x28760  ldarg.0
0x28761  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_OrderByActivityWall()
0x28766  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2876b  ldarg.0
0x2876c  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_SortActivityWall()
0x28771  brfalse.s loc_28784
0x28773  ldloc.0
0x28774  ldstr    aSortactivitywa// "sortActivityWall"
0x28779  ldarg.0
0x2877a  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_SortActivityWall()
0x2877f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28784  ldarg.0
0x28785  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_EmailConversationView()
0x2878a  pop
0x2878b  ldloc.0
0x2878c  ldstr    aEmailconversat// "emailConversationView"
0x28791  ldarg.0
0x28792  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_EmailConversationView()
0x28797  box      [mscorlib]System.Boolean
0x2879c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x287a1  ldarg.0
0x287a2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x287a7  ldstr    aIsEmailConvers// "IS_EMAIL_CONVERSATION"
0x287ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x287b1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEmailConversationViewFCB(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x287b6  brfalse.s loc_287C0
0x287b8  ldarg.0
0x287b9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_EmailConversationView()
0x287be  br.s     loc_287C1
0x287c0  ldc.i4.0
0x287c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x287c6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x287cb  stloc.1
0x287cc  ldloc.1
0x287cd  ldstr    aEventmanager// "eventManager"
0x287d2  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x287d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x287dc  ldarg.0
0x287dd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x287e2  ldstr    aMscrmForminput_4// "Mscrm.FormInputControl.Tabs.SfaTabsCont"...
0x287e7  ldloc.0
0x287e8  ldnull
0x287e9  ldloc.1
0x287ea  ldarg.0
0x287eb  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x287f0  ldc.i4.1
0x287f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x287f6  ret
```
