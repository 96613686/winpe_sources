# Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderExternalPartyRecordAssociationSetup

- ea: `0x18560`
- end: `0x187ef`
- name: `Microsoft.Crm.Application.Components.UI.ExternalApplications::RenderExternalPartyRecordAssociationSetup`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18c50`

## callees

- `0x18560`
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
0x18560  ldarg.1
0x18561  ldstr    aTableWidth100S// "<table width=\"100%\" style=\"padding-b"...
0x18566  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1856b  ldarg.1
0x1856c  ldstr    aTrTdClassMsCrm// "<tr><td class=\"ms-crm-Form-Section ms-"...
0x18571  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18576  ldstr    aExternalApplic_6// "External_Applications_RecordAssocation_"...
0x1857b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18580  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x18585  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1858a  ldarg.1
0x1858b  ldstr    aTrTdColspan20T// "<tr><td colspan=\"2\">{0}</td></tr>"
0x18590  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18595  ldstr    aExternalApplic_7// "External_Applications_RecordAssocation_"...
0x1859a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1859f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x185a4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x185a9  ldarg.1
0x185aa  ldstr    aTrTdClassMsCrm_0// "<tr><td class=\"ms-crm-EntitySection\">"...
0x185af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x185b4  ldstr    aExternalApplic_8// "External_Applications_RecordAssocation_"...
0x185b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x185be  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x185c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x185c8  ldstr    aExternalApplic_9// "External_Applications_RecordAssocation_"...
0x185cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x185d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x185d7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x185dc  ldarg.1
0x185dd  ldstr    aTrTdClassMsCrm_1// "<tr><td class=\"ms-crm-EntitySection\" "...
0x185e2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x185e7  ldarg.2
0x185e8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x185ed  stloc.0
0x185ee  br       loc_186CF
0x185f3  ldloca.s 0
0x185f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x185fa  stloc.1
0x185fb  ldarg.1
0x185fc  ldc.i4.s 0xB
0x185fe  newarr   [mscorlib]System.String
0x18603  dup
0x18604  ldc.i4.0
0x18605  ldstr    aTrOnclickFetch// "<tr onclick=\"fetchExternalPartyFieldsF"...
0x1860a  stelem.ref
0x1860b  dup
0x1860c  ldc.i4.1
0x1860d  ldloc.1
0x1860e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18613  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x18618  stelem.ref
0x18619  dup
0x1861a  ldc.i4.2
0x1861b  ldstr    asc_42E92// "','"
0x18620  stelem.ref
0x18621  dup
0x18622  ldc.i4.3
0x18623  ldloc.1
0x18624  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18629  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1862e  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x18633  ldarg.0
0x18634  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18639  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1863e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x18643  stelem.ref
0x18644  dup
0x18645  ldc.i4.4
0x18646  ldstr    aStyleHeight25p// "');\" style=\"height: 25px\"><td id=\"r"...
0x1864b  stelem.ref
0x1864c  dup
0x1864d  ldc.i4.5
0x1864e  ldloc.1
0x1864f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18654  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x18659  stelem.ref
0x1865a  dup
0x1865b  ldc.i4.6
0x1865c  ldstr    aNowrapClassMsC// "\" nowrap class=\"ms-crm-EntityName\" t"...
0x18661  stelem.ref
0x18662  dup
0x18663  ldc.i4.7
0x18664  ldloc.1
0x18665  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1866a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1866f  stelem.ref
0x18670  dup
0x18671  ldc.i4.8
0x18672  ldstr    asc_42E92// "','"
0x18677  stelem.ref
0x18678  dup
0x18679  ldc.i4.s 9
0x1867b  ldloc.1
0x1867c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18681  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x18686  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1868b  ldarg.0
0x1868c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18691  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18696  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1869b  stelem.ref
0x1869c  dup
0x1869d  ldc.i4.s 0xA
0x1869f  ldstr    a0TdTr// "');\" >{0}</td></tr>"
0x186a4  stelem.ref
0x186a5  call     string [mscorlib]System.String::Concat(string[])
0x186aa  ldloc.1
0x186ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x186b0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x186b5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x186ba  ldarg.0
0x186bb  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x186c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x186c5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x186ca  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x186cf  ldloca.s 0
0x186d1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::MoveNext()
0x186d6  brtrue   loc_185F3
0x186db  leave.s  loc_186EB
0x186dd  ldloca.s 0
0x186df  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>
0x186e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x186ea  endfinally
0x186eb  ldarg.1
0x186ec  ldstr    aTbodyTableDivT// "</tbody></table></div></td><td class=\""...
0x186f1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x186f6  ldarg.1
0x186f7  ldstr    aDivTableStyleB// "</div><table style=\"border-spacing:0 5"...
0x186fc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18701  ldarg.3
0x18702  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x18707  stloc.0
0x18708  br       loc_187C7
0x1870d  ldloca.s 0
0x1870f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x18714  stloc.2
0x18715  ldarg.1
0x18716  ldstr    aTrTdClassMsCrm_2// "<tr><td class=\" ms-crm-EntityFieldSect"...
0x1871b  ldloc.2
0x1871c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x18721  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x18726  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1872b  ldarg.0
0x1872c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18731  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18736  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1873b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x18740  ldarg.0
0x18741  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x18746  dup
0x18747  stloc.s  4
0x18749  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x1874e  ldloc.s  4
0x18750  stloc.3
0x18751  ldarg.0
0x18752  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18757  ldloc.2
0x18758  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1875d  ldstr    aRecordAssoExtC// "record_asso_ext_channel_fields"
0x18762  call     string [mscorlib]System.String::Concat(string, string)
0x18767  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1876c  ldarg.0
0x1876d  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18772  ldstr    aOnrecordassoci// "onRecordAssociationFieldChange(this);"
0x18777  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string value)
0x1877c  ldarg.0
0x1877d  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x18782  ldc.i4.0
0x18783  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x18788  ldarg.0
0x18789  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x1878e  ldarg.1
0x1878f  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x18794  ldarg.1
0x18795  ldarg.0
0x18796  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x1879b  callvirt instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0x187a0  ldarg.0
0x187a1  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x187a6  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x187ab  call     void Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter output, string clientSideFormInputBehaviorClassName, string id)
0x187b0  leave.s  loc_187BC
0x187b2  ldloc.3
0x187b3  brfalse.s loc_187BB
0x187b5  ldloc.3
0x187b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x187bb  endfinally
0x187bc  ldarg.1
0x187bd  ldstr    aTdTr// "</td></tr>"
0x187c2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x187c7  ldloca.s 0
0x187c9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::MoveNext()
0x187ce  brtrue   loc_1870D
0x187d3  leave.s  loc_187E3
0x187d5  ldloca.s 0
0x187d7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>
0x187dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x187e2  endfinally
0x187e3  ldarg.1
0x187e4  ldstr    aTbodyTableDivT_0// "</tbody></table></div></td></tr></table"...
0x187e9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x187ee  ret
```
