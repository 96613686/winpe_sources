# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::GoalManagementUpgradeHandler

- ea: `0x24bc0`
- end: `0x24da9`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::GoalManagementUpgradeHandler`
- size: `489`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x24bc0`
- `0x63db0`

## string_xrefs

- `0x24bc1`: `ImportExportXml/Entities/Entity/EntityInfo/entity[@Name='Goal']`
- `0x24bea`: `attributes/attribute[@PhysicalName='ConsiderOnlyGoalOwnersRecords']/RequiredLevel`
- `0x24c44`: `ImportExportXml/Entities/Entity/EntityInfo/entity[@Name='GoalRollupQuery']`
- `0x24c53`: `attributes/attribute[@PhysicalName='FetchXml']/Length`
- `0x24c70`: `attributes/attribute[@PhysicalName='FetchXml']/MaxLength`
- `0x24c8d`: `ImportExportXml/Entities/Entity/EntityInfo/entity[@Name='Organization']`

## pseudocode

```c

```

## disassembly

```asm
0x24bc0  ldarg.1
0x24bc1  ldstr    aImportexportxm_68// "ImportExportXml/Entities/Entity/EntityI"...
0x24bc6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24bcb  stloc.0
0x24bcc  ldloc.0
0x24bcd  brfalse.s loc_24C43
0x24bcf  ldloc.0
0x24bd0  ldstr    aIsmailmergeena// "IsMailMergeEnabled"
0x24bd5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24bda  stloc.3
0x24bdb  ldloc.3
0x24bdc  brfalse.s loc_24BE9
0x24bde  ldloc.3
0x24bdf  ldstr    a0_1// "0"
0x24be4  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24be9  ldloc.0
0x24bea  ldstr    aAttributesAttr_3// "attributes/attribute[@PhysicalName='Con"...
0x24bef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24bf4  stloc.s  4
0x24bf6  ldloc.s  4
0x24bf8  brfalse.s loc_24C06
0x24bfa  ldloc.s  4
0x24bfc  ldstr    aSystemrequired// "systemrequired"
0x24c01  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24c06  ldloc.0
0x24c07  ldstr    aAttributesAttr_4// "attributes/attribute[@PhysicalName='Rol"...
0x24c0c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c11  stloc.s  5
0x24c13  ldloc.s  4
0x24c15  brfalse.s loc_24C23
0x24c17  ldloc.s  5
0x24c19  ldstr    aSystemrequired// "systemrequired"
0x24c1e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24c23  ldloc.0
0x24c24  ldstr    aAttributesAttr_5// "attributes/attribute[@PhysicalName='Own"...
0x24c29  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c2e  stloc.s  6
0x24c30  ldloc.s  6
0x24c32  brfalse.s loc_24C43
0x24c34  ldloc.s  6
0x24c36  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x24c3b  ldloc.s  6
0x24c3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x24c42  pop
0x24c43  ldarg.1
0x24c44  ldstr    aImportexportxm_69// "ImportExportXml/Entities/Entity/EntityI"...
0x24c49  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c4e  stloc.1
0x24c4f  ldloc.1
0x24c50  brfalse.s loc_24C8C
0x24c52  ldloc.1
0x24c53  ldstr    aAttributesAttr_6// "attributes/attribute[@PhysicalName='Fet"...
0x24c58  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c5d  stloc.s  7
0x24c5f  ldloc.s  7
0x24c61  brfalse.s loc_24C6F
0x24c63  ldloc.s  7
0x24c65  ldstr    aMax// "max"
0x24c6a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24c6f  ldloc.1
0x24c70  ldstr    aAttributesAttr_7// "attributes/attribute[@PhysicalName='Fet"...
0x24c75  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c7a  stloc.s  8
0x24c7c  ldloc.s  8
0x24c7e  brfalse.s loc_24C8C
0x24c80  ldloc.s  8
0x24c82  ldstr    a1073741823// "1073741823"
0x24c87  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24c8c  ldarg.1
0x24c8d  ldstr    aImportexportxm_70// "ImportExportXml/Entities/Entity/EntityI"...
0x24c92  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24c97  stloc.2
0x24c98  ldloc.2
0x24c99  brfalse  loc_24D86
0x24c9e  ldloc.2
0x24c9f  ldstr    aAttributesAttr_8// "attributes/attribute[@PhysicalName='Fis"...
0x24ca4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24ca9  stloc.s  9
0x24cab  ldloc.s  9
0x24cad  brfalse.s loc_24CBB
0x24caf  ldloc.s  9
0x24cb1  ldstr    aNone// "none"
0x24cb6  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24cbb  ldloc.2
0x24cbc  ldstr    aAttributesAttr_9// "attributes/attribute[@PhysicalName='Fis"...
0x24cc1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24cc6  stloc.s  0xA
0x24cc8  ldloc.s  0xA
0x24cca  brfalse.s loc_24CD8
0x24ccc  ldloc.s  0xA
0x24cce  ldstr    aSystemrequired// "systemrequired"
0x24cd3  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24cd8  ldloc.2
0x24cd9  ldstr    aAttributesAttr_10// "attributes/attribute[@PhysicalName='Fis"...
0x24cde  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24ce3  stloc.s  0xB
0x24ce5  ldloc.s  0xB
0x24ce7  brfalse.s loc_24CF5
0x24ce9  ldloc.s  0xB
0x24ceb  ldstr    aSystemrequired// "systemrequired"
0x24cf0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24cf5  ldloc.2
0x24cf6  ldstr    aAttributesAttr_11// "attributes/attribute[@PhysicalName='Fis"...
0x24cfb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24d00  stloc.s  0xC
0x24d02  ldloc.s  0xC
0x24d04  brfalse.s loc_24D12
0x24d06  ldloc.s  0xC
0x24d08  ldstr    aNone// "none"
0x24d0d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24d12  ldloc.2
0x24d13  ldstr    aAttributesAttr_12// "attributes/attribute[@PhysicalName='Fis"...
0x24d18  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24d1d  stloc.s  0xD
0x24d1f  ldloc.s  0xD
0x24d21  brfalse.s loc_24D2F
0x24d23  ldloc.s  0xD
0x24d25  ldstr    aNone// "none"
0x24d2a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24d2f  ldloc.2
0x24d30  ldstr    aAttributesAttr_13// "attributes/attribute[@PhysicalName='Fis"...
0x24d35  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24d3a  stloc.s  0xE
0x24d3c  ldloc.s  0xE
0x24d3e  brfalse.s loc_24D4C
0x24d40  ldloc.s  0xE
0x24d42  ldstr    aNone// "none"
0x24d47  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24d4c  ldloc.2
0x24d4d  ldstr    aAttributesAttr_14// "attributes/attribute[@PhysicalName='Fis"...
0x24d52  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24d57  stloc.s  0xF
0x24d59  ldloc.s  0xF
0x24d5b  brfalse.s loc_24D69
0x24d5d  ldloc.s  0xF
0x24d5f  ldstr    aSystemrequired// "systemrequired"
0x24d64  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24d69  ldloc.2
0x24d6a  ldstr    aAttributesAttr_15// "attributes/attribute[@PhysicalName='IsF"...
0x24d6f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x24d74  stloc.s  0x10
0x24d76  ldloc.s  0x10
0x24d78  brfalse.s loc_24D86
0x24d7a  ldloc.s  0x10
0x24d7c  ldstr    aSystemrequired// "systemrequired"
0x24d81  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x24d86  ldarg.s  6
0x24d88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24d8d  ldstr    aExecutingSolut// "Executing solution package Upgrade hand"...
0x24d92  ldc.i4.1
0x24d93  newarr   [mscorlib]System.Object
0x24d98  dup
0x24d99  ldc.i4.0
0x24d9a  ldarg.s  4
0x24d9c  stelem.ref
0x24d9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24da2  ldc.i4.1
0x24da3  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x24da8  ret
```
