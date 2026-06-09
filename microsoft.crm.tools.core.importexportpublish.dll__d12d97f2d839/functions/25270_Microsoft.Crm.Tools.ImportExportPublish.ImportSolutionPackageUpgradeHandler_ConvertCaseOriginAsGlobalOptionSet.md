# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::ConvertCaseOriginAsGlobalOptionSet

- ea: `0x25270`
- end: `0x256be`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::ConvertCaseOriginAsGlobalOptionSet`
- size: `1102`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x25270`
- `0x511e0`
- `0x63db0`
- `0x94fa0`

## string_xrefs

- `0x2555e`: `Templates`
- `0x25630`: `ImportExportXml/SolutionManifest/RootComponents`
- `0x2563b`: `RootComponent`
- `0x2556e`: `RibbonDiffXml`
- `0x25271`: `ImportExportXml/Entities/Entity/EntityInfo/entity[@Name='Incident']/attributes/attribute[@PhysicalName='CaseOriginCode']/optionset`
- `0x253ef`: `ImportExportXml/optionsets`
- `0x25548`: `FieldSecurityProfiles`
- `0x2557e`: `IsvConfig`

## pseudocode

```c

```

## disassembly

```asm
0x25270  ldarg.1
0x25271  ldstr    aImportexportxm_77// "ImportExportXml/Entities/Entity/EntityI"...
0x25276  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2527b  stloc.0
0x2527c  ldloc.0
0x2527d  brfalse  loc_2569B
0x25282  ldloc.0
0x25283  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25288  ldstr    aName_1// "Name"
0x2528d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25292  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x25297  stloc.1
0x25298  ldarg.s  5
0x2529a  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x2529f  stloc.2
0x252a0  ldnull
0x252a1  stloc.3
0x252a2  ldnull
0x252a3  stloc.s  4
0x252a5  ldarg.s  7
0x252a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x252ac  ldloc.1
0x252ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(string)
0x252b2  stloc.s  5
0x252b4  ldloc.s  5
0x252b6  brfalse.s loc_252C1
0x252b8  ldloc.s  5
0x252ba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_IsGlobal()
0x252bf  brtrue.s loc_252C2
0x252c1  ret
0x252c2  ldnull
0x252c3  stloc.s  6
0x252c5  ldloc.s  5
0x252c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_DisplayNames()
0x252cc  ldloc.2
0x252cd  ldarg.s  5
0x252cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x252d4  stloc.s  6
0x252d6  ldloc.s  6
0x252d8  brfalse.s loc_252E2
0x252da  ldloc.s  6
0x252dc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x252e1  stloc.3
0x252e2  ldloc.s  5
0x252e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Descriptions()
0x252e9  ldloc.2
0x252ea  ldarg.s  5
0x252ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x252f1  stloc.s  6
0x252f3  ldloc.s  6
0x252f5  brfalse.s loc_25300
0x252f7  ldloc.s  6
0x252f9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x252fe  stloc.s  4
0x25300  ldloc.0
0x25301  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25306  ldstr    aLocalizedname_0// "localizedName"
0x2530b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25310  stloc.s  7
0x25312  ldloc.s  7
0x25314  brtrue.s loc_25331
0x25316  ldarg.1
0x25317  ldstr    aLocalizedname_0// "localizedName"
0x2531c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x25321  stloc.s  7
0x25323  ldloc.0
0x25324  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25329  ldloc.s  7
0x2532b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x25330  pop
0x25331  ldloc.s  7
0x25333  ldloc.3
0x25334  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x25339  ldloc.0
0x2533a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2533f  ldstr    aDescription// "description"
0x25344  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25349  stloc.s  8
0x2534b  ldloc.s  8
0x2534d  brtrue.s loc_2536A
0x2534f  ldarg.1
0x25350  ldstr    aDescription// "description"
0x25355  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x2535a  stloc.s  8
0x2535c  ldloc.0
0x2535d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25362  ldloc.s  8
0x25364  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x25369  pop
0x2536a  ldloc.s  8
0x2536c  ldloc.s  4
0x2536e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x25373  ldarg.1
0x25374  ldstr    aOptionsetname// "OptionSetName"
0x25379  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2537e  stloc.s  9
0x25380  ldloc.s  9
0x25382  ldloc.1
0x25383  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x25388  ldloc.0
0x25389  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x2538e  ldloc.s  9
0x25390  ldloc.0
0x25391  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x25396  pop
0x25397  ldloc.0
0x25398  ldstr    aIsglobal// "IsGlobal"
0x2539d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x253a2  stloc.s  0xA
0x253a4  ldloc.s  0xA
0x253a6  brtrue.s loc_253E2
0x253a8  ldarg.1
0x253a9  ldstr    aIsglobal// "IsGlobal"
0x253ae  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x253b3  stloc.s  0xA
0x253b5  ldloc.0
0x253b6  ldstr    aOptionsettype// "OptionSetType"
0x253bb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x253c0  stloc.s  0xF
0x253c2  ldloc.s  0xF
0x253c4  brfalse.s loc_253D3
0x253c6  ldloc.0
0x253c7  ldloc.s  0xA
0x253c9  ldloc.s  0xF
0x253cb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertAfter(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x253d0  pop
0x253d1  br.s     loc_253E2
0x253d3  ldloc.0
0x253d4  ldloc.s  0xA
0x253d6  ldloc.0
0x253d7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x253dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x253e1  pop
0x253e2  ldloc.s  0xA
0x253e4  ldstr    a1// "1"
0x253e9  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x253ee  ldarg.1
0x253ef  ldstr    aImportexportxm_78// "ImportExportXml/optionsets"
0x253f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x253f9  isinst   [System.Xml]System.Xml.XmlElement
0x253fe  stloc.s  0xB
0x25400  ldloc.s  0xB
0x25402  brtrue   loc_25626
0x25407  ldarg.1
0x25408  ldstr    aOptionsets_0// "optionsets"
0x2540d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x25412  stloc.s  0xB
0x25414  ldnull
0x25415  stloc.s  0x10
0x25417  ldarg.1
0x25418  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2541d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x25422  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x25427  stloc.s  0x11
0x25429  br       loc_255DE
0x2542e  ldloc.s  0x11
0x25430  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x25435  castclass [System.Xml]System.Xml.XmlNode
0x2543a  stloc.s  0x12
0x2543c  ldloc.s  0x12
0x2543e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x25443  stloc.s  0x13
0x25445  ldloc.s  0x13
0x25447  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2544c  stloc.s  0x14
0x2544e  ldloc.s  0x14
0x25450  ldc.i4   0x3E77CE7E
0x25455  bgt.un.s loc_254AF
0x25457  ldloc.s  0x14
0x25459  ldc.i4   0x256EC50B
0x2545e  bgt.un.s loc_25489
0x25460  ldloc.s  0x14
0x25462  ldc.i4   0x1838400A
0x25467  beq      loc_25504
0x2546c  ldloc.s  0x14
0x2546e  ldc.i4   0x195BACE9
0x25473  beq      loc_255BC
0x25478  ldloc.s  0x14
0x2547a  ldc.i4   0x256EC50B
0x2547f  beq      loc_2556C
0x25484  br       loc_255DE
0x25489  ldloc.s  0x14
0x2548b  ldc.i4   0x3924C282
0x25490  beq      loc_2559C
0x25495  ldloc.s  0x14
0x25497  ldc.i4   0x3AD7388B
0x2549c  beq      loc_2557C
0x254a1  ldloc.s  0x14
0x254a3  ldc.i4   0x3E77CE7E
0x254a8  beq.s    loc_2551A
0x254aa  br       loc_255DE
0x254af  ldloc.s  0x14
0x254b1  ldc.i4   0x8A185E86
0x254b6  bgt.un.s loc_254DE
0x254b8  ldloc.s  0x14
0x254ba  ldc.i4   0x43CAFB88
0x254bf  beq      loc_2555C
0x254c4  ldloc.s  0x14
0x254c6  ldc.i4   0x7DDECB63
0x254cb  beq.s    loc_25546
0x254cd  ldloc.s  0x14
0x254cf  ldc.i4   0x8A185E86
0x254d4  beq      loc_255CC
0x254d9  br       loc_255DE
0x254de  ldloc.s  0x14
0x254e0  ldc.i4   0xE1333584
0x254e5  beq      loc_2558C
0x254ea  ldloc.s  0x14
0x254ec  ldc.i4   0xE23D5661
0x254f1  beq.s    loc_25530
0x254f3  ldloc.s  0x14
0x254f5  ldc.i4   0xFF063348
0x254fa  beq      loc_255AC
0x254ff  br       loc_255DE
0x25504  ldloc.s  0x13
0x25506  ldstr    aEntities_0// "Entities"
0x2550b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25510  brtrue   loc_255DA
0x25515  br       loc_255DE
0x2551a  ldloc.s  0x13
0x2551c  ldstr    aRoles// "Roles"
0x25521  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25526  brtrue   loc_255DA
0x2552b  br       loc_255DE
0x25530  ldloc.s  0x13
0x25532  ldstr    aWorkflows// "Workflows"
0x25537  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2553c  brtrue   loc_255DA
0x25541  br       loc_255DE
0x25546  ldloc.s  0x13
0x25548  ldstr    aFieldsecurityp_1// "FieldSecurityProfiles"
0x2554d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25552  brtrue   loc_255DA
0x25557  br       loc_255DE
0x2555c  ldloc.s  0x13
0x2555e  ldstr    aTemplates// "Templates"
0x25563  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25568  brtrue.s loc_255DA
0x2556a  br.s     loc_255DE
0x2556c  ldloc.s  0x13
0x2556e  ldstr    aRibbondiffxml// "RibbonDiffXml"
0x25573  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25578  brtrue.s loc_255DA
0x2557a  br.s     loc_255DE
0x2557c  ldloc.s  0x13
0x2557e  ldstr    aIsvconfig// "IsvConfig"
0x25583  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25588  brtrue.s loc_255DA
0x2558a  br.s     loc_255DE
0x2558c  ldloc.s  0x13
0x2558e  ldstr    aRelationshipro// "RelationshipRoles"
0x25593  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25598  brtrue.s loc_255DA
0x2559a  br.s     loc_255DE
0x2559c  ldloc.s  0x13
0x2559e  ldstr    aConnectionrole_2// "ConnectionRoles"
0x255a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x255a8  brtrue.s loc_255DA
0x255aa  br.s     loc_255DE
0x255ac  ldloc.s  0x13
0x255ae  ldstr    aSitemap// "SiteMap"
0x255b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x255b8  brtrue.s loc_255DA
0x255ba  br.s     loc_255DE
0x255bc  ldloc.s  0x13
0x255be  ldstr    aEntityrelation_19// "EntityRelationships"
0x255c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x255c8  brtrue.s loc_255DA
0x255ca  br.s     loc_255DE
0x255cc  ldloc.s  0x13
0x255ce  ldstr    aOrganizationse// "OrganizationSetting"
0x255d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x255d8  brfalse.s loc_255DE
0x255da  ldloc.s  0x12
0x255dc  stloc.s  0x10
0x255de  ldloc.s  0x11
0x255e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x255e5  brtrue   loc_2542E
0x255ea  leave.s  loc_25601
0x255ec  ldloc.s  0x11
0x255ee  isinst   [mscorlib]System.IDisposable
0x255f3  stloc.s  0x15
0x255f5  ldloc.s  0x15
0x255f7  brfalse.s loc_25600
0x255f9  ldloc.s  0x15
0x255fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25600  endfinally
0x25601  ldloc.s  0x10
0x25603  brfalse.s loc_25612
0x25605  ldarg.1
0x25606  ldloc.s  0xB
0x25608  ldloc.s  0x10
0x2560a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertAfter(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x2560f  pop
0x25610  br.s     loc_25626
0x25612  ldarg.1
0x25613  ldloc.s  0xB
0x25615  ldarg.1
0x25616  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2561b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
  ... truncated ...
```
