# Microsoft.Crm.Application.Components.UI.RegionalOptions::Render

- ea: `0x21ff0`
- end: `0x2221d`
- name: `Microsoft.Crm.Application.Components.UI.RegionalOptions::Render`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x21e00`
- `0x21e30`
- `0x21e50`
- `0x21f90`
- `0x21ff0`
- `0x22220`
- `0x22df0`
- `0x22e00`
- `0x23c30`
- `0x24290`

## pseudocode

```c

```

## disassembly

```asm
0x21ff0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x21ff5  brfalse.s loc_21FFF
0x21ff7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x21ffc  brtrue.s loc_21FFF
0x21ffe  ret
0x21fff  ldarg.1
0x22000  ldstr    aTableWidth100// "<table width=\"100%\">"
0x22005  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2200a  ldarg.1
0x2200b  ldstr    aColWidth700Col// "<col width=700><col>"
0x22010  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22015  ldarg.1
0x22016  ldstr    aTrTdClassMsCrm_5// "<tr><td class=\"ms-crm-Form-Section ms-"...
0x2201b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22020  ldarg.0
0x22021  call     instance bool Microsoft.Crm.Application.Components.UI.RegionalOptions::get_UserSettings()
0x22026  brtrue.s loc_2202F
0x22028  ldstr    aRegionalOption_5// "Regional_Option_System_Options_Tab_Head"...
0x2202d  br.s     loc_22034
0x2202f  ldstr    aRegionalOption_6// "Regional_Option_Personal_Options_Tab_He"...
0x22034  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22039  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2203e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x22043  ldarg.1
0x22044  ldstr    aTrTdColspan2Id// "<tr><td colspan=\"2\" id=\"standardForm"...
0x22049  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2204e  ldstr    aRegionalOption_7// "Regional_Option_Tab_Desc"
0x22053  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22058  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2205d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x22062  ldarg.1
0x22063  ldstr    aTrTdClassMsCrm_6// "<tr><td class=\"ms-crm-Form-Section ms-"...
0x22068  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2206d  ldstr    aRegionalOption_8// "Regional_Option_Tab_Options_Label"
0x22072  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22077  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2207c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22081  ldstr    aRegionalOption_9// "Regional_Option_Tab_Options_Label_Toolt"...
0x22086  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2208b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x22090  ldarg.0
0x22091  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.RegionalOptions::_localeOptions
0x22096  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2209b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x220a0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object, object)
0x220a5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteUserSettings()
0x220aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x220af  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x220b4  brtrue.s loc_220CE
0x220b6  ldarg.0
0x220b7  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.RegionalOptions::_localeOptions
0x220bc  ldc.i4.1
0x220bd  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x220c2  ldarg.0
0x220c3  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.RegionalOptions::_customizeButton
0x220c8  ldc.i4.1
0x220c9  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x220ce  ldarg.1
0x220cf  ldstr    aTrStylePadding// "<tr style=\"padding-top:10px;\"><td now"...
0x220d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x220d9  ldarg.0
0x220da  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.RegionalOptions::_localeOptions
0x220df  ldarg.1
0x220e0  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x220e5  ldarg.1
0x220e6  ldstr    aTdTd_0// "</td><td>"
0x220eb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x220f0  ldarg.0
0x220f1  call     instance void Microsoft.Crm.Application.Components.UI.RegionalOptions::SetCustomizeButtonHandler()
0x220f6  ldarg.0
0x220f7  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.RegionalOptions::_customizeButton
0x220fc  ldarg.1
0x220fd  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x22102  ldarg.1
0x22103  ldstr    aTdTr// "</td></tr>"
0x22108  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2210d  ldarg.0
0x2210e  call     instance bool Microsoft.Crm.Application.Components.UI.RegionalOptions::get_ShowSampleStandards()
0x22113  brfalse  loc_22211
0x22118  ldarg.0
0x22119  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x2211e  ldc.i4.1
0x2211f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_ReadOnly(bool value)
0x22124  ldarg.1
0x22125  ldstr    aTrTdColspan2Fi// "<tr><td colspan=\"2\"><fieldset style="...
0x2212a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2212f  ldstr    aRegionalOption_10// "Regional_Option_Tab_SamplePreview"
0x22134  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22139  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2213e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x22143  ldsfld   string [mscorlib]System.String::Empty
0x22148  stloc.0
0x22149  ldarg.0
0x2214a  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype SampleStandardInfo> Microsoft.Crm.Application.Components.UI.RegionalOptions::_samplesList
0x2214f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype SampleStandardInfo>::GetEnumerator()
0x22154  stloc.1
0x22155  br       loc_221EA
0x2215a  ldloca.s 1
0x2215c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype SampleStandardInfo>::get_Current()
0x22161  stloc.2
0x22162  ldarg.0
0x22163  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x22168  ldarg.0
0x22169  ldloc.2
0x2216a  call     instance string Microsoft.Crm.Application.Components.UI.RegionalOptions::getSampleData(valuetype SampleStandardInfo sample)
0x2216f  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string value)
0x22174  ldarg.0
0x22175  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x2217a  ldloc.2
0x2217b  ldfld    string SampleStandardInfo::_id
0x22180  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x22185  ldarg.0
0x22186  ldloc.2
0x22187  call     instance string Microsoft.Crm.Application.Components.UI.RegionalOptions::formatReadingOrder(valuetype SampleStandardInfo sample)
0x2218c  stloc.0
0x2218d  ldarg.1
0x2218e  ldstr    aTrStylePadding_0// "<tr style=\"padding-top:5px\"><td></td>"...
0x22193  ldloc.2
0x22194  ldfld    string SampleStandardInfo::_resourceId
0x22199  ldloc.0
0x2219a  ldloc.2
0x2219b  ldfld    string SampleStandardInfo::_id
0x221a0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object, object)
0x221a5  ldloc.2
0x221a6  ldfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleSetting SampleStandardInfo::_field
0x221ab  ldc.i4.2
0x221ac  bne.un.s loc_221D3
0x221ae  ldarg.0
0x221af  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x221b4  ldstr    asc_5AEF8// "\u200E"
0x221b9  ldarg.0
0x221ba  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x221bf  callvirt instance string Microsoft.Crm.Application.Components.UI.TextBox::get_Text()
0x221c4  ldstr    asc_5AEFC// "\u202A"
0x221c9  call     string [mscorlib]System.String::Concat(string, string, string)
0x221ce  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string value)
0x221d3  ldarg.0
0x221d4  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.RegionalOptions::_sampleData
0x221d9  ldarg.1
0x221da  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x221df  ldarg.1
0x221e0  ldstr    aTdTdTdTr// "</td><td></td></tr>"
0x221e5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x221ea  ldloca.s 1
0x221ec  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype SampleStandardInfo>::MoveNext()
0x221f1  brtrue   loc_2215A
0x221f6  leave.s  loc_22206
0x221f8  ldloca.s 1
0x221fa  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype SampleStandardInfo>
0x22200  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22205  endfinally
0x22206  ldarg.1
0x22207  ldstr    aTableFieldsetT// "</table></fieldset></td></tr>"
0x2220c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22211  ldarg.1
0x22212  ldstr    aTable_0// "</table>"
0x22217  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2221c  ret
```
