# Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderExternalPartyParentAssociationSetup

- ea: `0x187f0`
- end: `0x18aaa`
- name: `Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderExternalPartyParentAssociationSetup`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18c50`

## callees

- `0x187f0`
- `0x22480`
- `0x23f00`
- `0x26530`
- `0x26600`
- `0x26750`

## pseudocode

```c

```

## disassembly

```asm
0x187f0  ldarg.1
0x187f1  ldstr    aTableWidth100S// "<table width=\"100%\" style=\"padding-b"...
0x187f6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x187fb  ldarg.1
0x187fc  ldstr    aTrTdClassMsCrm// "<tr><td class=\"ms-crm-Form-Section ms-"...
0x18801  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18806  ldstr    aExternalApplic_10// "External_Applications_ParentAssociation"...
0x1880b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18810  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18815  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1881a  ldarg.1
0x1881b  ldstr    aTrTdColspan20T// "<tr><td colspan=\"2\">{0}</td></tr>"
0x18820  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18825  ldstr    aExternalApplic_11// "External_Applications_ParentAssocation_"...
0x1882a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1882f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18834  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x18839  ldarg.1
0x1883a  ldstr    aTrTdClassMsCrm_0// "<tr><td class=\"ms-crm-EntitySection\">"...
0x1883f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18844  ldstr    aExternalApplic_12// "External_Applications_ParentAssocation_"...
0x18849  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1884e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18853  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18858  ldstr    aExternalApplic_13// "External_Applications_ParentAssocation_"...
0x1885d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18862  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18867  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1886c  ldarg.1
0x1886d  ldstr    aTrTdClassMsCrm_3// "<tr><td class=\"ms-crm-EntitySection\" "...
0x18872  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18877  ldarg.2
0x18878  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x1887d  stloc.0
0x1887e  br       loc_1895F
0x18883  ldloca.s 0
0x18885  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x1888a  stloc.1
0x1888b  ldarg.1
0x1888c  ldc.i4.s 0xB
0x1888e  newarr   [mscorlib]System.String
0x18893  dup
0x18894  ldc.i4.0
0x18895  ldstr    aTrOnclickFetch_0// "<tr onclick=\"fetchExternalPartyFieldsF"...
0x1889a  stelem.ref
0x1889b  dup
0x1889c  ldc.i4.1
0x1889d  ldloc.1
0x1889e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x188a3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x188a8  stelem.ref
0x188a9  dup
0x188aa  ldc.i4.2
0x188ab  ldstr    asc_42E92// "','"
0x188b0  stelem.ref
0x188b1  dup
0x188b2  ldc.i4.3
0x188b3  ldloc.1
0x188b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x188b9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x188be  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x188c3  ldarg.0
0x188c4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x188c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x188ce  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x188d3  stelem.ref
0x188d4  dup
0x188d5  ldc.i4.4
0x188d6  ldstr    aStyleHeight25p_0// "');\" style=\"height: 25px\"><td id=\"p"...
0x188db  stelem.ref
0x188dc  dup
0x188dd  ldc.i4.5
0x188de  ldloc.1
0x188df  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x188e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x188e9  stelem.ref
0x188ea  dup
0x188eb  ldc.i4.6
0x188ec  ldstr    aNowrapClassMsC_0// "\" nowrap class=\"ms-crm-EntityName\" t"...
0x188f1  stelem.ref
0x188f2  dup
0x188f3  ldc.i4.7
0x188f4  ldloc.1
0x188f5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x188fa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x188ff  stelem.ref
0x18900  dup
0x18901  ldc.i4.8
0x18902  ldstr    asc_42E92// "','"
0x18907  stelem.ref
0x18908  dup
0x18909  ldc.i4.s 9
0x1890b  ldloc.1
0x1890c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18911  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x18916  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1891b  ldarg.0
0x1891c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18921  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18926  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1892b  stelem.ref
0x1892c  dup
0x1892d  ldc.i4.s 0xA
0x1892f  ldstr    a0TdTr// "');\" >{0}</td></tr>"
0x18934  stelem.ref
0x18935  call     string [mscorlib]System.String::Concat(string[])
0x1893a  ldloc.1
0x1893b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18940  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x18945  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1894a  ldarg.0
0x1894b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18950  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18955  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1895a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1895f  ldloca.s 0
0x18961  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::MoveNext()
0x18966  brtrue   loc_18883
0x1896b  leave.s  loc_1897B
0x1896d  ldloca.s 0
0x1896f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>
0x18975  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1897a  endfinally
0x1897b  ldarg.1
0x1897c  ldstr    aTbodyTableDivT_1// "</tbody></table></div></td><td class=\""...
0x18981  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18986  ldstr    aExternalApplic_14// "External_Applications_ParentAssociation"...
0x1898b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18990  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18995  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1899a  ldarg.1
0x1899b  ldstr    aDivIdParentass// "<div id=\"parentAssoc_selectedEntityNam"...
0x189a0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x189a5  ldarg.0
0x189a6  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_parentAttributeSelect
0x189ab  ldarg.1
0x189ac  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x189b1  ldarg.1
0x189b2  ldstr    aDivDivDivIdExt// "</div></div><div id=\"extChannelSection"...
0x189b7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x189bc  ldarg.3
0x189bd  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x189c2  stloc.0
0x189c3  br       loc_18A82
0x189c8  ldloca.s 0
0x189ca  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x189cf  stloc.2
0x189d0  ldarg.1
0x189d1  ldstr    aTrTdClassMsCrm_2// "<tr><td class=\" ms-crm-EntityFieldSect"...
0x189d6  ldloc.2
0x189d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x189dc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x189e1  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x189e6  ldarg.0
0x189e7  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x189ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x189f1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x189f6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x189fb  ldarg.0
0x189fc  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x18a01  dup
0x18a02  stloc.s  4
0x18a04  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a09  ldloc.s  4
0x18a0b  stloc.3
0x18a0c  ldarg.0
0x18a0d  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a12  ldloc.2
0x18a13  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18a18  ldstr    aParentAssoExtC// "parent_asso_ext_channel_fields"
0x18a1d  call     string [mscorlib]System.String::Concat(string, string)
0x18a22  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x18a27  ldarg.0
0x18a28  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a2d  ldstr    aOnparentassoci// "onParentAssociationFieldChange(this);"
0x18a32  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string value)
0x18a37  ldarg.0
0x18a38  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a3d  ldc.i4.0
0x18a3e  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x18a43  ldarg.0
0x18a44  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a49  ldarg.1
0x18a4a  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x18a4f  ldarg.1
0x18a50  ldarg.0
0x18a51  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a56  callvirt instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0x18a5b  ldarg.0
0x18a5c  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18a61  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x18a66  call     void Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter output, string clientSideFormInputBehaviorClassName, string id)
0x18a6b  leave.s  loc_18A77
0x18a6d  ldloc.3
0x18a6e  brfalse.s loc_18A76
0x18a70  ldloc.3
0x18a71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a76  endfinally
0x18a77  ldarg.1
0x18a78  ldstr    aTdTr// "</td></tr>"
0x18a7d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18a82  ldloca.s 0
0x18a84  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::MoveNext()
0x18a89  brtrue   loc_189C8
0x18a8e  leave.s  loc_18A9E
0x18a90  ldloca.s 0
0x18a92  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>
0x18a98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a9d  endfinally
0x18a9e  ldarg.1
0x18a9f  ldstr    aTbodyTableDivT_0// "</tbody></table></div></td></tr></table"...
0x18aa4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18aa9  ret
```
