# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateViewCustomControlDependencies

- ea: `0x642b0`
- end: `0x64391`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateViewCustomControlDependencies`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x63c60`

## callees

- `0x642b0`
- `0x643a0`
- `0x64670`

## string_xrefs

- `0x642d0`: `layoutxml`
- `0x642e0`: `layoutxml`
- `0x642f0`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x642b0  ldarg.0
0x642b1  ldarg.2
0x642b2  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x642b7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x642bc  ldarg.3
0x642bd  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Metadata.Dependency.DependencyProcessor::RetrieveViewData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity businessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x642c2  stloc.0
0x642c3  ldsfld   string [mscorlib]System.String::Empty
0x642c8  pop
0x642c9  ldloc.0
0x642ca  brfalse  loc_64390
0x642cf  ldloc.0
0x642d0  ldstr    aLayoutxml_0// "layoutxml"
0x642d5  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x642da  brfalse  loc_64390
0x642df  ldloc.0
0x642e0  ldstr    aLayoutxml_0// "layoutxml"
0x642e5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x642ea  brfalse  loc_64390
0x642ef  ldloc.0
0x642f0  ldstr    aLayoutxml_0// "layoutxml"
0x642f5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x642fa  callvirt instance string [mscorlib]System.Object::ToString()
0x642ff  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x64304  ldstr    aGrid// "grid"
0x64309  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x6430e  stloc.1
0x6430f  ldloc.1
0x64310  brfalse.s loc_64390
0x64312  ldloc.1
0x64313  ldc.i4.0
0x64314  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x64319  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x6431e  stloc.2
0x6431f  ldloc.2
0x64320  brfalse.s loc_64390
0x64322  ldloc.2
0x64323  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x64328  ldc.i4.0
0x64329  ble.s    loc_64390
0x6432b  ldloc.2
0x6432c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x64331  stloc.3
0x64332  br.s     loc_64372
0x64334  ldloc.3
0x64335  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6433a  castclass [System.Xml]System.Xml.XmlNode
0x6433f  stloc.s  4
0x64341  ldloc.s  4
0x64343  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x64348  ldstr    aControldescrip_1// "controlDescriptions"
0x6434d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x64352  brfalse.s loc_64372
0x64354  ldloc.s  4
0x64356  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x6435b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x64360  stloc.s  5
0x64362  ldarg.0
0x64363  ldloc.s  5
0x64365  ldarg.1
0x64366  ldarg.2
0x64367  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x6436c  ldarg.3
0x6436d  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddCustomControlCandidateItem(class [System.Xml]System.Xml.XmlDocument controlDescriptionXml, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x64372  ldloc.3
0x64373  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64378  brtrue.s loc_64334
0x6437a  leave.s  loc_64390
0x6437c  ldloc.3
0x6437d  isinst   [mscorlib]System.IDisposable
0x64382  stloc.s  6
0x64384  ldloc.s  6
0x64386  brfalse.s loc_6438F
0x64388  ldloc.s  6
0x6438a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6438f  endfinally
0x64390  ret
```
