# Microsoft.Crm.Common.Application.Pages.MA.DynamicListQueryPage::ConfigureForm

- ea: `0x16c00`
- end: `0x16ce7`
- name: `Microsoft.Crm.Common.Application.Pages.MA.DynamicListQueryPage::ConfigureForm`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16c00`

## string_xrefs

- `0x16cbd`: `DynamicListQueryPage.ConfigureForm There was an error while trying to execute the list query addition code.\nError Message: {0}\nStack Trace:\n {1}`

## pseudocode

```c

```

## disassembly

```asm
0x16c00  ldarg.0
0x16c01  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16c06  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x16c0b  ldsfld   string [mscorlib]System.String::Empty
0x16c10  stloc.0
0x16c11  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x16c16  ldc.i4.0
0x16c17  conv.i8
0x16c18  ble      loc_16CE6
0x16c1d  ldarg.0
0x16c1e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16c23  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16c28  ldstr    aItemobjectid// "itemObjectId"
0x16c2d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16c32  ldnull
0x16c33  cgt.un
0x16c35  ldstr    aListShouldBeVa// "List should be valid"
0x16c3a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x16c3f  ldstr    aList// "list"
0x16c44  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16c49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16c4e  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x16c53  dup
0x16c54  ldarg.0
0x16c55  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16c5a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16c5f  ldstr    aItemobjectid// "itemObjectId"
0x16c64  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16c69  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x16c6e  ldarg.0
0x16c6f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16c74  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x16c79  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [mscorlib]System.IO.Stream)
0x16c7e  ldstr    aRootFetch// "//root/fetch"
0x16c83  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16c88  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x16c8d  stloc.0
0x16c8e  dup
0x16c8f  ldstr    aQuery// "query"
0x16c94  ldloc.0
0x16c95  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x16c9a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x16c9f  ldarg.0
0x16ca0  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x16ca5  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x16caa  leave.s  loc_16CE6
0x16cac  stloc.1
0x16cad  ldloc.1
0x16cae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16cb3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x16cb8  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x16cbd  ldstr    aDynamiclistque// "DynamicListQueryPage.ConfigureForm Ther"...
0x16cc2  ldc.i4.2
0x16cc3  newarr   [mscorlib]System.Object
0x16cc8  dup
0x16cc9  ldc.i4.0
0x16cca  ldloc.1
0x16ccb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16cd0  stelem.ref
0x16cd1  dup
0x16cd2  ldc.i4.1
0x16cd3  ldloc.1
0x16cd4  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x16cd9  stelem.ref
0x16cda  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16cdf  ldloc.1
0x16ce0  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x16ce5  throw
0x16ce6  ret
```
