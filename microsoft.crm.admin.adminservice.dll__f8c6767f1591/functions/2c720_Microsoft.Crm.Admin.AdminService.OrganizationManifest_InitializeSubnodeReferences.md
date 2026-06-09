# Microsoft.Crm.Admin.AdminService.OrganizationManifest::InitializeSubnodeReferences

- ea: `0x2c720`
- end: `0x2c773`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationManifest::InitializeSubnodeReferences`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2bf60`
- `0x2bfb0`

## callees

- `0x2c720`
- `0x2c780`

## string_xrefs

- `0x2c727`: `/OrganizationManifest/Version`
- `0x2c73e`: `Organization Manifest lacks a Version element`
- `0x2c767`: `Organization Manifest lacks a Version element`
- `0x2c750`: `/OrganizationManifest/TableRows`

## pseudocode

```c

```

## disassembly

```asm
0x2c720  ldarg.0
0x2c721  ldarg.0
0x2c722  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Admin.AdminService.OrganizationManifest::_doc
0x2c727  ldstr    aOrganizationma// "/OrganizationManifest/Version"
0x2c72c  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::SelectSingletonElement(class [System.Xml]System.Xml.XmlNode baseNode, string XPathQuery)
0x2c731  stfld    class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::_versionElem
0x2c736  ldarg.0
0x2c737  ldfld    class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::_versionElem
0x2c73c  brtrue.s loc_2C749
0x2c73e  ldstr    aOrganizationMa_0// "Organization Manifest lacks a Version e"...
0x2c743  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2c748  throw
0x2c749  ldarg.0
0x2c74a  ldarg.0
0x2c74b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Admin.AdminService.OrganizationManifest::_doc
0x2c750  ldstr    aOrganizationma_0// "/OrganizationManifest/TableRows"
0x2c755  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::SelectSingletonElement(class [System.Xml]System.Xml.XmlNode baseNode, string XPathQuery)
0x2c75a  stfld    class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::_rowsElem
0x2c75f  ldarg.0
0x2c760  ldfld    class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Admin.AdminService.OrganizationManifest::_rowsElem
0x2c765  brtrue.s loc_2C772
0x2c767  ldstr    aOrganizationMa_0// "Organization Manifest lacks a Version e"...
0x2c76c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2c771  throw
0x2c772  ret
```
