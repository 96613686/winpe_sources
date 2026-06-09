# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::ConfigureHeader

- ea: `0x22010`
- end: `0x22155`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::ConfigureHeader`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x22010`
- `0x22160`
- `0x22340`

## string_xrefs

- `0x22040`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x22050`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x22060`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x22070`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x22080`: `/_static/_common/scripts/Wall.Control.js`
- `0x22120`: `masterComponentId`
- `0x220d8`: `/_controls/onenotecontrol/onenotecontroltemplate.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x22010  ldarg.0
0x22011  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x22016  ldarg.0
0x22017  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2201c  ldc.i4.1
0x2201d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x22022  ldarg.0
0x22023  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22028  ldc.i4.1
0x22029  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x2202e  ldarg.0
0x2202f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22034  ldc.i4.1
0x22035  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJSRender(bool)
0x2203a  ldarg.0
0x2203b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22040  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x22045  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2204a  ldarg.0
0x2204b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22050  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x22055  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2205a  ldarg.0
0x2205b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22060  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x22065  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2206a  ldarg.0
0x2206b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22070  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x22075  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2207a  ldarg.0
0x2207b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22080  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x22085  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2208a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2208f  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x22094  stloc.3
0x22095  ldloca.s 3
0x22097  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2209c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x220a1  stloc.0
0x220a2  ldarg.0
0x220a3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x220a8  ldstr    aControlsOnenot// "/_controls/OneNoteControl/onenotecontro"...
0x220ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x220b2  ldarg.0
0x220b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x220b8  ldstr    aStaticFormsOne// "/_static/_forms/OneNoteControl.js"
0x220bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x220c2  ldarg.0
0x220c3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x220c8  ldstr    aOnenotestrings// "_OneNoteStrings"
0x220cd  ldarg.0
0x220ce  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::GenerateClientStrings()
0x220d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x220d8  ldstr    aControlsOnenot_0// "/_controls/onenotecontrol/onenotecontro"...
0x220dd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x220e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x220e7  stloc.1
0x220e8  ldloc.1
0x220e9  ldc.i4.1
0x220ea  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x220ef  ldloc.1
0x220f0  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x220f5  ldstr    aLcid// "lcid"
0x220fa  ldloc.0
0x220fb  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x22100  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x22105  stloc.2
0x22106  ldloc.2
0x22107  ldstr    aWallcontentpag// "wallContentPageUrl"
0x2210c  ldloc.1
0x2210d  callvirt instance string [mscorlib]System.Object::ToString()
0x22112  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22117  ldarg.0
0x22118  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::get_MasterComponentId()
0x2211d  brfalse.s loc_22130
0x2211f  ldloc.2
0x22120  ldstr    aMastercomponen// "masterComponentId"
0x22125  ldarg.0
0x22126  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::get_MasterComponentId()
0x2212b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22130  ldarg.0
0x22131  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x22136  ldstr    aMscrmOnenoteco// "Mscrm.OneNoteControl.OneNoteControl"
0x2213b  ldloc.2
0x2213c  ldnull
0x2213d  ldnull
0x2213e  ldarg.0
0x2213f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22144  ldstr    aContainer// "_container"
0x22149  call     string [mscorlib]System.String::Concat(string, string)
0x2214e  ldc.i4.1
0x2214f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x22154  ret
```
