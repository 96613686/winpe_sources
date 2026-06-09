# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::SetAndValidateObjectTypeCode

- ea: `0x3ad0`
- end: `0x3b0d`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::SetAndValidateObjectTypeCode`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3920`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  ldarg.0
0x3ad1  ldarg.0
0x3ad2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3ad7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3adc  ldstr    aObjecttypecode_0// "objectTypeCode"
0x3ae1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3ae6  ldc.i4.7
0x3ae7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3aec  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x3af1  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3af6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3afb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b00  ldarg.0
0x3b01  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3b06  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3b0b  pop
0x3b0c  ret
```
