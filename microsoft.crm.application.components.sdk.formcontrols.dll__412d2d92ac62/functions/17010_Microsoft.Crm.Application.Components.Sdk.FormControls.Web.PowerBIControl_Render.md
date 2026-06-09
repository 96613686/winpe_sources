# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::Render

- ea: `0x17010`
- end: `0x17171`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::Render`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x15280`
- `0x152d0`
- `0x152f0`
- `0x15310`
- `0x16ed0`
- `0x17010`
- `0x17180`
- `0x17230`
- `0x174d0`
- `0x17a10`

## pseudocode

```c

```

## disassembly

```asm
0x17010  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x17015  brtrue.s loc_1703B
0x17017  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x1701c  brfalse.s loc_1703A
0x1701e  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_IsPowerBIEnabledByAdmin()
0x17023  brfalse.s loc_17031
0x17025  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1702a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::IsPowerBIEmbedFCBEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1702f  brtrue.s loc_17032
0x17031  ret
0x17032  ldarg.0
0x17033  ldarg.1
0x17034  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WritePowerBIOutlookOfflineScreen(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x17039  ret
0x1703a  ret
0x1703b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17040  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::IsPowerBITileFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17045  brtrue.s loc_17048
0x17047  ret
0x17048  ldarg.1
0x17049  brtrue.s loc_17056
0x1704b  ldstr    aOutput// "output"
0x17050  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17055  throw
0x17056  ldc.i4.s 0x19
0x17058  stloc.0
0x17059  ldloca.s 0
0x1705b  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x17061  callvirt instance string [mscorlib]System.Object::ToString()
0x17066  ldarg.1
0x17067  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x1706c  dup
0x1706d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17072  ldc.i4.s 0xA
0x17074  stloc.1
0x17075  ldloca.s 1
0x17077  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1707d  callvirt instance string [mscorlib]System.Object::ToString()
0x17082  ldstr    aMsCrmPowerbi// "ms-crm-powerbi"
0x17087  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1708c  dup
0x1708d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17092  ldc.i4.s 0x11
0x17094  stloc.1
0x17095  ldloca.s 1
0x17097  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1709d  callvirt instance string [mscorlib]System.Object::ToString()
0x170a2  ldarg.0
0x170a3  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x170a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x170ad  dup
0x170ae  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x170b3  ldc.i4.s 0x20
0x170b5  stloc.1
0x170b6  ldloca.s 1
0x170b8  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x170be  callvirt instance string [mscorlib]System.Object::ToString()
0x170c3  ldarg.0
0x170c4  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x170c9  stloc.2
0x170ca  ldloca.s 2
0x170cc  ldstr    aD// "D"
0x170d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x170d6  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x170db  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x170e0  dup
0x170e1  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x170e6  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_IsPowerBIEnabledByAdmin()
0x170eb  brtrue.s loc_170F6
0x170ed  ldarg.0
0x170ee  ldarg.1
0x170ef  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WritePowerBIAdminDisabledScreen(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x170f4  br.s     loc_1714D
0x170f6  ldarg.0
0x170f7  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::get_Type()
0x170fc  brtrue.s loc_17105
0x170fe  ldarg.0
0x170ff  ldarg.1
0x17100  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButtonContainerAndButtons(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x17105  ldc.i4.s 0x19
0x17107  stloc.0
0x17108  ldloca.s 0
0x1710a  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x17110  callvirt instance string [mscorlib]System.Object::ToString()
0x17115  ldarg.1
0x17116  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x1711b  dup
0x1711c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17121  ldc.i4.s 0xA
0x17123  stloc.1
0x17124  ldloca.s 1
0x17126  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1712c  callvirt instance string [mscorlib]System.Object::ToString()
0x17131  ldstr    aMsCrmPowerbiIf_0// "ms-crm-powerbi-iframe-container"
0x17136  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1713b  dup
0x1713c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x17141  ldarg.0
0x17142  ldarg.1
0x17143  callvirt instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x17148  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x1714d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x17152  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIEmbedEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIEmbedEventSource::get_Instance()
0x17157  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1715c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x17161  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x17166  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x1716b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIEmbedEventSource::LogRunTimeLoaded(valuetype [mscorlib]System.Guid, string, string)
0x17170  ret
```
