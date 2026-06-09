# Microsoft.Crm.Extensibility.MetadataEndpointService::GenerateMetadata

- ea: `0x6aa0`
- end: `0x6b28`
- name: `Microsoft.Crm.Extensibility.MetadataEndpointService::GenerateMetadata`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x6b50`

## string_xrefs

- `0x6acf`: `D:\a\1\s\src\Extensibility\Sdk\MetadataEndpointService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6aa0  ldarg.1
0x6aa1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6aa6  ldc.i4.0
0x6aa7  ceq
0x6aa9  ldstr    aArgumentOrgani// "Argument organization name not passed i"...
0x6aae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6ab3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x6ab8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x6abd  ldarg.1
0x6abe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationId(string)
0x6ac3  ldstr    aS2srealm// "S2SRealm"
0x6ac8  ldc.i4.s 0x2C
0x6aca  ldstr    aGeneratemetada// "GenerateMetadata"
0x6acf  ldstr    aDA1SSrcExtensi// "D:\\a\\1\\s\\src\\Extensibility\\Sdk\\M"...
0x6ad4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x6ad9  isinst   [mscorlib]System.String
0x6ade  stloc.0
0x6adf  ldloc.0
0x6ae0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6ae5  ldc.i4.0
0x6ae6  ceq
0x6ae8  ldstr    aCrmRealmNotSet// "CRM realm not set in the organization t"...
0x6aed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6af2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6af7  ldstr    a01// "{0}@{1}"
0x6afc  ldc.i4.2
0x6afd  newarr   [mscorlib]System.Object
0x6b02  dup
0x6b03  ldc.i4.0
0x6b04  ldstr    a00000007000000// "00000007-0000-0000-c000-000000000000"
0x6b09  stelem.ref
0x6b0a  dup
0x6b0b  ldc.i4.1
0x6b0c  ldloc.0
0x6b0d  stelem.ref
0x6b0e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6b13  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore[] Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::GetSigningCertificates()
0x6b18  ldstr    a00000007000000// "00000007-0000-0000-c000-000000000000"
0x6b1d  ldstr    a00000007000000// "00000007-0000-0000-c000-000000000000"
0x6b22  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataEndpointObject::.ctor(string, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore[], string, string)
0x6b27  ret
```
