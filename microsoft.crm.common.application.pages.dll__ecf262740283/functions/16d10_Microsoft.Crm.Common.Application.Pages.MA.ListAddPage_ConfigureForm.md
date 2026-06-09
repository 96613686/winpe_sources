# Microsoft.Crm.Common.Application.Pages.MA.ListAddPage::ConfigureForm

- ea: `0x16d10`
- end: `0x16ff2`
- name: `Microsoft.Crm.Common.Application.Pages.MA.ListAddPage::ConfigureForm`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16d10`
- `0x1de50`

## string_xrefs

- `0x16fc5`: `ListAddPage.ConfigureForm There was an error while trying to execute the list members addition code.\nError Message: {0}\nStack Trace:\n {1}`

## pseudocode

```c

```

## disassembly

```asm
0x16d10  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x16d15  stloc.0
0x16d16  ldloc.0
0x16d17  ldarg.0
0x16d18  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16d1d  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x16d22  stfld    class [mscorlib]System.IO.Stream <>c__DisplayClass2_0::inputStream
0x16d27  ldsfld   string [mscorlib]System.String::Empty
0x16d2c  stloc.1
0x16d2d  ldsfld   string [mscorlib]System.String::Empty
0x16d32  stloc.2
0x16d33  ldloc.0
0x16d34  ldfld    class [mscorlib]System.IO.Stream <>c__DisplayClass2_0::inputStream
0x16d39  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x16d3e  ldc.i4.0
0x16d3f  conv.i8
0x16d40  ble      loc_16FF1
0x16d45  ldarg.0
0x16d46  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16d4b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16d50  ldstr    aItemobjectid// "itemObjectId"
0x16d55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16d5a  ldnull
0x16d5b  cgt.un
0x16d5d  ldstr    aListShouldBeVa// "List should be valid"
0x16d62  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x16d67  ldarg.0
0x16d68  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16d6d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16d72  ldstr    aIoption// "iOption"
0x16d77  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16d7c  ldnull
0x16d7d  cgt.un
0x16d7f  ldstr    aInvalidOptionC// "Invalid option chosen"
0x16d84  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x16d89  ldarg.0
0x16d8a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16d8f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16d94  ldstr    aIsdirty// "isDirty"
0x16d99  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16d9e  ldnull
0x16d9f  cgt.un
0x16da1  ldstr    aInvalidParamet// "Invalid parameter"
0x16da6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x16dab  ldstr    aList// "list"
0x16db0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16db5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16dba  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x16dbf  stloc.3
0x16dc0  ldarg.0
0x16dc1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16dc6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16dcb  ldstr    aItemobjectid// "itemObjectId"
0x16dd0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16dd5  stloc.s  4
0x16dd7  ldarg.0
0x16dd8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16ddd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16de2  ldstr    aIoption// "iOption"
0x16de7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16dec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16df1  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x16df6  stloc.s  5
0x16df8  ldloc.0
0x16df9  ldftn    instance class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass2_0::<ConfigureForm>b__0()
0x16dff  newobj   instance void class [mscorlib]System.Func`1<class [System.Xml]System.Xml.XmlDocument>::.ctor(object, native int)
0x16e04  ldc.i4.0
0x16e05  newobj   instance void class [mscorlib]System.Lazy`1<class [System.Xml]System.Xml.XmlDocument>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x16e0a  stloc.s  6
0x16e0c  ldnull
0x16e0d  stloc.s  7
0x16e0f  ldc.i4.0
0x16e10  stloc.s  8
0x16e12  ldarg.0
0x16e13  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16e18  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16e1d  ldstr    aItotal// "iTotal"
0x16e22  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16e27  ldstr    a0// "0"
0x16e2c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x16e31  brfalse.s loc_16EB1
0x16e33  ldloc.s  5
0x16e35  ldc.i4.1
0x16e36  bne.un.s loc_16EB1
0x16e38  ldloc.s  6
0x16e3a  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System.Xml]System.Xml.XmlDocument>::get_Value()
0x16e3f  ldstr    aRootIdsId// "//root/Ids/Id"
0x16e44  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x16e49  stloc.s  0xA
0x16e4b  ldloc.s  0xA
0x16e4d  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x16e52  newarr   [mscorlib]System.String
0x16e57  stloc.s  7
0x16e59  ldloc.s  0xA
0x16e5b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x16e60  stloc.s  0xB
0x16e62  br.s     loc_16E83
0x16e64  ldloc.s  0xB
0x16e66  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x16e6b  castclass [System.Xml]System.Xml.XmlNode
0x16e70  stloc.s  0xC
0x16e72  ldloc.s  7
0x16e74  ldloc.s  8
0x16e76  dup
0x16e77  ldc.i4.1
0x16e78  add
0x16e79  stloc.s  8
0x16e7b  ldloc.s  0xC
0x16e7d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x16e82  stelem.ref
0x16e83  ldloc.s  0xB
0x16e85  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16e8a  brtrue.s loc_16E64
0x16e8c  leave.s  loc_16EA3
0x16e8e  ldloc.s  0xB
0x16e90  isinst   [mscorlib]System.IDisposable
0x16e95  stloc.s  0xD
0x16e97  ldloc.s  0xD
0x16e99  brfalse.s loc_16EA2
0x16e9b  ldloc.s  0xD
0x16e9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ea2  endfinally
0x16ea3  leave.s  loc_16EB1
0x16ea5  ldloc.s  0xA
0x16ea7  brfalse.s loc_16EB0
0x16ea9  ldloc.s  0xA
0x16eab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16eb0  endfinally
0x16eb1  ldstr    aFalse// "false"
0x16eb6  stloc.s  9
0x16eb8  ldarg.0
0x16eb9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16ebe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16ec3  ldstr    aIsdirty// "isDirty"
0x16ec8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16ecd  stloc.s  9
0x16ecf  ldloc.s  9
0x16ed1  ldstr    aTrue// "true"
0x16ed6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16edb  brfalse.s loc_16EF6
0x16edd  ldloc.s  6
0x16edf  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System.Xml]System.Xml.XmlDocument>::get_Value()
0x16ee4  ldstr    aRootFetch// "//root/fetch"
0x16ee9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16eee  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x16ef3  stloc.1
0x16ef4  br.s     loc_16F0C
0x16ef6  ldarg.0
0x16ef7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16efc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16f01  ldstr    aSavedqueryid// "savedQueryId"
0x16f06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16f0b  stloc.2
0x16f0c  ldloc.s  5
0x16f0e  ldc.i4.1
0x16f0f  bne.un.s loc_16F58
0x16f11  ldc.i4.0
0x16f12  stloc.s  0xE
0x16f14  br.s     loc_16F50
0x16f16  ldloc.s  7
0x16f18  ldloc.s  0xE
0x16f1a  ldelem.ref
0x16f1b  callvirt instance string [mscorlib]System.Object::ToString()
0x16f20  ldc.i4.1
0x16f21  newarr   [mscorlib]System.Char
0x16f26  dup
0x16f27  ldc.i4.0
0x16f28  ldc.i4.s 0x2C
0x16f2a  stelem.i2
0x16f2b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16f30  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ConvertStringArrayToGuidArray(string[])
0x16f35  stloc.s  0xF
0x16f37  ldloc.s  4
0x16f39  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x16f3e  ldloc.s  0xF
0x16f40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16f45  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersList(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16f4a  ldloc.s  0xE
0x16f4c  ldc.i4.1
0x16f4d  add
0x16f4e  stloc.s  0xE
0x16f50  ldloc.s  0xE
0x16f52  ldloc.s  7
0x16f54  ldlen
0x16f55  conv.i4
0x16f56  blt.s    loc_16F16
0x16f58  ldloc.s  5
0x16f5a  ldc.i4.2
0x16f5b  bne.un.s loc_16FA5
0x16f5d  ldloc.s  9
0x16f5f  ldstr    aTrue// "true"
0x16f64  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x16f69  brfalse.s loc_16F9C
0x16f6b  ldloc.2
0x16f6c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x16f71  ldarg.0
0x16f72  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16f77  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16f7c  ldstr    aSavedquerytype// "savedQueryType"
0x16f81  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16f86  ldc.i4.7
0x16f87  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16f8c  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x16f91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x16f96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0x16f9b  stloc.1
0x16f9c  ldloc.3
0x16f9d  ldloc.s  4
0x16f9f  ldloc.1
0x16fa0  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::AddMembersByFetchXml(string, string)
0x16fa5  ldarg.0
0x16fa6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x16fab  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x16fb0  leave.s  loc_16FF1
0x16fb2  stloc.s  0x10
0x16fb4  ldloc.s  0x10
0x16fb6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16fbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x16fc0  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x16fc5  ldstr    aListaddpageCon// "ListAddPage.ConfigureForm There was an "...
0x16fca  ldc.i4.2
0x16fcb  newarr   [mscorlib]System.Object
0x16fd0  dup
0x16fd1  ldc.i4.0
0x16fd2  ldloc.s  0x10
0x16fd4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16fd9  stelem.ref
0x16fda  dup
0x16fdb  ldc.i4.1
0x16fdc  ldloc.s  0x10
0x16fde  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x16fe3  stelem.ref
0x16fe4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16fe9  ldloc.s  0x10
0x16feb  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x16ff0  throw
0x16ff1  ret
```
