# Microsoft.Crm.Application.Bundling.ScriptBundleConfig::InitializeBundles

- ea: `0x12a00`
- end: `0x1312b`
- name: `Microsoft.Crm.Application.Bundling.ScriptBundleConfig::InitializeBundles`
- size: `1835`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x13130`

## callees

- `0x12a00`
- `0x13150`

## string_xrefs

- `0x12a07`: `~/_static/_common/scripts/jquery-2.1.1.min.js`
- `0x12a12`: `~/_static/_common/scripts/jsrender.min.js`
- `0x12a1d`: `~/_static/_common/scripts/jquery.tmpl.min.js`
- `0x12a2e`: `~/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x12a39`: `~/_static/_common/scripts/jqueryplugins.js`
- `0x12a44`: `~/_static/_common/scripts/jquery.jstree.js`
- `0x12a4f`: `~/_static/_common/scripts/jquery.hotkeys.js`
- `0x12a60`: `~/_static/_common/scripts/mscrm.caching.js`
- `0x12a71`: `~/_static/_common/scripts/Performance.js`
- `0x12a7c`: `~/_static/_common/scripts/SalesCommonImported.js`
- `0x12a87`: `~/_static/_common/scripts/SalesCommonFramework.js`
- `0x12a92`: `~/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x12abe`: `~/_static/_common/scripts/InlineEditCommon.js`
- `0x12ac9`: `~/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0x12ad4`: `~/_static/_common/scripts/main.js`
- `0x12b16`: `~/_static/_common/styles/autotooltip.js`
- `0x12b21`: `~/_static/_common/scripts/commandbaractions.js`
- `0x12b38`: `~/_static/_common/scripts/widgetmanager.js`
- `0x12b43`: `~/_static/_common/scripts/PostMessageCommunication.js`
- `0x12ba5`: `~/_static/_controls/pane/compositecontrol.js`
- `0x12bc9`: `~/_static/_common/scripts/GlowingImage.js`
- `0x12be1`: `~/_static/_controls/BreadCrumbControl/BreadCrumbControl.js`
- `0x12c41`: `~/_static/_forms/LinkControlBehavior.js`
- `0x12c4d`: `~/_static/_controls/CompositeData/CompositeDataControl.js`
- `0x12c7f`: `~/_static/_common/scripts/Wall.Interfaces.js`
- `0x12e24`: `~/_static/_common/scripts/Wall.Interfaces.js`
- `0x12c8b`: `~/_static/_common/scripts/Wall.Control.js`
- `0x12e30`: `~/_static/_common/scripts/Wall.Control.js`
- `0x12ca3`: `~/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0x12cfe`: `~/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0x12d71`: `~/_static/_common/scripts/maincontrols.js`
- `0x12d84`: `~/_static/_common/scripts/DashboardSelector.js`
- `0x12e18`: `~/_static/_common/scripts/CommandBarActions.js`
- `0x12e60`: `~/_static/_common/scripts/react.js`
- `0x12f1c`: `CommonBundle`
- `0x1300c`: `CommonExtendedBundle`

## pseudocode

```c

