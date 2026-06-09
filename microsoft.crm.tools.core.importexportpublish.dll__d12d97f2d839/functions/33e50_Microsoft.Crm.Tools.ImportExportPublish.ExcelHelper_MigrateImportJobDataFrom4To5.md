# Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::MigrateImportJobDataFrom4To5

- ea: `0x33e50`
- end: `0x3409d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::MigrateImportJobDataFrom4To5`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x33e50`
- `0x340a0`

## string_xrefs

- `0x33e58`: `importexportxml`
- `0x33e76`: `importexportxml/*/*`
- `0x33f24`: `template`
- `0x33f37`: `securityrole`
- `0x33fbf`: `securityrole`
- `0x33e64`: `solutionManifests`
- `0x34014`: `solutionManifests`
- `0x34028`: `solutionManifest`

## pseudocode

```c

```

## disassembly

```asm
0x33e50  ldarg.1
0x33e51  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x33e56  stloc.0
0x33e57  ldloc.0
0x33e58  ldstr    aImportexportxm_95// "importexportxml"
0x33e5d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x33e62  stloc.1
0x33e63  ldloc.1
0x33e64  ldstr    aSolutionmanife_0// "solutionManifests"
0x33e69  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x33e6e  stloc.2
0x33e6f  ldloc.2
0x33e70  brtrue   loc_3406C
0x33e75  ldloc.0
0x33e76  ldstr    aImportexportxm_97// "importexportxml/*/*"
0x33e7b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x33e80  stloc.3
0x33e81  ldloc.3
0x33e82  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x33e87  stloc.s  6
0x33e89  br       loc_33FF0
0x33e8e  ldloc.s  6
0x33e90  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x33e95  castclass [System.Xml]System.Xml.XmlNode
0x33e9a  stloc.s  7
0x33e9c  ldloc.s  7
0x33e9e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33ea3  stloc.s  8
0x33ea5  ldloc.s  7
0x33ea7  ldsfld   string [mscorlib]System.String::Empty
0x33eac  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x33eb1  ldloc.0
0x33eb2  ldstr    aResult// "result"
0x33eb7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x33ebc  stloc.s  9
0x33ebe  ldloc.s  7
0x33ec0  ldloc.s  9
0x33ec2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x33ec7  pop
0x33ec8  ldarg.0
0x33ec9  ldloc.0
0x33eca  ldloc.s  7
0x33ecc  ldloc.s  9
0x33ece  ldstr    aResult// "result"
0x33ed3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::MoveAttribute(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode node, class [System.Xml]System.Xml.XmlNode resultNode, string attributeName)
0x33ed8  ldarg.0
0x33ed9  ldloc.0
0x33eda  ldloc.s  7
0x33edc  ldloc.s  9
0x33ede  ldstr    aErrorcode_0// "errorcode"
0x33ee3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::MoveAttribute(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode node, class [System.Xml]System.Xml.XmlNode resultNode, string attributeName)
0x33ee8  ldarg.0
0x33ee9  ldloc.0
0x33eea  ldloc.s  7
0x33eec  ldloc.s  9
0x33eee  ldstr    aErrortext_0// "errortext"
0x33ef3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::MoveAttribute(class [System.Xml]System.Xml.XmlDocument doc, class [System.Xml]System.Xml.XmlNode node, class [System.Xml]System.Xml.XmlNode resultNode, string attributeName)
0x33ef8  ldloc.0
0x33ef9  ldstr    aId// "id"
0x33efe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x33f03  stloc.s  0xA
0x33f05  ldloc.s  0xA
0x33f07  ldloc.s  8
0x33f09  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x33f0e  ldloc.s  7
0x33f10  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33f15  ldloc.s  0xA
0x33f17  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x33f1c  pop
0x33f1d  ldloc.s  7
0x33f1f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33f24  ldstr    aTemplate_0// "template"
0x33f29  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33f2e  brtrue.s loc_33F59
0x33f30  ldloc.s  7
0x33f32  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33f37  ldstr    aSecurityrole_0// "securityrole"
0x33f3c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33f41  brtrue.s loc_33F59
0x33f43  ldloc.s  7
0x33f45  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33f4a  ldstr    aWorkflow_1// "workflow"
0x33f4f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33f54  brfalse  loc_33FF0
0x33f59  ldloc.0
0x33f5a  ldstr    aName// "name"
0x33f5f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x33f64  stloc.s  0xB
0x33f66  ldloc.s  0xB
0x33f68  ldloc.s  8
0x33f6a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x33f6f  ldloc.s  7
0x33f71  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33f76  ldloc.s  0xB
0x33f78  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x33f7d  pop
0x33f7e  ldloc.s  7
0x33f80  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33f85  ldstr    aWorkflow_1// "workflow"
0x33f8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33f8f  brfalse.s loc_33FB8
0x33f91  ldloc.0
0x33f92  ldstr    aWorkflowid_0// "workflowid"
0x33f97  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x33f9c  stloc.s  0xC
0x33f9e  ldloc.s  0xC
0x33fa0  ldloc.s  8
0x33fa2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x33fa7  ldloc.s  7
0x33fa9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33fae  ldloc.s  0xC
0x33fb0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x33fb5  pop
0x33fb6  br.s     loc_33FF0
0x33fb8  ldloc.s  7
0x33fba  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33fbf  ldstr    aSecurityrole_0// "securityrole"
0x33fc4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33fc9  brfalse.s loc_33FF0
0x33fcb  ldloc.0
0x33fcc  ldstr    aRoleid// "roleid"
0x33fd1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x33fd6  stloc.s  0xD
0x33fd8  ldloc.s  0xD
0x33fda  ldloc.s  8
0x33fdc  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x33fe1  ldloc.s  7
0x33fe3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33fe8  ldloc.s  0xD
0x33fea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x33fef  pop
0x33ff0  ldloc.s  6
0x33ff2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33ff7  brtrue   loc_33E8E
0x33ffc  leave.s  loc_34013
0x33ffe  ldloc.s  6
0x34000  isinst   [mscorlib]System.IDisposable
0x34005  stloc.s  0xE
0x34007  ldloc.s  0xE
0x34009  brfalse.s loc_34012
0x3400b  ldloc.s  0xE
0x3400d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34012  endfinally
0x34013  ldloc.0
0x34014  ldstr    aSolutionmanife_0// "solutionManifests"
0x34019  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3401e  stloc.2
0x3401f  ldloc.1
0x34020  ldloc.2
0x34021  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x34026  pop
0x34027  ldloc.0
0x34028  ldstr    aSolutionmanife_1// "solutionManifest"
0x3402d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x34032  stloc.s  4
0x34034  ldloc.2
0x34035  ldloc.s  4
0x34037  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3403c  pop
0x3403d  ldloc.0
0x3403e  ldstr    aUniquename_0// "UniqueName"
0x34043  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x34048  stloc.s  5
0x3404a  ldloc.s  4
0x3404c  ldloc.s  5
0x3404e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x34053  pop
0x34054  ldloc.s  5
0x34056  ldstr    aDefault// "Default"
0x3405b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x34060  leave.s  loc_3406C
0x34062  ldloc.3
0x34063  brfalse.s loc_3406B
0x34065  ldloc.3
0x34066  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3406b  endfinally
0x3406c  leave.s  loc_34093
0x3406e  stloc.s  0xF
0x34070  ldstr    aImportjobDataC// "ImportJob.data could not be loaded. Dat"...
0x34075  ldc.i4.2
0x34076  newarr   [mscorlib]System.Object
0x3407b  dup
0x3407c  ldc.i4.0
0x3407d  ldloc.s  0xF
0x3407f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x34084  stelem.ref
0x34085  dup
0x34086  ldc.i4.1
0x34087  ldarg.1
0x34088  stelem.ref
0x34089  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x3408e  ldarg.1
0x3408f  stloc.s  0x10
0x34091  leave.s  loc_3409A
0x34093  ldloc.0
0x34094  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x34099  ret
0x3409a  ldloc.s  0x10
0x3409c  ret
```
