# Microsoft.Crm.XmlUpgrade.VisualizationXmlProcessor::ProcessVisualizationXml

- ea: `0x49eb0`
- end: `0x49f49`
- name: `Microsoft.Crm.XmlUpgrade.VisualizationXmlProcessor::ProcessVisualizationXml`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x50a00`

## callees

- `0x49eb0`
- `0x4a0d0`
- `0x4a1b0`

## string_xrefs

- `0x49efb`: `Cannot replace the visualization webresource by more than 1 resource for the {0}`

## pseudocode

```c

```

## disassembly

```asm
0x49eb0  ldarg.2
0x49eb1  brtrue.s loc_49EBE
0x49eb3  ldstr    aVisualizationw// "visualizationWebResourceNodes cannot be"...
0x49eb8  newobj   instance void [mscorlib]System.NullReferenceException::.ctor(string)
0x49ebd  throw
0x49ebe  ldarg.2
0x49ebf  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x49ec4  stloc.0
0x49ec5  br.s     loc_49F2A
0x49ec7  ldloc.0
0x49ec8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x49ecd  castclass [System.Xml]System.Xml.XmlNode
0x49ed2  stloc.1
0x49ed3  ldloc.1
0x49ed4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x49ed9  stloc.2
0x49eda  call     class Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::get_Instance()
0x49edf  ldloc.2
0x49ee0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition> Microsoft.Crm.XmlUpgrade.FormXmlUpgradeInformation::GetUpgradedResources(string oldResourceName)
0x49ee5  stloc.3
0x49ee6  ldloc.3
0x49ee7  brfalse.s loc_49F2A
0x49ee9  ldloc.3
0x49eea  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::get_Count()
0x49eef  ldc.i4.0
0x49ef0  ble.s    loc_49F2A
0x49ef2  ldloc.3
0x49ef3  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::get_Count()
0x49ef8  ldc.i4.1
0x49ef9  beq.s    loc_49F0C
0x49efb  ldstr    aCannotReplaceT// "Cannot replace the visualization webres"...
0x49f00  ldloc.2
0x49f01  call     string [mscorlib]System.String::Format(string, object)
0x49f06  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x49f0b  throw
0x49f0c  ldloc.3
0x49f0d  call     T0x2B000044
0x49f12  stloc.s  5
0x49f14  ldloca.s 5
0x49f16  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.XmlUpgrade.ResourceDefinition>::get_Value()
0x49f1b  stloc.s  4
0x49f1d  ldloc.1
0x49f1e  ldloc.s  4
0x49f20  ldfld    string Microsoft.Crm.XmlUpgrade.ResourceDefinition::Name
0x49f25  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x49f2a  ldloc.0
0x49f2b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x49f30  brtrue.s loc_49EC7
0x49f32  leave.s  loc_49F48
0x49f34  ldloc.0
0x49f35  isinst   [mscorlib]System.IDisposable
0x49f3a  stloc.s  6
0x49f3c  ldloc.s  6
0x49f3e  brfalse.s loc_49F47
0x49f40  ldloc.s  6
0x49f42  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49f47  endfinally
0x49f48  ret
```
