# Microsoft.Crm.Common.Application.Pages.Common.Icon::ConfigurePage

- ea: `0x1bfa0`
- end: `0x1c109`
- name: `Microsoft.Crm.Common.Application.Pages.Common.Icon::ConfigurePage`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1bfa0`
- `0x1c110`

## string_xrefs

- `0x1c0a1`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x1bfa0  ldarg.0
0x1bfa1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bfa6  call     int32 [Microsoft.Crm]Microsoft.Crm.CachingTime::get_ExtendedExpiration()
0x1bfab  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x1bfb0  ldarg.0
0x1bfb1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1bfb6  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1bfbb  ldc.i4.4
0x1bfbc  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1bfc1  ldarg.0
0x1bfc2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1bfc7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bfcc  ldstr    aObjecttypecode// "objectTypeCode"
0x1bfd1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bfd6  stloc.0
0x1bfd7  ldarg.0
0x1bfd8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1bfdd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bfe2  ldstr    aEtn// "etn"
0x1bfe7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bfec  stloc.1
0x1bfed  ldloc.0
0x1bfee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bff3  brfalse.s loc_1C000
0x1bff5  ldloc.1
0x1bff6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bffb  ldc.i4.0
0x1bffc  ceq
0x1bffe  br.s     loc_1C001
0x1c000  ldc.i4.1
0x1c001  ldstr    aMustProvideEit// "Must provide either object type code or"...
0x1c006  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1c00b  ldnull
0x1c00c  stloc.2
0x1c00d  ldloc.0
0x1c00e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c013  brtrue.s loc_1C032
0x1c015  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c01a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c01f  ldloc.0
0x1c020  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c025  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1c02a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x1c02f  stloc.2
0x1c030  br.s     loc_1C044
0x1c032  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c037  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c03c  ldloc.1
0x1c03d  ldc.i4.1
0x1c03e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1c043  stloc.2
0x1c044  ldloc.2
0x1c045  ldnull
0x1c046  cgt.un
0x1c048  ldstr    aEntityMetadata// "Entity Metadata not found."
0x1c04d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1c052  ldarg.0
0x1c053  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1c058  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1c05d  ldstr    aIcontype// "iconType"
0x1c062  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c067  stloc.3
0x1c068  ldloc.3
0x1c069  ldstr    aIcontype// "iconType"
0x1c06e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1c073  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType
0x1c078  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c07d  ldloc.3
0x1c07e  ldc.i4.1
0x1c07f  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x1c084  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType
0x1c089  stloc.s  4
0x1c08b  ldloc.s  4
0x1c08d  ldc.i4.2
0x1c08e  bne.un.s loc_1C093
0x1c090  ldc.i4.0
0x1c091  stloc.s  4
0x1c093  ldc.i4.1
0x1c094  stloc.s  5
0x1c096  ldarg.0
0x1c097  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1c09c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1c0a1  ldstr    aCache// "cache"
0x1c0a6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c0ab  stloc.s  6
0x1c0ad  ldloc.s  6
0x1c0af  brfalse.s loc_1C0CC
0x1c0b1  ldloc.s  6
0x1c0b3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1c0b8  ldc.i4.0
0x1c0b9  ble.s    loc_1C0CC
0x1c0bb  ldloc.s  6
0x1c0bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c0c2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1c0c7  brtrue.s loc_1C0CC
0x1c0c9  ldc.i4.0
0x1c0ca  stloc.s  5
0x1c0cc  ldarg.0
0x1c0cd  ldloc.2
0x1c0ce  ldloc.s  4
0x1c0d0  ldloca.s 7
0x1c0d2  call     instance unsigned int8[] Microsoft.Crm.Common.Application.Pages.Common.Icon::GetIconBits(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata em, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType iconType, [out] string& contentType)
0x1c0d7  stloc.s  8
0x1c0d9  ldloc.s  5
0x1c0db  brtrue.s loc_1C0EE
0x1c0dd  ldarg.0
0x1c0de  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c0e3  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c0e8  ldc.i4.1
0x1c0e9  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x1c0ee  ldarg.0
0x1c0ef  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c0f4  ldloc.s  7
0x1c0f6  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1c0fb  ldarg.0
0x1c0fc  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c101  ldloc.s  8
0x1c103  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0x1c108  ret
```
