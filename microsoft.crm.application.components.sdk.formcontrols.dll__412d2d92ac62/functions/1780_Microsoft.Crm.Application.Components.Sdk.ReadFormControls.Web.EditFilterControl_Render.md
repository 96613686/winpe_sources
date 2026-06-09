# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::Render

- ea: `0x1780`
- end: `0x19cd`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::Render`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xb050`

## callees

- `0x1450`
- `0x1710`
- `0x1730`
- `0x1750`
- `0x1770`
- `0x1780`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.0
0x1781  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1786  ldstr    aEditfiltertitl// "EditFilterTitle"
0x178b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1790  ldstr    aInlineeditcont// "InlineEditControls.EditFilterControl.La"...
0x1795  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x179a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x179f  ldarg.0
0x17a0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17a5  ldstr    aEditfiltererro// "EditFilterErrorNoEntity"
0x17aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17af  ldstr    aInlineeditcont_0// "InlineEditControls.EditFilterControl.Er"...
0x17b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x17be  ldarg.0
0x17bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17c4  ldstr    aEditfilterfilt// "EditFilterFilterExits"
0x17c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17ce  ldstr    aInlineeditcont_1// "InlineEditControls.EditFilterControl.Fi"...
0x17d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x17dd  ldarg.0
0x17de  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17e3  ldstr    aEditfilterrequ// "EditFilterRequiredFields"
0x17e8  ldarg.0
0x17e9  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_EditFilterRequiredFields()
0x17ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x17f3  ldarg.0
0x17f4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17f9  ldstr    aDefaultentityn// "DefaultEntityName"
0x17fe  ldarg.0
0x17ff  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_DefaultEntityName()
0x1804  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1809  ldarg.0
0x180a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x180f  ldstr    aEntityfieldcon// "EntityFieldControlId"
0x1814  ldarg.0
0x1815  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_EntityFieldControlId()
0x181a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x181f  ldarg.0
0x1820  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_FormDataControl()
0x1825  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x182a  brfalse.s loc_1847
0x182c  ldarg.0
0x182d  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_FormDataControl()
0x1832  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1837  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x183c  dup
0x183d  brtrue.s loc_185C
0x183f  pop
0x1840  ldsfld   string [mscorlib]System.String::Empty
0x1845  br.s     loc_185C
0x1847  ldstr    aUnbound// "unbound_"
0x184c  ldarg.0
0x184d  call     instance class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EditFilterControl::get_FormDataControl()
0x1852  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1857  call     string [mscorlib]System.String::Concat(string, string)
0x185c  stloc.0
0x185d  ldarg.1
0x185e  ldstr    aSpan// "span"
0x1863  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1868  ldarg.1
0x1869  ldstr    aContenteditabl// "contentEditable"
0x186e  ldstr    aFalse// "false"
0x1873  ldc.i4.0
0x1874  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1879  ldstr    aId// "id"
0x187e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1883  ldstr    a0Valuespan// "{0}_valueSpan"
0x1888  ldc.i4.1
0x1889  newarr   [mscorlib]System.Object
0x188e  dup
0x188f  ldc.i4.0
0x1890  ldarg.0
0x1891  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1896  stelem.ref
0x1897  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x189c  ldarg.1
0x189d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18a2  ldarg.1
0x18a3  ldc.i4.s 0x3E
0x18a5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x18aa  ldarg.1
0x18ab  ldstr    asc_2FDC8// "--"
0x18b0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18b5  ldarg.1
0x18b6  ldstr    aSpan// "span"
0x18bb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x18c0  ldarg.1
0x18c1  ldstr    aDiv// "div"
0x18c6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x18cb  ldarg.1
0x18cc  ldstr    aClass// "class"
0x18d1  ldstr    aMsCrmInlineEdi// "ms-crm-Inline-EditIcon"
0x18d6  ldc.i4.0
0x18d7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x18dc  ldarg.1
0x18dd  ldc.i4.s 0x3E
0x18df  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x18e4  ldarg.1
0x18e5  ldstr    aImg// "img"
0x18ea  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x18ef  ldstr    aId// "id"
0x18f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f9  ldstr    a0I// "{0}_i"
0x18fe  ldc.i4.1
0x18ff  newarr   [mscorlib]System.Object
0x1904  dup
0x1905  ldc.i4.0
0x1906  ldarg.0
0x1907  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x190c  stelem.ref
0x190d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1912  ldarg.1
0x1913  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1918  ldarg.1
0x1919  ldstr    aSrc// "src"
0x191e  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1923  ldc.i4.1
0x1924  newarr   [mscorlib]System.Char
0x1929  dup
0x192a  ldc.i4.0
0x192b  ldc.i4.s 0x2F
0x192d  stelem.i2
0x192e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1933  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x1938  call     string [mscorlib]System.String::Concat(string, string)
0x193d  ldc.i4.0
0x193e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1943  ldarg.1
0x1944  ldstr    aStyle// "style"
0x1949  ldstr    aDisplayBlockCu// "display :block; cursor:pointer; margin-"...
0x194e  ldc.i4.0
0x194f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1954  ldarg.1
0x1955  ldstr    aClass// "class"
0x195a  ldstr    aMsCrmImagestri// "ms-crm-ImageStrip-grid_filter"
0x195f  ldc.i4.0
0x1960  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1965  ldarg.1
0x1966  ldstr    aStyle// "style"
0x196b  ldstr    aDisplayBlockBa// "display :block; background : transparen"...
0x1970  ldc.i4.0
0x1971  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1976  ldstr    aAttrname// "attrname"
0x197b  ldloc.0
0x197c  ldarg.1
0x197d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1982  ldarg.1
0x1983  ldstr    aAlt// "alt"
0x1988  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x198d  ldstr    aInlineeditcont// "InlineEditControls.EditFilterControl.La"...
0x1992  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1997  ldc.i4.0
0x1998  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x199d  ldarg.1
0x199e  ldstr    aClass// "class"
0x19a3  ldstr    aMsCrmInlineloo// "ms-crm-InlineLookupEdit"
0x19a8  ldc.i4.0
0x19a9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x19ae  ldarg.1
0x19af  ldc.i4.s 0x3E
0x19b1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x19b6  ldarg.1
0x19b7  ldstr    aImg// "img"
0x19bc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x19c1  ldarg.1
0x19c2  ldstr    aDiv// "div"
0x19c7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x19cc  ret
```
