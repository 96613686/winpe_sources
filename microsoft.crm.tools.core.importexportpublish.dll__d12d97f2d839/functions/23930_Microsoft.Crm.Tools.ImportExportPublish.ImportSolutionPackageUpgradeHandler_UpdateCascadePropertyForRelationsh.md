# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateCascadePropertyForRelationshipHandler

- ea: `0x23930`
- end: `0x23aba`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateCascadePropertyForRelationshipHandler`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x23930`

## string_xrefs

- `0x239b7`: `ImportExportXml/EntityRelationships/EntityRelationship[@Name='`
- `0x239fe`: `ImportExportXml/EntityRelationships/EntityRelationship[@Name='`
- `0x23a3b`: `ImportExportXml/EntityRelationships/EntityRelationship[@Name='`
- `0x23a75`: `ImportExportXml/EntityRelationships/EntityRelationship[@Name='`
- `0x23a04`: `']/CascadeDelete`
- `0x23a41`: `']/CascadeDelete`
- `0x23a7b`: `']/CascadeDelete`
- `0x23a20`: `RemoveLink`
- `0x23a5a`: `RemoveLink`
- `0x23958`: `slabase_businesshoursid`
- `0x239a2`: `slabase_businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x23930  ldc.i4.5
0x23931  newarr   [mscorlib]System.String
0x23936  dup
0x23937  ldc.i4.0
0x23938  ldstr    aLeadQualifying// "lead_qualifying_opportunity"
0x2393d  stelem.ref
0x2393e  dup
0x2393f  ldc.i4.1
0x23940  ldstr    aAccountEntitle// "account_entitlement_Customer"
0x23945  stelem.ref
0x23946  dup
0x23947  ldc.i4.2
0x23948  ldstr    aContactEntitle// "contact_entitlement_Customer"
0x2394d  stelem.ref
0x2394e  dup
0x2394f  ldc.i4.3
0x23950  ldstr    aSystemuserEmai// "SystemUser_Email_EmailSender"
0x23955  stelem.ref
0x23956  dup
0x23957  ldc.i4.4
0x23958  ldstr    aSlabaseBusines// "slabase_businesshoursid"
0x2395d  stelem.ref
0x2395e  stloc.1
0x2395f  ldc.i4.0
0x23960  stloc.2
0x23961  br       loc_23AB0
0x23966  ldloc.1
0x23967  ldloc.2
0x23968  ldelem.ref
0x23969  stloc.3
0x2396a  ldloc.3
0x2396b  ldstr    aLeadQualifying// "lead_qualifying_opportunity"
0x23970  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23975  brtrue.s loc_239B6
0x23977  ldloc.3
0x23978  ldstr    aAccountEntitle// "account_entitlement_Customer"
0x2397d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23982  brtrue.s loc_239FD
0x23984  ldloc.3
0x23985  ldstr    aContactEntitle// "contact_entitlement_Customer"
0x2398a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2398f  brtrue.s loc_239FD
0x23991  ldloc.3
0x23992  ldstr    aSystemuserEmai// "SystemUser_Email_EmailSender"
0x23997  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2399c  brtrue   loc_23A3A
0x239a1  ldloc.3
0x239a2  ldstr    aSlabaseBusines// "slabase_businesshoursid"
0x239a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x239ac  brtrue   loc_23A74
0x239b1  br       loc_23AAC
0x239b6  ldarg.1
0x239b7  ldstr    aImportexportxm_54// "ImportExportXml/EntityRelationships/Ent"...
0x239bc  ldloc.3
0x239bd  ldstr    aCascadeassign_1// "']/CascadeAssign"
0x239c2  call     string [mscorlib]System.String::Concat(string, string, string)
0x239c7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x239cc  stloc.s  4
0x239ce  ldloc.s  4
0x239d0  brfalse  loc_23AAC
0x239d5  ldloc.s  4
0x239d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x239dc  ldstr    aCascade// "Cascade"
0x239e1  ldc.i4.5
0x239e2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x239e7  brtrue   loc_23AAC
0x239ec  ldloc.s  4
0x239ee  ldstr    aNocascade// "NoCascade"
0x239f3  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x239f8  br       loc_23AAC
0x239fd  ldarg.1
0x239fe  ldstr    aImportexportxm_54// "ImportExportXml/EntityRelationships/Ent"...
0x23a03  ldloc.3
0x23a04  ldstr    aCascadedelete_1// "']/CascadeDelete"
0x23a09  call     string [mscorlib]System.String::Concat(string, string, string)
0x23a0e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x23a13  stloc.0
0x23a14  ldloc.0
0x23a15  brfalse  loc_23AAC
0x23a1a  ldloc.0
0x23a1b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x23a20  ldstr    aRemovelink// "RemoveLink"
0x23a25  ldc.i4.5
0x23a26  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x23a2b  brtrue.s loc_23AAC
0x23a2d  ldloc.0
0x23a2e  ldstr    aRestrict// "Restrict"
0x23a33  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x23a38  br.s     loc_23AAC
0x23a3a  ldarg.1
0x23a3b  ldstr    aImportexportxm_54// "ImportExportXml/EntityRelationships/Ent"...
0x23a40  ldloc.3
0x23a41  ldstr    aCascadedelete_1// "']/CascadeDelete"
0x23a46  call     string [mscorlib]System.String::Concat(string, string, string)
0x23a4b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x23a50  stloc.0
0x23a51  ldloc.0
0x23a52  brfalse.s loc_23AAC
0x23a54  ldloc.0
0x23a55  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x23a5a  ldstr    aRemovelink// "RemoveLink"
0x23a5f  ldc.i4.5
0x23a60  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x23a65  brtrue.s loc_23AAC
0x23a67  ldloc.0
0x23a68  ldstr    aNocascade// "NoCascade"
0x23a6d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x23a72  br.s     loc_23AAC
0x23a74  ldarg.1
0x23a75  ldstr    aImportexportxm_54// "ImportExportXml/EntityRelationships/Ent"...
0x23a7a  ldloc.3
0x23a7b  ldstr    aCascadedelete_1// "']/CascadeDelete"
0x23a80  call     string [mscorlib]System.String::Concat(string, string, string)
0x23a85  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x23a8a  stloc.0
0x23a8b  ldloc.0
0x23a8c  brfalse.s loc_23AAC
0x23a8e  ldloc.0
0x23a8f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x23a94  ldstr    aNocascade// "NoCascade"
0x23a99  ldc.i4.5
0x23a9a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x23a9f  brtrue.s loc_23AAC
0x23aa1  ldloc.0
0x23aa2  ldstr    aRestrict// "Restrict"
0x23aa7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x23aac  ldloc.2
0x23aad  ldc.i4.1
0x23aae  add
0x23aaf  stloc.2
0x23ab0  ldloc.2
0x23ab1  ldloc.1
0x23ab2  ldlen
0x23ab3  conv.i4
0x23ab4  blt      loc_23966
0x23ab9  ret
```
