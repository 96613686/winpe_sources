# Microsoft.Crm.Tools.Admin.OrganizationOperation::get_ImportXmlFilePath

- ea: `0x9980`
- end: `0x99af`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::get_ImportXmlFilePath`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe360`

## callees

- `0x9120`
- `0x9980`
- `0xa550`

## string_xrefs

- `0x9999`: `9\ImportExport\newimport.xml`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.0
0x9981  ldfld    string Microsoft.Crm.Tools.Admin.OrganizationOperation::_importXmlFilePath
0x9986  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x998b  brfalse.s loc_99A8
0x998d  ldarg.0
0x998e  ldarg.0
0x998f  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::_organizationInfo
0x9994  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0x9999  ldstr    a9ImportexportN// "9\\ImportExport\\newimport.xml"
0x999e  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(int32 baseLanguageCode, string relativePath)
0x99a3  stfld    string Microsoft.Crm.Tools.Admin.OrganizationOperation::_importXmlFilePath
0x99a8  ldarg.0
0x99a9  ldfld    string Microsoft.Crm.Tools.Admin.OrganizationOperation::_importXmlFilePath
0x99ae  ret
```
