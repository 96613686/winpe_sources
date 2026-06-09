# Microsoft.Crm.Application.Forms.FollowUpFormCell::Render

- ea: `0x3bba0`
- end: `0x3be01`
- name: `Microsoft.Crm.Application.Forms.FollowUpFormCell::Render`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3bb60`
- `0x3bb80`
- `0x3bba0`
- `0xdff00`

## string_xrefs

- `0x3bc5b`: `ms-crm-Field-Recommended`
- `0x3bd34`: `Forms.Recommended.AltTag`
- `0x3bd5e`: `/_imgs/frm_recommended.gif`

## pseudocode

```c

```

## disassembly

```asm
0x3bba0  ldarg.1
0x3bba1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x3bba6  stloc.0
0x3bba7  ldarg.0
0x3bba8  call     instance bool Microsoft.Crm.Application.Forms.FollowUpFormCell::get_ShowLabel()
0x3bbad  brfalse  loc_3BD9C
0x3bbb2  ldarg.0
0x3bbb3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x3bbb8  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x3bbbd  ldc.i4.0
0x3bbbe  bgt.s    loc_3BBC3
0x3bbc0  ldnull
0x3bbc1  br.s     loc_3BBCF
0x3bbc3  ldarg.0
0x3bbc4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x3bbc9  ldc.i4.0
0x3bbca  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0x3bbcf  stloc.1
0x3bbd0  ldloc.1
0x3bbd1  brtrue.s loc_3BBD6
0x3bbd3  ldnull
0x3bbd4  br.s     loc_3BBDC
0x3bbd6  ldloc.1
0x3bbd7  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x3bbdc  stloc.2
0x3bbdd  ldloc.0
0x3bbde  ldstr    aTdValignTop_0// "<td valign=\"top\" "
0x3bbe3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bbe8  ldloc.0
0x3bbe9  ldstr    aId_3// "id=\""
0x3bbee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bbf3  ldloc.1
0x3bbf4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x3bbf9  ldstr    aC// "_c"
0x3bbfe  call     string [mscorlib]System.String::Concat(string, string)
0x3bc03  ldloc.0
0x3bc04  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x3bc09  ldloc.0
0x3bc0a  ldstr    aClass_2// "\" class=\""
0x3bc0f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bc14  ldarg.0
0x3bc15  ldfld    bool Microsoft.Crm.Application.Forms.FollowUpFormCell::_requiredLevelOverriden
0x3bc1a  brtrue.s loc_3BC30
0x3bc1c  ldloc.2
0x3bc1d  brfalse.s loc_3BC30
0x3bc1f  ldarg.0
0x3bc20  ldloc.2
0x3bc21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3bc26  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3bc2b  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FollowUpFormCell::_requiredLevel
0x3bc30  ldarg.0
0x3bc31  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FollowUpFormCell::get_RequiredLevel()
0x3bc36  stloc.3
0x3bc37  ldloc.3
0x3bc38  ldc.i4.1
0x3bc39  sub
0x3bc3a  switch   loc_3BC4D, loc_3BC4D, loc_3BC5A
0x3bc4b  br.s     loc_3BC67
0x3bc4d  ldloc.0
0x3bc4e  ldstr    aMsCrmFieldRequ// "ms-crm-Field-Required"
0x3bc53  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bc58  br.s     loc_3BC72
0x3bc5a  ldloc.0
0x3bc5b  ldstr    aMsCrmFieldReco// "ms-crm-Field-Recommended"
0x3bc60  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bc65  br.s     loc_3BC72
0x3bc67  ldloc.0
0x3bc68  ldstr    aMsCrmFieldNorm// "ms-crm-Field-Normal"
0x3bc6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bc72  ldloc.0
0x3bc73  ldstr    aLabelFor// "\"><label for=\""
0x3bc78  ldloc.1
0x3bc79  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x3bc7e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3bc83  ldstr    asc_F5D2A// "\">"
0x3bc88  call     string [mscorlib]System.String::Concat(string, string, string)
0x3bc8d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bc92  ldloc.0
0x3bc93  ldarg.0
0x3bc94  ldfld    string Microsoft.Crm.Application.Forms.FollowUpFormCell::_label
0x3bc99  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3bc9e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bca3  ldarg.0
0x3bca4  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FollowUpFormCell::get_RequiredLevel()
0x3bca9  stloc.3
0x3bcaa  ldloc.3
0x3bcab  ldc.i4.1
0x3bcac  sub
0x3bcad  switch   loc_3BCC3, loc_3BCC3, loc_3BD1F
0x3bcbe  br       loc_3BD79
0x3bcc3  ldloc.0
0x3bcc4  ldstr    aImg// "<img "
0x3bcc9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bcce  ldstr    aAlt// "alt"
0x3bcd3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3bcd8  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x3bcdd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bce2  ldarg.1
0x3bce3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3bce8  ldstr    aSrc// "src"
0x3bced  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3bcf2  ldc.i4.1
0x3bcf3  newarr   [mscorlib]System.Char
0x3bcf8  dup
0x3bcf9  ldc.i4.0
0x3bcfa  ldc.i4.s 0x2F
0x3bcfc  stelem.i2
0x3bcfd  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3bd02  ldstr    aImgsFrmRequire// "/_imgs/frm_required.gif"
0x3bd07  call     string [mscorlib]System.String::Concat(string, string)
0x3bd0c  ldarg.1
0x3bd0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3bd12  ldloc.0
0x3bd13  ldstr    asc_111DE8// "/>"
0x3bd18  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bd1d  br.s     loc_3BD79
0x3bd1f  ldloc.0
0x3bd20  ldstr    aImg// "<img "
0x3bd25  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bd2a  ldstr    aAlt// "alt"
0x3bd2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3bd34  ldstr    aFormsRecommend// "Forms.Recommended.AltTag"
0x3bd39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bd3e  ldarg.1
0x3bd3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3bd44  ldstr    aSrc// "src"
0x3bd49  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3bd4e  ldc.i4.1
0x3bd4f  newarr   [mscorlib]System.Char
0x3bd54  dup
0x3bd55  ldc.i4.0
0x3bd56  ldc.i4.s 0x2F
0x3bd58  stelem.i2
0x3bd59  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3bd5e  ldstr    aImgsFrmRecomme// "/_imgs/frm_recommended.gif"
0x3bd63  call     string [mscorlib]System.String::Concat(string, string)
0x3bd68  ldarg.1
0x3bd69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3bd6e  ldloc.0
0x3bd6f  ldstr    asc_111DE8// "/>"
0x3bd74  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bd79  ldloc.0
0x3bd7a  ldstr    aLabel_0// "</label>"
0x3bd7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bd84  ldarg.1
0x3bd85  ldloc.1
0x3bd86  ldarg.0
0x3bd87  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FollowUpFormCell::get_RequiredLevel()
0x3bd8c  call     void Microsoft.Crm.Application.Components.Utility.SharedMethods::RenderRequiredLevelHiddenLabel(class [System.Web]System.Web.UI.HtmlTextWriter output, class [System.Web]System.Web.UI.Control childControl, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel requiredLevel)
0x3bd91  ldloc.0
0x3bd92  ldstr    aTdTrTr// "</td></tr><tr>"
0x3bd97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bd9c  ldloc.0
0x3bd9d  ldstr    aTd_2// "<td>"
0x3bda2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3bda7  ldarg.0
0x3bda8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x3bdad  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x3bdb2  stloc.s  4
0x3bdb4  br.s     loc_3BDD5
0x3bdb6  ldloc.s  4
0x3bdb8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3bdbd  castclass [System.Web]System.Web.UI.Control
0x3bdc2  stloc.s  5
0x3bdc4  ldloc.s  5
0x3bdc6  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x3bdcb  brfalse.s loc_3BDD5
0x3bdcd  ldloc.s  5
0x3bdcf  ldarg.1
0x3bdd0  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x3bdd5  ldloc.s  4
0x3bdd7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3bddc  brtrue.s loc_3BDB6
0x3bdde  leave.s  loc_3BDF5
0x3bde0  ldloc.s  4
0x3bde2  isinst   [mscorlib]System.IDisposable
0x3bde7  stloc.s  6
0x3bde9  ldloc.s  6
0x3bdeb  brfalse.s loc_3BDF4
0x3bded  ldloc.s  6
0x3bdef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3bdf4  endfinally
0x3bdf5  ldloc.0
0x3bdf6  ldstr    aTd// "</td>"
0x3bdfb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3be00  ret
```
