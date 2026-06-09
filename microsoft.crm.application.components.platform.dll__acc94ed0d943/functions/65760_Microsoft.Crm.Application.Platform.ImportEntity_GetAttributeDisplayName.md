# Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName

- ea: `0x65760`
- end: `0x657ef`
- name: `Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x66940`

## callees

- `0x11760`
- `0x30260`
- `0x65460`
- `0x65490`
- `0x65760`
- `0x66000`

## string_xrefs

- `0x6576d`: `createdon`
- `0x657c0`: `createdon`
- `0x65761`: `overriddencreatedon`
- `0x657d1`: `ImportWizard.AttributeMapPage.CreatedOnColumnForNewEntity`

## pseudocode

```c

```

## disassembly

```asm
0x65760  ldarg.1
0x65761  ldstr    aOverriddencrea// "overriddencreatedon"
0x65766  callvirt instance bool [mscorlib]System.String::Equals(string)
0x6576b  brfalse.s loc_65774
0x6576d  ldstr    aCreatedon// "createdon"
0x65772  starg.s  1
0x65774  ldarg.0
0x65775  ldfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode Microsoft.Crm.Application.Platform.ImportEntity::_processCode
0x6577a  ldc.i4.3
0x6577b  bne.un.s loc_657DC
0x6577d  ldarg.1
0x6577e  ldarg.0
0x6577f  call     instance string Microsoft.Crm.Application.Platform.ImportEntity::get_PrimaryKeyAttributeName()
0x65784  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65789  brfalse.s loc_657A1
0x6578b  ldarg.0
0x6578c  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.ImportEntity::_entityCustomizationNode
0x65791  ldstr    aPrimarykeydisp// "PrimaryKeyDisplayName"
0x65796  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6579b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x657a0  ret
0x657a1  ldarg.1
0x657a2  ldarg.0
0x657a3  call     instance string Microsoft.Crm.Application.Platform.ImportEntity::get_OwnerAttributeName()
0x657a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x657ad  brfalse.s loc_657BF
0x657af  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x657b4  ldstr    aImportwizardAt_1// "ImportWizard.AttributeMapPage.OwnerColu"...
0x657b9  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x657be  ret
0x657bf  ldarg.1
0x657c0  ldstr    aCreatedon// "createdon"
0x657c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x657ca  brfalse.s loc_657DC
0x657cc  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x657d1  ldstr    aImportwizardAt_2// "ImportWizard.AttributeMapPage.CreatedOn"...
0x657d6  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x657db  ret
0x657dc  ldarg.0
0x657dd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.ImportEntity::_targetEntityMetadata
0x657e2  ldarg.1
0x657e3  ldc.i4.1
0x657e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x657e9  call     string Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x657ee  ret
```
