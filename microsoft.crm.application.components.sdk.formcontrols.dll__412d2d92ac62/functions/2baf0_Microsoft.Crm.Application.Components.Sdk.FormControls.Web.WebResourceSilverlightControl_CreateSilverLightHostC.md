# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::CreateSilverLightHostControl

- ea: `0x2baf0`
- end: `0x2beeb`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::CreateSilverLightHostControl`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x2bac0`

## callees

- `0x17990`
- `0x17a10`
- `0x2b220`
- `0x2b240`
- `0x2b260`
- `0x2b280`
- `0x2b2c0`
- `0x2b300`
- `0x2b380`
- `0x2ba90`
- `0x2baf0`
- `0x2bef0`
- `0x2bf00`

## string_xrefs

- `0x2bc25`: `enablehtmlaccess`
- `0x2be2b`: `<a id="{0}" href="{1}://go.microsoft.com/fwlink/?LinkID=124807" style="text-decoration: none;">`
- `0x2be3e`: `<img src="{0}://go.microsoft.com/fwlink/?LinkId=108181" alt="Get Microsoft Silverlight" style="border-style: none"/>`

## pseudocode

```c

```

## disassembly

```asm
0x2baf0  ldstr    aDiv// "div"
0x2baf5  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2bafa  stloc.0
0x2bafb  ldstr    aObject// "object"
0x2bb00  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2bb05  stloc.1
0x2bb06  ldloc.1
0x2bb07  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bb0c  ldstr    aData// "data"
0x2bb11  ldstr    aDataApplicatio// "data:application/x-silverlight,"
0x2bb16  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bb1b  ldloc.1
0x2bb1c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bb21  ldstr    aType// "type"
0x2bb26  ldstr    aApplicationXSi// "application/x-silverlight"
0x2bb2b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bb30  ldloc.1
0x2bb31  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bb36  ldstr    aResizemode// "resizeMode"
0x2bb3b  ldarg.0
0x2bb3c  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.WebResourceSizeType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_SizeType()
0x2bb41  stloc.s  5
0x2bb43  ldloca.s 5
0x2bb45  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.WebResourceSizeType
0x2bb4b  callvirt instance string [mscorlib]System.Object::ToString()
0x2bb50  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bb55  ldloc.1
0x2bb56  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bb5b  ldstr    aDesiredheight// "desiredHeight"
0x2bb60  ldarg.0
0x2bb61  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Height()
0x2bb66  stloc.s  6
0x2bb68  ldloca.s 6
0x2bb6a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bb6f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2bb74  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bb79  ldloc.1
0x2bb7a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bb7f  ldstr    aDesiredwidth// "desiredWidth"
0x2bb84  ldarg.0
0x2bb85  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Width()
0x2bb8a  stloc.s  6
0x2bb8c  ldloca.s 6
0x2bb8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bb93  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2bb98  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bb9d  ldloc.1
0x2bb9e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2bba3  ldstr    aTabindex// "tabindex"
0x2bba8  ldarg.0
0x2bba9  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2bbae  stloc.s  6
0x2bbb0  ldloca.s 6
0x2bbb2  ldstr    aD// "D"
0x2bbb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bbbc  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2bbc1  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2bbc6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2bbcb  stloc.2
0x2bbcc  ldloc.2
0x2bbcd  ldstr    aSource// "source"
0x2bbd2  ldarg.0
0x2bbd3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::GetWebResourceUrl()
0x2bbd8  callvirt instance string [mscorlib]System.Object::ToString()
0x2bbdd  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTag(string key, string value)
0x2bbe2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bbe7  pop
0x2bbe8  ldloc.2
0x2bbe9  ldstr    aMinruntimevers// "minRuntimeVersion"
0x2bbee  ldarg.0
0x2bbef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::GetWebResource()
0x2bbf4  ldstr    aSilverlightver// "silverlightversion"
0x2bbf9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2bbfe  castclass [mscorlib]System.String
0x2bc03  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTag(string key, string value)
0x2bc08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bc0d  pop
0x2bc0e  ldloc.2
0x2bc0f  ldstr    aIswindowless// "iswindowless"
0x2bc14  ldstr    aFalse// "false"
0x2bc19  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTag(string key, string value)
0x2bc1e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bc23  pop
0x2bc24  ldloc.2
0x2bc25  ldstr    aEnablehtmlacce// "enablehtmlaccess"
0x2bc2a  ldstr    aTrue// "true"
0x2bc2f  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTag(string key, string value)
0x2bc34  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bc39  pop
0x2bc3a  ldarg.0
0x2bc3b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::get_PassParameters()
0x2bc40  brfalse  loc_2BDD0
0x2bc45  ldsfld   string [mscorlib]System.String::Empty
0x2bc4a  stloc.s  7
0x2bc4c  ldsfld   string [mscorlib]System.String::Empty
0x2bc51  stloc.s  8
0x2bc53  ldsfld   string [mscorlib]System.String::Empty
0x2bc58  stloc.s  9
0x2bc5a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2bc5f  stloc.s  0xA
0x2bc61  ldarg.0
0x2bc62  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_UsedInReadForm()
0x2bc67  brfalse.s loc_2BCE0
0x2bc69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bc6e  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x2bc73  ldc.i4.2
0x2bc74  newarr   [mscorlib]System.Object
0x2bc79  dup
0x2bc7a  ldc.i4.0
0x2bc7b  ldstr    aEntity// "_entity"
0x2bc80  stelem.ref
0x2bc81  dup
0x2bc82  ldc.i4.1
0x2bc83  ldstr    aId_0// "Id"
0x2bc88  stelem.ref
0x2bc89  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2bc8e  stloc.s  7
0x2bc90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bc95  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x2bc9a  ldc.i4.2
0x2bc9b  newarr   [mscorlib]System.Object
0x2bca0  dup
0x2bca1  ldc.i4.0
0x2bca2  ldstr    aEntity// "_entity"
0x2bca7  stelem.ref
0x2bca8  dup
0x2bca9  ldc.i4.1
0x2bcaa  ldstr    aTypecode// "TypeCode"
0x2bcaf  stelem.ref
0x2bcb0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2bcb5  stloc.s  8
0x2bcb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bcbc  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x2bcc1  ldc.i4.2
0x2bcc2  newarr   [mscorlib]System.Object
0x2bcc7  dup
0x2bcc8  ldc.i4.0
0x2bcc9  ldstr    aEntity// "_entity"
0x2bcce  stelem.ref
0x2bccf  dup
0x2bcd0  ldc.i4.1
0x2bcd1  ldstr    aTypename// "TypeName"
0x2bcd6  stelem.ref
0x2bcd7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2bcdc  stloc.s  9
0x2bcde  br.s     loc_2BD39
0x2bce0  ldarg.0
0x2bce1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2bce6  brfalse.s loc_2BD39
0x2bce8  ldarg.0
0x2bce9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2bcee  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x2bcf3  brtrue.s loc_2BD02
0x2bcf5  ldarg.0
0x2bcf6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2bcfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x2bd00  stloc.s  7
0x2bd02  ldarg.0
0x2bd03  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2bd08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x2bd0d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2bd12  stloc.s  6
0x2bd14  ldloca.s 6
0x2bd16  ldstr    aD// "D"
0x2bd1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bd20  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2bd25  stloc.s  8
0x2bd27  ldarg.0
0x2bd28  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2bd2d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x2bd32  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2bd37  stloc.s  9
0x2bd39  ldloc.s  0xA
0x2bd3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bd40  ldstr    aId0Type1Typena// "id={0},type={1},typename={2},orgname={3"...
0x2bd45  ldc.i4.6
0x2bd46  newarr   [mscorlib]System.Object
0x2bd4b  dup
0x2bd4c  ldc.i4.0
0x2bd4d  ldloc.s  7
0x2bd4f  stelem.ref
0x2bd50  dup
0x2bd51  ldc.i4.1
0x2bd52  ldloc.s  8
0x2bd54  stelem.ref
0x2bd55  dup
0x2bd56  ldc.i4.2
0x2bd57  ldloc.s  9
0x2bd59  stelem.ref
0x2bd5a  dup
0x2bd5b  ldc.i4.3
0x2bd5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2bd61  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2bd66  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2bd6b  stelem.ref
0x2bd6c  dup
0x2bd6d  ldc.i4.4
0x2bd6e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2bd73  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2bd78  box      [mscorlib]System.Int32
0x2bd7d  stelem.ref
0x2bd7e  dup
0x2bd7f  ldc.i4.5
0x2bd80  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x2bd85  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x2bd8a  box      [mscorlib]System.Int32
0x2bd8f  stelem.ref
0x2bd90  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x2bd95  pop
0x2bd96  ldarg.0
0x2bd97  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Data()
0x2bd9c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bda1  brtrue.s loc_2BDB6
0x2bda3  ldloc.s  0xA
0x2bda5  ldstr    aData0// ",data={0}"
0x2bdaa  ldarg.0
0x2bdab  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Data()
0x2bdb0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x2bdb5  pop
0x2bdb6  ldloc.2
0x2bdb7  ldstr    aInitparams// "initParams"
0x2bdbc  ldloc.s  0xA
0x2bdbe  callvirt instance string [mscorlib]System.Object::ToString()
0x2bdc3  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTagNoEncodeValue(string key, string value)
0x2bdc8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bdcd  pop
0x2bdce  br.s     loc_2BE0C
0x2bdd0  ldarg.0
0x2bdd1  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Data()
0x2bdd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bddb  brtrue.s loc_2BE0C
0x2bddd  ldloc.2
0x2bdde  ldstr    aInitparams// "initParams"
0x2bde3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bde8  ldstr    aData0_0// "data={0}"
0x2bded  ldc.i4.1
0x2bdee  newarr   [mscorlib]System.Object
0x2bdf3  dup
0x2bdf4  ldc.i4.0
0x2bdf5  ldarg.0
0x2bdf6  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Data()
0x2bdfb  stelem.ref
0x2bdfc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2be01  call     string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceSilverlightControl::FormParameterTag(string key, string value)
0x2be06  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2be0b  pop
0x2be0c  ldstr    aHttp// "http"
0x2be11  stloc.3
0x2be12  ldarg.0
0x2be13  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2be18  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2be1d  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0x2be22  brfalse.s loc_2BE2A
0x2be24  ldstr    aHttps// "https"
0x2be29  stloc.3
0x2be2a  ldloc.2
0x2be2b  ldstr    aAId0Href1GoMic// "<a id=\"{0}\" href=\"{1}://go.microsoft"...
0x2be30  ldarg.0
0x2be31  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2be36  ldloc.3
0x2be37  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2be3c  pop
0x2be3d  ldloc.2
0x2be3e  ldstr    aImgSrc0GoMicro// "<img src=\"{0}://go.microsoft.com/fwlin"...
0x2be43  ldloc.3
0x2be44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x2be49  pop
0x2be4a  ldloc.1
0x2be4b  ldloc.2
0x2be4c  callvirt instance string [mscorlib]System.Object::ToString()
0x2be51  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x2be56  ldloc.1
0x2be57  ldarg.0
0x2be58  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2be5d  ldstr    aObject_0// "_object"
0x2be62  call     string [mscorlib]System.String::Concat(string, string)
0x2be67  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2be6c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2be71  stloc.s  4
0x2be73  ldloc.s  4
0x2be75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2be7a  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x2be7f  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x2be84  stloc.s  0xB
0x2be86  ldloc.1
0x2be87  ldloc.s  0xB
0x2be89  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x2be8e  ldloc.0
0x2be8f  ldloc.s  4
0x2be91  callvirt instance string [mscorlib]System.Object::ToString()
0x2be96  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x2be9b  ldloc.0
0x2be9c  ldarg.0
0x2be9d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2bea2  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2bea7  ldloc.0
0x2bea8  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x2bead  ldstr    aVisibility// "visibility"
0x2beb2  ldstr    aHidden// "hidden"
0x2beb7  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
  ... truncated ...
```
