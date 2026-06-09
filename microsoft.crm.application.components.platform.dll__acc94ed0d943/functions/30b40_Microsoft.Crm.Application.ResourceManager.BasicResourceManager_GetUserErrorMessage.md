# Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetUserErrorMessage

- ea: `0x30b40`
- end: `0x30cbc`
- name: `Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetUserErrorMessage`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x302f0`

## callees

- `0x10040`
- `0x10080`
- `0x100d0`
- `0x12c40`
- `0x30240`
- `0x30870`
- `0x30b40`

## string_xrefs

- `0x30b79`: `<A target="_blank" href="{0}" class="ms-crm-Link">{1}</A>`
- `0x30c1d`: `<A target="_blank" href="{0}" class="ms-crm-Link">{1}</A>`
- `0x30c0b`: `CRM_Outlook_Client_Latest_Version_Download_Link`
- `0x30c2b`: `CRM_Outlook_Client_Latest_Version_Download_Link`

## pseudocode

```c

```

## disassembly

```asm
0x30b40  ldsfld   string [mscorlib]System.String::Empty
0x30b45  stloc.0
0x30b46  newobj   instance void Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x30b4b  ldarg.1
0x30b4c  ldarg.3
0x30b4d  call     instance class Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Errors.ErrorLookup::GetError(string errorCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30b52  stloc.1
0x30b53  ldc.i4   0x80048293
0x30b58  ldloc.1
0x30b59  callvirt instance int32 Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x30b5e  bne.un   loc_30BF7
0x30b63  ldarg.2
0x30b64  brtrue.s loc_30B74
0x30b66  ldarg.0
0x30b67  ldstr    aCrmDynamicsSan// "CRM_Dynamics_Sandboxing"
0x30b6c  ldarg.3
0x30b6d  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30b72  br.s     loc_30BB1
0x30b74  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30b79  ldstr    aATargetBlankHr// "<A target=\"_blank\" href=\"{0}\" class"...
0x30b7e  ldc.i4.2
0x30b7f  newarr   [mscorlib]System.Object
0x30b84  dup
0x30b85  ldc.i4.0
0x30b86  ldarg.0
0x30b87  ldstr    aCrmDynamicsSan_0// "CRM_Dynamics_Sandboxing_Address"
0x30b8c  ldarg.3
0x30b8d  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30b92  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x30b97  stelem.ref
0x30b98  dup
0x30b99  ldc.i4.1
0x30b9a  ldarg.0
0x30b9b  ldstr    aCrmDynamicsSan// "CRM_Dynamics_Sandboxing"
0x30ba0  ldarg.3
0x30ba1  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30ba6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x30bab  stelem.ref
0x30bac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30bb1  stloc.2
0x30bb2  ldarg.0
0x30bb3  ldstr    aErrorMessageSa// "Error_Message_Sandboxing_Instruction"
0x30bb8  ldarg.3
0x30bb9  ldc.i4.1
0x30bba  newarr   [mscorlib]System.Object
0x30bbf  dup
0x30bc0  ldc.i4.0
0x30bc1  ldloc.2
0x30bc2  stelem.ref
0x30bc3  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x30bc8  stloc.3
0x30bc9  ldarg.0
0x30bca  ldstr    aErrorMessageSa_0// "Error_Message_Sandboxing"
0x30bcf  ldarg.3
0x30bd0  ldc.i4.2
0x30bd1  newarr   [mscorlib]System.Object
0x30bd6  dup
0x30bd7  ldc.i4.0
0x30bd8  ldloc.3
0x30bd9  stelem.ref
0x30bda  dup
0x30bdb  ldc.i4.1
0x30bdc  ldarg.2
0x30bdd  brtrue.s loc_30BE6
0x30bdf  ldsfld   string [mscorlib]System.String::Empty
0x30be4  br.s     loc_30BEB
0x30be6  ldstr    aBrBr// "<br><br>"
0x30beb  stelem.ref
0x30bec  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x30bf1  stloc.0
0x30bf2  br       loc_30CBA
0x30bf7  ldc.i4   0x80044203
0x30bfc  ldloc.1
0x30bfd  callvirt instance int32 Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x30c02  bne.un   loc_30C8A
0x30c07  ldarg.2
0x30c08  brtrue.s loc_30C18
0x30c0a  ldarg.0
0x30c0b  ldstr    aCrmOutlookClie// "CRM_Outlook_Client_Latest_Version_Downl"...
0x30c10  ldarg.3
0x30c11  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30c16  br.s     loc_30C55
0x30c18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30c1d  ldstr    aATargetBlankHr// "<A target=\"_blank\" href=\"{0}\" class"...
0x30c22  ldc.i4.2
0x30c23  newarr   [mscorlib]System.Object
0x30c28  dup
0x30c29  ldc.i4.0
0x30c2a  ldarg.0
0x30c2b  ldstr    aCrmOutlookClie// "CRM_Outlook_Client_Latest_Version_Downl"...
0x30c30  ldarg.3
0x30c31  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30c36  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x30c3b  stelem.ref
0x30c3c  dup
0x30c3d  ldc.i4.1
0x30c3e  ldarg.0
0x30c3f  ldstr    aBrandCrmTradem// "Brand_CRM_Trademark_Outlook_Full"
0x30c44  ldarg.3
0x30c45  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30c4a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x30c4f  stelem.ref
0x30c50  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30c55  stloc.s  4
0x30c57  ldarg.0
0x30c58  ldstr    aErrorMessage0x_0// "Error_Message_0x"
0x30c5d  ldarg.1
0x30c5e  call     string [mscorlib]System.String::Concat(string, string)
0x30c63  ldarg.3
0x30c64  ldc.i4.2
0x30c65  newarr   [mscorlib]System.Object
0x30c6a  dup
0x30c6b  ldc.i4.0
0x30c6c  ldarg.3
0x30c6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x30c72  call     class [mscorlib]System.Version Microsoft.Crm.Caching.CrmVersion::GetCrmVersionByOrganization(valuetype [mscorlib]System.Guid organizationId)
0x30c77  callvirt instance string [mscorlib]System.Object::ToString()
0x30c7c  stelem.ref
0x30c7d  dup
0x30c7e  ldc.i4.1
0x30c7f  ldloc.s  4
0x30c81  stelem.ref
0x30c82  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x30c87  stloc.0
0x30c88  br.s     loc_30CBA
0x30c8a  ldarg.0
0x30c8b  ldstr    aErrorMessage0x_0// "Error_Message_0x"
0x30c90  ldarg.1
0x30c91  call     string [mscorlib]System.String::Concat(string, string)
0x30c96  ldarg.3
0x30c97  ldc.i4.2
0x30c98  newarr   [mscorlib]System.Object
0x30c9d  dup
0x30c9e  ldc.i4.0
0x30c9f  ldarg.s  4
0x30ca1  stelem.ref
0x30ca2  dup
0x30ca3  ldc.i4.1
0x30ca4  ldarg.2
0x30ca5  brtrue.s loc_30CAE
0x30ca7  ldsfld   string [mscorlib]System.String::Empty
0x30cac  br.s     loc_30CB3
0x30cae  ldstr    aBrBr// "<br><br>"
0x30cb3  stelem.ref
0x30cb4  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x30cb9  stloc.0
0x30cba  ldloc.0
0x30cbb  ret
```
