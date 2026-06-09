# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddCustomAttributeTypeDefaults

- ea: `0x7780`
- end: `0x7a3d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddCustomAttributeTypeDefaults`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x76e0`

## callees

- `0x7780`
- `0x7a40`
- `0x7a50`
- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0x7780  ldarg.0
0x7781  ldstr    aName// "name"
0x7786  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x778b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7790  stloc.0
0x7791  ldloc.0
0x7792  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x7797  stloc.1
0x7798  ldloc.1
0x7799  ldc.i4   0x60CAE230
0x779e  bgt.un.s loc_77BC
0x77a0  ldloc.1
0x77a1  ldc.i4   0x1F088D4C
0x77a6  beq      loc_7832
0x77ab  ldloc.1
0x77ac  ldc.i4   0x5BC874BE
0x77b1  beq.s    loc_77E6
0x77b3  ldloc.1
0x77b4  ldc.i4   0x60CAE230
0x77b9  beq.s    loc_7810
0x77bb  ret
0x77bc  ldloc.1
0x77bd  ldc.i4   0xBAC37203
0x77c2  bgt.un.s loc_77D5
0x77c4  ldloc.1
0x77c5  ldc.i4   0x95E97E5E
0x77ca  beq.s    loc_7821
0x77cc  ldloc.1
0x77cd  ldc.i4   0xBAC37203
0x77d2  beq.s    loc_7802
0x77d4  ret
0x77d5  ldloc.1
0x77d6  ldc.i4   0xCCEA6D90
0x77db  beq.s    loc_7843
0x77dd  ldloc.1
0x77de  ldc.i4   0xD9844140
0x77e3  beq.s    loc_77F4
0x77e5  ret
0x77e6  ldloc.0
0x77e7  ldstr    aNvarchar// "nvarchar"
0x77ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x77f1  brtrue.s loc_7854
0x77f3  ret
0x77f4  ldloc.0
0x77f5  ldstr    aPicklist// "picklist"
0x77fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x77ff  brtrue.s loc_7879
0x7801  ret
0x7802  ldloc.0
0x7803  ldstr    aMultiselectpic// "multiselectpicklist"
0x7808  call     bool [mscorlib]System.String::op_Equality(string, string)
0x780d  brtrue.s loc_7879
0x780f  ret
0x7810  ldloc.0
0x7811  ldstr    aBit// "bit"
0x7816  call     bool [mscorlib]System.String::op_Equality(string, string)
0x781b  brtrue   loc_78F3
0x7820  ret
0x7821  ldloc.0
0x7822  ldstr    aInt// "int"
0x7827  call     bool [mscorlib]System.String::op_Equality(string, string)
0x782c  brtrue   loc_79B6
0x7831  ret
0x7832  ldloc.0
0x7833  ldstr    aDecimal// "decimal"
0x7838  call     bool [mscorlib]System.String::op_Equality(string, string)
0x783d  brtrue   loc_79E3
0x7842  ret
0x7843  ldloc.0
0x7844  ldstr    aDatetime// "datetime"
0x7849  call     bool [mscorlib]System.String::op_Equality(string, string)
0x784e  brtrue   loc_7A2B
0x7853  ret
0x7854  ldarg.0
0x7855  ldstr    aFormat// "format"
0x785a  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_DefaultFormat()
0x785f  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7864  pop
0x7865  ldarg.0
0x7866  ldstr    aLength// "length"
0x786b  ldc.i4.s 0x64
0x786d  box      [mscorlib]System.Int32
0x7872  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7877  pop
0x7878  ret
0x7879  ldarg.0
0x787a  ldstr    aValues// "values"
0x787f  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName)
0x7884  dup
0x7885  ldstr    aDefault// "default"
0x788a  ldc.i4   0x80000000
0x788f  stloc.s  5
0x7891  ldloca.s 5
0x7893  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7898  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x789d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x78a2  dup
0x78a3  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x78a8  ldstr    aValue// "value"
0x78ad  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x78b2  stloc.2
0x78b3  ldloc.2
0x78b4  ldstr    aValue// "value"
0x78b9  ldc.i4   0x80000000
0x78be  stloc.s  5
0x78c0  ldloca.s 5
0x78c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78c7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x78cc  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x78d1  ldloc.2
0x78d2  ldstr    aLabel// "label"
0x78d7  ldc.i4.m1
0x78d8  stloc.s  5
0x78da  ldloca.s 5
0x78dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78e1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x78e6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x78eb  ldloc.2
0x78ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x78f1  pop
0x78f2  ret
0x78f3  ldarg.0
0x78f4  ldstr    aValues// "values"
0x78f9  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName)
0x78fe  dup
0x78ff  ldstr    aDefault// "default"
0x7904  ldc.i4.0
0x7905  stloc.s  5
0x7907  ldloca.s 5
0x7909  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x790e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7913  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x7918  dup
0x7919  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x791e  ldstr    aValue// "value"
0x7923  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x7928  stloc.3
0x7929  ldloc.3
0x792a  ldstr    aValue// "value"
0x792f  ldc.i4.0
0x7930  stloc.s  5
0x7932  ldloca.s 5
0x7934  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7939  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x793e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x7943  ldloc.3
0x7944  ldstr    aLabel// "label"
0x7949  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x794e  ldstr    aSystemcustomiz_1// "SystemCustomization.Boolean.Values.Fals"...
0x7953  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7958  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x795d  dup
0x795e  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x7963  ldstr    aValue// "value"
0x7968  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x796d  stloc.s  4
0x796f  ldloc.s  4
0x7971  ldstr    aValue// "value"
0x7976  ldc.i4.1
0x7977  stloc.s  5
0x7979  ldloca.s 5
0x797b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7980  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7985  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x798a  ldloc.s  4
0x798c  ldstr    aLabel// "label"
0x7991  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7996  ldstr    aSystemcustomiz_2// "SystemCustomization.Boolean.Values.True"
0x799b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x79a0  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x79a5  dup
0x79a6  ldloc.3
0x79a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x79ac  pop
0x79ad  ldloc.s  4
0x79af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x79b4  pop
0x79b5  ret
0x79b6  ldarg.0
0x79b7  ldstr    aMinvalue// "minvalue"
0x79bc  ldc.i4   0x80000000
0x79c1  box      [mscorlib]System.Int32
0x79c6  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x79cb  pop
0x79cc  ldarg.0
0x79cd  ldstr    aMaxvalue// "maxvalue"
0x79d2  ldc.i4   0x7FFFFFFF
0x79d7  box      [mscorlib]System.Int32
0x79dc  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x79e1  pop
0x79e2  ret
0x79e3  ldarg.0
0x79e4  ldstr    aPrecision// "precision"
0x79e9  ldc.i4.s 0xA
0x79eb  box      [mscorlib]System.Int32
0x79f0  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x79f5  pop
0x79f6  ldarg.0
0x79f7  ldstr    aMinvalue// "minvalue"
0x79fc  ldc.r8   -1.0e9
0x7a05  box      [mscorlib]System.Double
0x7a0a  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7a0f  pop
0x7a10  ldarg.0
0x7a11  ldstr    aMaxvalue// "maxvalue"
0x7a16  ldc.r8   1.0e9
0x7a1f  box      [mscorlib]System.Double
0x7a24  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7a29  pop
0x7a2a  ret
0x7a2b  ldarg.0
0x7a2c  ldstr    aFormat// "format"
0x7a31  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x7a36  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7a3b  pop
0x7a3c  ret
```