```

## disassembly

```asm
0x12a00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a05  stloc.0
0x12a06  ldloc.0
0x12a07  ldstr    aStaticCommonSc_20// "~/_static/_common/scripts/jquery-2.1.1."...
0x12a0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a11  ldloc.0
0x12a12  ldstr    aStaticCommonSc_21// "~/_static/_common/scripts/jsrender.min."...
0x12a17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a1c  ldloc.0
0x12a1d  ldstr    aStaticCommonSc_22// "~/_static/_common/scripts/jquery.tmpl.m"...
0x12a22  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a27  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a2c  stloc.1
0x12a2d  ldloc.1
0x12a2e  ldstr    aStaticCommonSc_23// "~/_static/_common/scripts/jquery_ui_1.8"...
0x12a33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a38  ldloc.1
0x12a39  ldstr    aStaticCommonSc_24// "~/_static/_common/scripts/jqueryplugins"...
0x12a3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a43  ldloc.1
0x12a44  ldstr    aStaticCommonSc_25// "~/_static/_common/scripts/jquery.jstree"...
0x12a49  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a4e  ldloc.1
0x12a4f  ldstr    aStaticCommonSc_26// "~/_static/_common/scripts/jquery.hotkey"...
0x12a54  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a59  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a5e  stloc.2
0x12a5f  ldloc.2
0x12a60  ldstr    aStaticCommonSc_27// "~/_static/_common/scripts/mscrm.caching"...
0x12a65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a6a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a6f  stloc.3
0x12a70  ldloc.3
0x12a71  ldstr    aStaticCommonSc_28// "~/_static/_common/scripts/Performance.j"...
0x12a76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a7b  ldloc.3
0x12a7c  ldstr    aStaticCommonSc_29// "~/_static/_common/scripts/SalesCommonIm"...
0x12a81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a86  ldloc.3
0x12a87  ldstr    aStaticCommonSc_30// "~/_static/_common/scripts/SalesCommonFr"...
0x12a8c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a91  ldloc.3
0x12a92  ldstr    aStaticCommonSc_31// "~/_static/_common/scripts/SalesCrmSoapP"...
0x12a97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a9c  ldloc.3
0x12a9d  ldstr    aStaticControls_23// "~/_static/_controls/NotificationList/No"...
0x12aa2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12aa7  ldloc.3
0x12aa8  ldstr    aStaticControls_24// "~/_static/_controls/FlyoutDialog/Flyout"...
0x12aad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ab2  ldloc.3
0x12ab3  ldstr    aStaticControls_25// "~/_static/_controls/InlineEdit/InlineEd"...
0x12ab8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12abd  ldloc.3
0x12abe  ldstr    aStaticCommonSc_32// "~/_static/_common/scripts/InlineEditCom"...
0x12ac3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ac8  ldloc.3
0x12ac9  ldstr    aStaticControls_26// "~/_static/_controls/GlobalQuickCreate/G"...
0x12ace  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ad3  ldloc.3
0x12ad4  ldstr    aStaticCommonSc_33// "~/_static/_common/scripts/main.js"
0x12ad9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ade  ldloc.3
0x12adf  ldstr    aStaticControls_27// "~/_static/_controls/MenuSelector/MenuSe"...
0x12ae4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ae9  ldloc.3
0x12aea  ldstr    aStaticControls_28// "~/_static/_controls/editableselect/edit"...
0x12aef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12af4  ldloc.3
0x12af5  ldstr    aStaticControls_29// "~/_static/_controls/datetimescroller/da"...
0x12afa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12aff  ldloc.3
0x12b00  ldstr    aStaticFormsDat// "~/_static/_forms/datetime.js"
0x12b05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b0a  ldloc.3
0x12b0b  ldstr    aStaticControls_30// "~/_static/_controls/lookupmru/lookupmru"...
0x12b10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b15  ldloc.3
0x12b16  ldstr    aStaticCommonSt_0// "~/_static/_common/styles/autotooltip.js"
0x12b1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b20  ldloc.3
0x12b21  ldstr    aStaticCommonSc_34// "~/_static/_common/scripts/commandbaract"...
0x12b26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b2b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12b30  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWidgetManagerFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12b35  brfalse.s loc_12B4D
0x12b37  ldloc.3
0x12b38  ldstr    aStaticCommonSc_35// "~/_static/_common/scripts/widgetmanager"...
0x12b3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b42  ldloc.3
0x12b43  ldstr    aStaticCommonSc_36// "~/_static/_common/scripts/PostMessageCo"...
0x12b48  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b4d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12b52  stloc.s  4
0x12b54  ldloc.s  4
0x12b56  ldstr    aStaticFormsSel_0// "~/_static/_forms/select.js"
0x12b5b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b60  ldloc.s  4
0x12b62  ldstr    aStaticFormsHid// "~/_static/_forms/HiddenInputBehavior.js"
0x12b67  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b6c  ldloc.s  4
0x12b6e  ldstr    aStaticNavTabba_0// "~/_static/_nav/TabBarControl.js"
0x12b73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b78  ldloc.s  4
0x12b7a  ldstr    aStaticFormsEma// "~/_static/_forms/EmailBodyInputBehavior"...
0x12b7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b84  ldloc.s  4
0x12b86  ldstr    aStaticFormsNum_0// "~/_static/_forms/numberinputbehavior.js"
0x12b8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b90  ldloc.s  4
0x12b92  ldstr    aStaticFormsFor_1// "~/_static/_forms/form.js"
0x12b97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12b9c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12ba1  stloc.s  5
0x12ba3  ldloc.s  5
0x12ba5  ldstr    aStaticControls_31// "~/_static/_controls/pane/compositecontr"...
0x12baa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12baf  ldloc.s  5
0x12bb1  ldstr    aStaticEntities// "~/_static/entities/productdetail.js"
0x12bb6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12bbb  ldloc.s  5
0x12bbd  ldstr    aStaticControls_32// "~/_static/_controls/HintText/HintText.j"...
0x12bc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12bc7  ldloc.s  5
0x12bc9  ldstr    aStaticCommonSc_37// "~/_static/_common/scripts/GlowingImage."...
0x12bce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12bd3  ldloc.s  5
0x12bd5  ldstr    aStaticControls_33// "~/_static/_controls/multipicklist/multi"...
0x12bda  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12bdf  ldloc.s  5
0x12be1  ldstr    aStaticControls_34// "~/_static/_controls/BreadCrumbControl/B"...
0x12be6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12beb  ldloc.s  5
0x12bed  ldstr    aStaticFormsLoo_0// "~/_static/_forms/LookupBehavior.js"
0x12bf2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12bf7  ldloc.s  5
0x12bf9  ldstr    aStaticControls_35// "~/_static/_controls/WebResourceControls"...
0x12bfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c03  ldloc.s  5
0x12c05  ldstr    aStaticControls_36// "~/_static/_controls/inlineedit/inlineed"...
0x12c0a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c0f  ldloc.s  5
0x12c11  ldstr    aStaticFormsChe// "~/_static/_forms/checkbox.js"
0x12c16  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c1b  ldloc.s  5
0x12c1d  ldstr    aStaticFormsTex// "~/_static/_forms/textinputbehavior.js"
0x12c22  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c27  ldloc.s  5
0x12c29  ldstr    aStaticAdvanced_0// "~/_static/AdvancedFind/AdvancedFindCont"...
0x12c2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c33  ldloc.s  5
0x12c35  ldstr    aStaticControls_37// "~/_static/_controls/inlineedit/inlineed"...
0x12c3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c3f  ldloc.s  5
0x12c41  ldstr    aStaticFormsLin// "~/_static/_forms/LinkControlBehavior.js"
0x12c46  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c4b  ldloc.s  5
0x12c4d  ldstr    aStaticControls_38// "~/_static/_controls/CompositeData/Compo"...
0x12c52  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c57  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12c5c  stloc.s  6
0x12c5e  ldloc.s  6
0x12c60  ldstr    aStaticControls_39// "~/_static/_controls/SocialInsights/Soci"...
0x12c65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c6a  ldloc.s  6
0x12c6c  ldstr    aStaticFormForm_0// "~/_static/form/FormControls.js"
0x12c71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c76  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12c7b  stloc.s  7
0x12c7d  ldloc.s  7
0x12c7f  ldstr    aStaticCommonSc_38// "~/_static/_common/scripts/Wall.Interfac"...
0x12c84  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c89  ldloc.s  7
0x12c8b  ldstr    aStaticCommonSc_39// "~/_static/_common/scripts/Wall.Control."...
0x12c90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c95  ldloc.s  7
0x12c97  ldstr    aStaticFormsAct// "~/_static/_forms/actionhubcontrol.js"
0x12c9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ca1  ldloc.s  7
0x12ca3  ldstr    aStaticControls_40// "~/_static/_controls/ActivityContainer/A"...
0x12ca8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cad  ldloc.s  7
0x12caf  ldstr    aStaticFormsAct_0// "~/_static/_forms/ActivitiesWallPage.js"
0x12cb4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cb9  ldloc.s  7
0x12cbb  ldstr    aStaticControls_41// "~/_static/_controls/ActivityContainer/A"...
0x12cc0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cc5  ldloc.s  7
0x12cc7  ldstr    aStaticFormTurb// "~/_static/form/Turbo.ActivityFeeds.js"
0x12ccc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cd1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12cd6  stloc.s  8
0x12cd8  ldloc.s  8
0x12cda  ldstr    aStaticControls_42// "~/_static/_controls/GetYammer/GetYammer"...
0x12cdf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12ce4  ldloc.s  8
0x12ce6  ldstr    aStaticFormsTab// "~/_static/_forms/Tabs.js"
0x12ceb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cf0  ldloc.s  8
0x12cf2  ldstr    aStaticControls_43// "~/_static/_controls/DPListControl/dynam"...
0x12cf7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12cfc  ldloc.s  8
0x12cfe  ldstr    aStaticControls_44// "~/_static/_controls/ReadForm/ReadFormUt"...
0x12d03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d08  ldloc.s  8
0x12d0a  ldstr    aStaticGridGrid_0// "~/_static/_grid/GridControl.js"
0x12d0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d14  ldloc.s  8
0x12d16  ldstr    aStaticControls_45// "~/_static/_controls/gridfilters/gridfil"...
0x12d1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d20  ldloc.s  8
0x12d22  ldstr    aStaticGridData// "~/_static/_grid/DataSetControl.js"
0x12d27  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d2c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12d31  stloc.s  9
0x12d33  ldloc.s  9
0x12d35  ldstr    aStaticControls_46// "~/_static/_controls/wallcontrol/errorre"...
0x12d3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d3f  ldloc.s  9
0x12d41  ldstr    aStaticControls_47// "~/_static/_controls/appmessagebar/appme"...
0x12d46  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d4b  ldloc.s  9
0x12d4d  ldstr    aStaticControls_48// "~/_static/_controls/AppNav/CrmNavBar.js"
0x12d52  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d57  ldloc.s  9
0x12d59  ldstr    aStaticControls_49// "~/_static/_controls/ribbon/ribbon.js"
0x12d5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d63  ldloc.s  9
0x12d65  ldstr    aStaticControls_50// "~/_static/_controls/NavBar/NavBar.js"
0x12d6a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d6f  ldloc.s  9
0x12d71  ldstr    aStaticCommonSc_40// "~/_static/_common/scripts/maincontrols."...
0x12d76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d7b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12d80  stloc.s  0xA
0x12d82  ldloc.s  0xA
0x12d84  ldstr    aStaticCommonSc_41// "~/_static/_common/scripts/DashboardSele"...
0x12d89  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d8e  ldloc.s  0xA
0x12d90  ldstr    aStaticVisualiz// "~/_static/visualization/visualizationac"...
0x12d95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12d9a  ldloc.s  0xA
0x12d9c  ldstr    aStaticControls_51// "~/_static/_controls/pane/visualizationp"...
0x12da1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12da6  ldloc.s  0xA
0x12da8  ldstr    aStaticVisualiz_0// "~/_static/visualization/visualization.j"...
0x12dad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12db2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12db7  stloc.s  0xB
0x12db9  ldloc.s  0xB
0x12dbb  ldstr    aStaticControls_52// "~/_static/_controls/processcontrol/proc"...
0x12dc0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12dc5  ldloc.s  0xB
0x12dc7  ldstr    aStaticControls_53// "~/_static/_controls/processcontrol/proc"...
0x12dcc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12dd1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12dd6  stloc.s  0xC
0x12dd8  ldloc.s  0xC
0x12dda  ldstr    aStaticFormsNot// "~/_static/_forms/notesv2.js"
0x12ddf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12de4  ldloc.s  0xC
0x12de6  ldstr    aStaticControls_54// "~/_static/_controls/pagehandler/entityp"...
0x12deb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12df0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12df5  stloc.s  0xD
0x12df7  ldloc.s  0xD
0x12df9  ldstr    aStaticControls_55// "~/_static/_controls/datetime/time.js"
0x12dfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e03  ldloc.s  0xD
0x12e05  ldstr    aStaticControls_56// "~/_static/_controls/datetime/date.js"
0x12e0a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e0f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12e14  stloc.s  0xE
0x12e16  ldloc.s  0xE
0x12e18  ldstr    aStaticCommonSc_42// "~/_static/_common/scripts/CommandBarAct"...
0x12e1d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e22  ldloc.s  0xE
0x12e24  ldstr    aStaticCommonSc_38// "~/_static/_common/scripts/Wall.Interfac"...
0x12e29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e2e  ldloc.s  0xE
0x12e30  ldstr    aStaticCommonSc_39// "~/_static/_common/scripts/Wall.Control."...
0x12e35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e3a  ldloc.s  0xE
0x12e3c  ldstr    aStaticFormsAct// "~/_static/_forms/actionhubcontrol.js"
0x12e41  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e46  ldloc.s  0xE
0x12e48  ldstr    aStaticActiviti_1// "~/_static/activities/email.js"
0x12e4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e52  ldloc.s  0xE
0x12e54  ldstr    aStaticControls_57// "~/_static/_controls/actionhubcontrol/rx"...
0x12e59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e5e  ldloc.s  0xE
0x12e60  ldstr    aStaticCommonSc_43// "~/_static/_common/scripts/react.js"
0x12e65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e6a  ldloc.s  0xE
0x12e6c  ldstr    aStaticControls_58// "~/_static/_controls/actionhubcontrol/ac"...
0x12e71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12e76  ldstr    aJquerybasebund// "JqueryBaseBundle"
0x12e7b  ldloc.0
0x12e7c  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
  ... truncated ...
```
