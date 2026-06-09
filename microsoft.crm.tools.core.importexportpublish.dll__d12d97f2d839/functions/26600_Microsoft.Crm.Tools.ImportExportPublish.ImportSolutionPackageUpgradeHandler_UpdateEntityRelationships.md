# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateEntityRelationships

- ea: `0x26600`
- end: `0x2666b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateEntityRelationships`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x25f70`

## callees

- `0x270c0`

## string_xrefs

- `0x26619`: `CascadeDelete`
- `0x2664a`: `CascadeDelete`
- `0x2662a`: `CascadeLinkMask`
- `0x2665b`: `CascadeLinkMask`

## pseudocode

```c

```

## disassembly

```asm
0x26600  ldc.i4.2
0x26601  newarr   [mscorlib]System.String
0x26606  dup
0x26607  ldc.i4.0
0x26608  ldstr    aLkLeadtoopport// "lk_leadtoopportunitysalesprocess_leadid"
0x2660d  stelem.ref
0x2660e  dup
0x2660f  ldc.i4.1
0x26610  ldstr    aLkPhonetocasep// "lk_phonetocaseprocess_incidentid"
0x26615  stelem.ref
0x26616  stloc.0
0x26617  ldarg.0
0x26618  ldloc.0
0x26619  ldstr    aCascadedelete_0// "CascadeDelete"
0x2661e  ldstr    a1// "1"
0x26623  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationships(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityRelationshipNames, string propertyName, string value)
0x26628  ldarg.0
0x26629  ldloc.0
0x2662a  ldstr    aCascadelinkmas_0// "CascadeLinkMask"
0x2662f  ldstr    a1// "1"
0x26634  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationships(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityRelationshipNames, string propertyName, string value)
0x26639  ldc.i4.1
0x2663a  newarr   [mscorlib]System.String
0x2663f  dup
0x26640  ldc.i4.0
0x26641  ldstr    aProductOpportu// "product_opportunities"
0x26646  stelem.ref
0x26647  stloc.0
0x26648  ldarg.0
0x26649  ldloc.0
0x2664a  ldstr    aCascadedelete_0// "CascadeDelete"
0x2664f  ldstr    a1// "1"
0x26654  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationships(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityRelationshipNames, string propertyName, string value)
0x26659  ldarg.0
0x2665a  ldloc.0
0x2665b  ldstr    aCascadelinkmas_0// "CascadeLinkMask"
0x26660  ldstr    a257// "257"
0x26665  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntityRelationships(class [System.Xml]System.Xml.XmlDocument customizationDoc, string[] entityRelationshipNames, string propertyName, string value)
0x2666a  ret
```
