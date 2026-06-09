# Microsoft.Crm.Application.Forms.EndUserForm::RenderFormSubmitFields

- ea: `0x2b100`
- end: `0x2b347`
- name: `Microsoft.Crm.Application.Forms.EndUserForm::RenderFormSubmitFields`
- size: `583`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc830`
- `0x2b410`
- `0x2dc00`
- `0x2dca0`
- `0x2f9d0`
- `0x32a10`
- `0x3b940`

## callees

- `0x26370`
- `0x26440`
- `0x264c0`
- `0x265f0`
- `0x2b100`
- `0x2b350`
- `0x2b390`

## string_xrefs

- `0x2b158`: `crmFormOriginalXml`
- `0x2b108`: `<input type="hidden" name="crmFormSubmitXml" id="crmFormSubmitXml" />`
- `0x2b183`: `<input type="hidden" id="crmFormOriginalXml" name="crmFormOriginalXml"`
- `0x2b291`: `<input type="hidden" name="crmFormSubmitSecurity" id="crmFormSubmitSecurity" value="`

## pseudocode

```c

```

## disassembly

```asm
0x2b100  ldarg.1
0x2b101  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2b106  stloc.0
0x2b107  ldloc.0
0x2b108  ldstr    aInputTypeHidde_7// "<input type=\"hidden\" name=\"crmFormSu"...
0x2b10d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b112  ldloc.0
0x2b113  ldstr    aInputTypeHidde_8// "<input type=\"hidden\" name=\"crmFormSu"...
0x2b118  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b11d  ldloc.0
0x2b11e  ldstr    aInputTypeHidde_9// "<input type=\"hidden\" id=\"crmFormSubm"...
0x2b123  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b128  ldstr    aValue// "value"
0x2b12d  ldarg.0
0x2b12e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b133  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x2b138  ldarg.1
0x2b139  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2b13e  ldloc.0
0x2b13f  ldstr    asc_1234C6// " />"
0x2b144  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b149  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2b14e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2b153  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2b158  ldstr    aCrmformorigina// "crmFormOriginalXml"
0x2b15d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2b162  stloc.1
0x2b163  ldarg.0
0x2b164  call     instance bool Microsoft.Crm.Application.Forms.AppForm::get_ErrorDuringSave()
0x2b169  brfalse.s loc_2B176
0x2b16b  ldloc.1
0x2b16c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b171  brtrue.s loc_2B176
0x2b173  ldloc.1
0x2b174  br.s     loc_2B181
0x2b176  ldarg.0
0x2b177  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b17c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x2b181  stloc.2
0x2b182  ldloc.0
0x2b183  ldstr    aInputTypeHidde_10// "<input type=\"hidden\" id=\"crmFormOrig"...
0x2b188  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b18d  ldstr    aValue// "value"
0x2b192  ldloc.2
0x2b193  ldarg.1
0x2b194  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2b199  ldloc.0
0x2b19a  ldstr    asc_1234C6// " />"
0x2b19f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b1a4  ldloc.0
0x2b1a5  ldstr    aInputTypeHidde_11// "<input type=\"hidden\" name=\"crmFormUs"...
0x2b1aa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b1af  ldstr    aValue// "value"
0x2b1b4  ldarg.0
0x2b1b5  ldfld    bool Microsoft.Crm.Application.Forms.EndUserForm::_userHasModifiedForm
0x2b1ba  brtrue.s loc_2B1C3
0x2b1bc  ldstr    aFalse// "false"
0x2b1c1  br.s     loc_2B1C8
0x2b1c3  ldstr    aTrue// "true"
0x2b1c8  ldarg.1
0x2b1c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2b1ce  ldloc.0
0x2b1cf  ldstr    asc_1234C6// " />"
0x2b1d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b1d9  ldloc.0
0x2b1da  ldstr    aInputTypeHidde_12// "<input type=\"hidden\" name=\"crmFormSu"...
0x2b1df  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b1e4  ldloc.0
0x2b1e5  ldarg.0
0x2b1e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b1eb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x2b1f0  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x2b1f5  stloc.3
0x2b1f6  ldloca.s 3
0x2b1f8  ldstr    aD// "D"
0x2b1fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b202  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2b207  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b20c  ldloc.0
0x2b20d  ldstr    asc_1236A2// "\" />"
0x2b212  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b217  ldloc.0
0x2b218  ldstr    aInputTypeHidde_13// "<input type=\"hidden\" id=\"crmFormSubm"...
0x2b21d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b222  ldstr    aValue// "value"
0x2b227  ldarg.0
0x2b228  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b22d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x2b232  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2b237  ldarg.1
0x2b238  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2b23d  ldloc.0
0x2b23e  ldstr    asc_1234C6// " />"
0x2b243  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b248  ldarg.0
0x2b249  call     instance bool Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x2b24e  brtrue.s loc_2B25D
0x2b250  ldarg.0
0x2b251  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b256  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x2b25b  brfalse.s loc_2B276
0x2b25d  ldarg.0
0x2b25e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x2b263  ldc.i4.2
0x2b264  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::Remove(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x2b269  ldarg.0
0x2b26a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x2b26f  ldc.i4.s 0x20
0x2b271  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::Remove(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x2b276  ldarg.0
0x2b277  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x2b27c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x2b281  brfalse.s loc_2B290
0x2b283  ldarg.0
0x2b284  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x2b289  ldc.i4.s 0x10
0x2b28b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::Remove(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x2b290  ldloc.0
0x2b291  ldstr    aInputTypeHidde_14// "<input type=\"hidden\" name=\"crmFormSu"...
0x2b296  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b29b  ldloc.0
0x2b29c  ldarg.0
0x2b29d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x2b2a2  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CheckAccessRights()
0x2b2a7  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x2b2ac  ldstr    aD// "D"
0x2b2b1  call     instance string [mscorlib]System.Enum::ToString(string)
0x2b2b6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b2bb  ldloc.0
0x2b2bc  ldstr    asc_F5D2A// "\">"
0x2b2c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b2c6  ldloc.0
0x2b2c7  ldstr    aInputTypeHidde_15// "<input type=\"hidden\" name=\"crmFormSu"...
0x2b2cc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b2d1  ldloc.0
0x2b2d2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x2b2d7  brtrue.s loc_2B2E0
0x2b2d9  ldstr    a0// "0"
0x2b2de  br.s     loc_2B2E5
0x2b2e0  ldstr    a1_0// "1"
0x2b2e5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b2ea  ldloc.0
0x2b2eb  ldstr    asc_1236A2// "\" />"
0x2b2f0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b2f5  ldarg.0
0x2b2f6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.EndUserForm::_mappedDataRemainder
0x2b2fb  brfalse.s loc_2B338
0x2b2fd  ldloc.0
0x2b2fe  ldstr    aInputTypeHidde_16// "<input type=\"hidden\" id=\"crmFormSubm"...
0x2b303  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b308  ldstr    aValue// "value"
0x2b30d  ldarg.0
0x2b30e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.EndUserForm::_mappedDataRemainder
0x2b313  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x2b318  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2b31d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2b322  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x2b327  ldarg.1
0x2b328  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2b32d  ldloc.0
0x2b32e  ldstr    asc_1234C6// " />"
0x2b333  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2b338  ldarg.0
0x2b339  ldarg.1
0x2b33a  callvirt instance void Microsoft.Crm.Application.Forms.EndUserForm::RenderWrpcTokenAsHiddenInput(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2b33f  ldarg.0
0x2b340  ldarg.1
0x2b341  callvirt instance void Microsoft.Crm.Application.Forms.EndUserForm::RenderSolutionId(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2b346  ret
```
