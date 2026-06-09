# Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::PopulateControlDefaultConfigFromNode

- ea: `0x31f90`
- end: `0x320a2`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::PopulateControlDefaultConfigFromNode`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x31f50`
- `0x320b0`

## callees

- `0x31f90`

## string_xrefs

- `0x31f97`: `CustomControlDefaultConfigId`
- `0x31f91`: `customcontroldefaultconfigid`
- `0x31fb6`: `ControlDescriptionXML`
- `0x31fc9`: `ControlDescriptionXML`
- `0x31fc3`: `controldescriptionxml`
- `0x3205c`: `eventsxml`
- `0x32066`: `<customControlDefaultConfig>{0}{1}</customControlDefaultConfig>`

## pseudocode

```c

```

## disassembly

```asm
0x31f90  ldarg.1
0x31f91  ldstr    aCustomcontrold_1// "customcontroldefaultconfigid"
0x31f96  ldarg.2
0x31f97  ldstr    aCustomcontrold_0// "CustomControlDefaultConfigId"
0x31f9c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31fa1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x31fa6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x31fab  box      [mscorlib]System.Guid
0x31fb0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x31fb5  ldarg.2
0x31fb6  ldstr    aControldescrip// "ControlDescriptionXML"
0x31fbb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31fc0  brfalse.s loc_31FDD
0x31fc2  ldarg.1
0x31fc3  ldstr    aControldescrip_0// "controldescriptionxml"
0x31fc8  ldarg.2
0x31fc9  ldstr    aControldescrip// "ControlDescriptionXML"
0x31fce  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31fd3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x31fd8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x31fdd  ldarg.1
0x31fde  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x31fe3  ldarg.0
0x31fe4  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31fe9  box      [mscorlib]System.Int32
0x31fee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x31ff3  ldarg.2
0x31ff4  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x31ff9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31ffe  brfalse.s loc_3201B
0x32000  ldarg.1
0x32001  ldstr    aIntroducedvers// "introducedversion"
0x32006  ldarg.2
0x32007  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x3200c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x32011  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x32016  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3201b  ldnull
0x3201c  stloc.0
0x3201d  ldnull
0x3201e  stloc.1
0x3201f  ldarg.2
0x32020  ldstr    aFormlibraries// "formLibraries"
0x32025  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3202a  brfalse.s loc_3203D
0x3202c  ldarg.2
0x3202d  ldstr    aFormlibraries// "formLibraries"
0x32032  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x32037  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3203c  stloc.0
0x3203d  ldarg.2
0x3203e  ldstr    aEvents// "events"
0x32043  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x32048  brfalse.s loc_3205B
0x3204a  ldarg.2
0x3204b  ldstr    aEvents// "events"
0x32050  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x32055  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3205a  stloc.1
0x3205b  ldarg.1
0x3205c  ldstr    aEventsxml// "eventsxml"
0x32061  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32066  ldstr    aCustomcontrold_3// "<customControlDefaultConfig>{0}{1}</cus"...
0x3206b  ldc.i4.2
0x3206c  newarr   [mscorlib]System.Object
0x32071  dup
0x32072  ldc.i4.0
0x32073  ldloc.0
0x32074  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32079  brtrue.s loc_3207E
0x3207b  ldloc.0
0x3207c  br.s     loc_32083
0x3207e  ldsfld   string [mscorlib]System.String::Empty
0x32083  stelem.ref
0x32084  dup
0x32085  ldc.i4.1
0x32086  ldloc.1
0x32087  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3208c  brtrue.s loc_32091
0x3208e  ldloc.1
0x3208f  br.s     loc_32096
0x32091  ldsfld   string [mscorlib]System.String::Empty
0x32096  stelem.ref
0x32097  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3209c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x320a1  ret
```
