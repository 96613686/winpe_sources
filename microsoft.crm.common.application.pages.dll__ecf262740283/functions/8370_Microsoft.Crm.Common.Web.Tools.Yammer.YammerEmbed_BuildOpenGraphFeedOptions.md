# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildOpenGraphFeedOptions

- ea: `0x8370`
- end: `0x845f`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildOpenGraphFeedOptions`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8110`

## callees

- `0x7e30`
- `0x8370`
- `0x8460`
- `0x84a0`

## string_xrefs

- `0x83b2`: `feedType: "open-graph"`

## pseudocode

```c

```

## disassembly

```asm
0x8370  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8375  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x837a  ldarg.3
0x837b  ldc.i4.1
0x837c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8381  stloc.0
0x8382  ldloc.0
0x8383  brfalse  loc_8457
0x8388  ldarg.0
0x8389  ldarg.3
0x838a  call     instance string Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::GetOpenGraphType(string entityTypeName)
0x838f  stloc.1
0x8390  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8395  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x839a  ldarg.2
0x839b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x83a0  ldarg.3
0x83a1  call     string [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerCrmUtility::GetCrmEntityUrl(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string)
0x83a6  stloc.2
0x83a7  ldarg.1
0x83a8  ldstr    asc_25960// ", "
0x83ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83b2  ldstr    aFeedtypeOpenGr// "feedType: \"open-graph\""
0x83b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83bc  ldstr    asc_25960// ", "
0x83c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83c6  ldstr    aObjectproperti// "objectProperties: {"
0x83cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83d0  ldstr    aUrl0// "url: \"{0}\""
0x83d5  ldloc.2
0x83d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x83db  ldstr    asc_25960// ", "
0x83e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83e5  ldstr    aDescription// "description: \"\", "
0x83ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83ef  ldstr    aType0// "type: \"{0}\""
0x83f4  ldloc.1
0x83f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x83fa  pop
0x83fb  ldarg.0
0x83fc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8401  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8406  ldstr    aTitle// "title"
0x840b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8410  stloc.3
0x8411  ldloc.3
0x8412  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8417  brfalse.s loc_8426
0x8419  ldarg.2
0x841a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x841f  ldloc.0
0x8420  call     string Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::RetrieveTitle(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x8425  stloc.3
0x8426  ldloc.3
0x8427  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x842c  brtrue.s loc_844A
0x842e  ldarg.1
0x842f  ldstr    asc_25960// ", "
0x8434  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8439  ldstr    aTitle0// "title: {0}"
0x843e  ldloc.3
0x843f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8444  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x8449  pop
0x844a  ldarg.1
0x844b  ldstr    asc_25B1E// " }"
0x8450  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8455  pop
0x8456  ret
0x8457  ldarg.0
0x8458  ldc.i4.1
0x8459  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_NoConversations(bool value)
0x845e  ret
```
