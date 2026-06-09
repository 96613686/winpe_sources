# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::RemoveInvalidInjections

- ea: `0x612b0`
- end: `0x613a5`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::RemoveInvalidInjections`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60e70`

## callees

- `0xe910`
- `0x5fc90`
- `0x612b0`
- `0x64990`
- `0x64ec0`

## string_xrefs

- `0x612dd`: `Map/EntityMaps/EntityMap/AttributeMaps/AttributeMap[TargetAttributeName='createdon' or TargetAttributeName='overriddencreatedon']`
- `0x61360`: `Map/EntityMaps/EntityMap[@TargetEntityName = 'incident']/AttributeMaps/AttributeMap[SourceAttributeName = 'AssetId' and ProcessCode = 'Create' and TargetAttributeRef = '_custAttribute_47_AssetId']`
- `0x61371`: `Map/EntityMaps/EntityMap[@TargetEntityName = 'incident']/AttributeMaps/AttributeMap[SourceAttributeName = 'Asset Name' and ProcessCode = 'Create' and TargetAttributeRef = '_custAttribute_47_AssetId']`

## pseudocode

```c

```

## disassembly

```asm
0x612b0  ldc.i4.2
0x612b1  ldc.i4.1
0x612b2  ldarg.2
0x612b3  call     bool Microsoft.Crm.Application.Platform.ImportHelper::IsMapOfType(int32 importMapType, int32 importMapSourceType, class Microsoft.Crm.Application.Platform.ImportWizardState wizardState)
0x612b8  stloc.0
0x612b9  ldc.i4.2
0x612ba  ldc.i4.2
0x612bb  ldarg.2
0x612bc  call     bool Microsoft.Crm.Application.Platform.ImportHelper::IsMapOfType(int32 importMapType, int32 importMapSourceType, class Microsoft.Crm.Application.Platform.ImportWizardState wizardState)
0x612c1  stloc.1
0x612c2  ldloc.0
0x612c3  brtrue.s loc_612CA
0x612c5  ldloc.1
0x612c6  brtrue.s loc_612CA
0x612c8  ldarg.1
0x612c9  ret
0x612ca  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_OverrideCreatedOnCreatedBy()
0x612cf  ldarg.2
0x612d0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x612d5  call     bool Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition pd, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x612da  brtrue.s loc_61331
0x612dc  ldarg.1
0x612dd  ldstr    aMapEntitymapsE_12// "Map/EntityMaps/EntityMap/AttributeMaps/"...
0x612e2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x612e7  stloc.s  4
0x612e9  ldloc.s  4
0x612eb  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x612f0  stloc.s  5
0x612f2  br.s     loc_61305
0x612f4  ldloc.s  5
0x612f6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x612fb  castclass [System.Xml]System.Xml.XmlNode
0x61300  call     void Microsoft.Crm.Application.Platform.ImportHelper::UnmapAttribute(class [System.Xml]System.Xml.XPath.IXPathNavigable attributeMap)
0x61305  ldloc.s  5
0x61307  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6130c  brtrue.s loc_612F4
0x6130e  leave.s  loc_61331
0x61310  ldloc.s  5
0x61312  isinst   [mscorlib]System.IDisposable
0x61317  stloc.s  6
0x61319  ldloc.s  6
0x6131b  brfalse.s loc_61324
0x6131d  ldloc.s  6
0x6131f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61324  endfinally
0x61325  ldloc.s  4
0x61327  brfalse.s loc_61330
0x61329  ldloc.s  4
0x6132b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61330  endfinally
0x61331  ldarg.1
0x61332  ldstr    aMapEntitymapsE_13// "Map/EntityMaps/EntityMap[@TargetEntityR"...
0x61337  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6133c  stloc.s  7
0x6133e  ldloc.s  7
0x61340  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x61345  brfalse.s loc_6134C
0x61347  ldarg.1
0x61348  stloc.s  8
0x6134a  leave.s  loc_613A2
0x6134c  leave.s  loc_6135A
0x6134e  ldloc.s  7
0x61350  brfalse.s loc_61359
0x61352  ldloc.s  7
0x61354  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61359  endfinally
0x6135a  ldnull
0x6135b  stloc.2
0x6135c  ldloc.0
0x6135d  brfalse.s loc_6136D
0x6135f  ldarg.1
0x61360  ldstr    aMapEntitymapsE_14// "Map/EntityMaps/EntityMap[@TargetEntityN"...
0x61365  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6136a  stloc.2
0x6136b  br.s     loc_6137C
0x6136d  ldloc.1
0x6136e  brfalse.s loc_6137C
0x61370  ldarg.1
0x61371  ldstr    aMapEntitymapsE_15// "Map/EntityMaps/EntityMap[@TargetEntityN"...
0x61376  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6137b  stloc.2
0x6137c  ldloc.2
0x6137d  brtrue.s loc_61381
0x6137f  ldarg.1
0x61380  ret
0x61381  ldloc.2
0x61382  call     void Microsoft.Crm.Application.Platform.ImportHelper::UnmapAttribute(class [System.Xml]System.Xml.XPath.IXPathNavigable attributeMap)
0x61387  ldarg.1
0x61388  ldstr    aMapCustomizati// "Map/Customizations/Entities/Entity[Logi"...
0x6138d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x61392  stloc.3
0x61393  ldloc.3
0x61394  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x61399  ldloc.3
0x6139a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x6139f  pop
0x613a0  ldarg.1
0x613a1  ret
0x613a2  ldloc.s  8
0x613a4  ret
```
