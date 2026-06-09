# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::AdjustCascadeDeletePropertyForParentalReflexiveRelationshipsHandler

- ea: `0x23850`
- end: `0x238db`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::AdjustCascadeDeletePropertyForParentalReflexiveRelationshipsHandler`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x23850`
- `0x63db0`

## string_xrefs

- `0x23878`: `ImportExportXml/EntityRelationships/EntityRelationship[@Name='`
- `0x2387e`: `']/CascadeDelete`
- `0x238a4`: `RemoveLink`

## pseudocode

```c

```

## disassembly

```asm
0x23850  ldc.i4.3
0x23851  newarr   [mscorlib]System.String
0x23856  dup
0x23857  ldc.i4.0
0x23858  ldstr    aAccountParentA// "account_parent_account"
0x2385d  stelem.ref
0x2385e  dup
0x2385f  ldc.i4.1
0x23860  ldstr    aContactCustome// "contact_customer_contacts"
0x23865  stelem.ref
0x23866  dup
0x23867  ldc.i4.2
0x23868  ldstr    aSubjectParentS// "subject_parent_subject"
0x2386d  stelem.ref
0x2386e  stloc.0
0x2386f  ldc.i4.0
0x23870  stloc.1
0x23871  br.s     loc_238B2
0x23873  ldloc.0
0x23874  ldloc.1
0x23875  ldelem.ref
0x23876  stloc.2
0x23877  ldarg.1
0x23878  ldstr    aImportexportxm_54// "ImportExportXml/EntityRelationships/Ent"...
0x2387d  ldloc.2
0x2387e  ldstr    aCascadedelete_1// "']/CascadeDelete"
0x23883  call     string [mscorlib]System.String::Concat(string, string, string)
0x23888  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2388d  stloc.3
0x2388e  ldloc.3
0x2388f  brfalse.s loc_238AE
0x23891  ldstr    aNocascade// "NoCascade"
0x23896  ldloc.3
0x23897  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2389c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x238a1  brfalse.s loc_238AE
0x238a3  ldloc.3
0x238a4  ldstr    aRemovelink// "RemoveLink"
0x238a9  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x238ae  ldloc.1
0x238af  ldc.i4.1
0x238b0  add
0x238b1  stloc.1
0x238b2  ldloc.1
0x238b3  ldloc.0
0x238b4  ldlen
0x238b5  conv.i4
0x238b6  blt.s    loc_23873
0x238b8  ldarg.s  6
0x238ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x238bf  ldstr    aExecutingSolut// "Executing solution package Upgrade hand"...
0x238c4  ldc.i4.1
0x238c5  newarr   [mscorlib]System.Object
0x238ca  dup
0x238cb  ldc.i4.0
0x238cc  ldarg.s  4
0x238ce  stelem.ref
0x238cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x238d4  ldc.i4.1
0x238d5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x238da  ret
```
