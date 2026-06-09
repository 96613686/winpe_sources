# Microsoft.Crm.SharedDatabase.Table::.ctor

- ea: `0x60650`
- end: `0x607ca`
- name: `Microsoft.Crm.SharedDatabase.Table::.ctor`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60f70`
- `0x65070`

## callees

- `0x1a880`
- `0x60650`
- `0x60920`
- `0x609c0`
- `0x60a10`
- `0x60aa0`

## string_xrefs

- `0x6070b`: `ConfigScope`
- `0x60718`: `ConfigScope`
- `0x606ea`: `Security`
- `0x60746`: `Cached`
- `0x60753`: `Cached`

## pseudocode

```c

```

## disassembly

```asm
0x60650  ldarg.0
0x60651  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.SharedDatabase.Index>::.ctor()
0x60656  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.SharedDatabase.Index> Microsoft.Crm.SharedDatabase.Table::_indexes
0x6065b  ldarg.0
0x6065c  ldc.i4.1
0x6065d  stfld    bool Microsoft.Crm.SharedDatabase.Table::_cached
0x60662  ldarg.0
0x60663  call     instance void [mscorlib]System.Object::.ctor()
0x60668  ldarg.1
0x60669  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6066e  stloc.0
0x6066f  ldarg.0
0x60670  ldloc.0
0x60671  ldstr    aName// "Name"
0x60676  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6067b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x60680  stfld    string Microsoft.Crm.SharedDatabase.Table::_name
0x60685  ldarg.1
0x60686  ldstr    aDescription_0// "Description"
0x6068b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60690  brfalse.s loc_606A4
0x60692  ldarg.1
0x60693  ldstr    aDescription_0// "Description"
0x60698  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6069d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x606a2  br.s     loc_606A5
0x606a4  ldnull
0x606a5  stloc.1
0x606a6  ldloc.1
0x606a7  brtrue.s loc_606B9
0x606a9  ldstr    aDescriptionMus// "Description must be specified"
0x606ae  ldc.i4   0x80044197
0x606b3  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x606b8  throw
0x606b9  ldarg.0
0x606ba  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSku
0x606bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x606c4  ldarg.1
0x606c5  ldstr    aSku// "SKU"
0x606ca  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x606cf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x606d4  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x606d9  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.SharedDatabase.Table::_sku
0x606de  ldarg.0
0x606df  ldtoken  Microsoft.Crm.SharedDatabase.SecurityLevel
0x606e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x606e9  ldarg.1
0x606ea  ldstr    aSecurity// "Security"
0x606ef  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x606f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x606f9  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x606fe  stfld    valuetype Microsoft.Crm.SharedDatabase.SecurityLevel Microsoft.Crm.SharedDatabase.Table::_security
0x60703  ldarg.0
0x60704  ldc.i4.0
0x60705  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::_scope
0x6070a  ldarg.1
0x6070b  ldstr    aConfigscope// "ConfigScope"
0x60710  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60715  brfalse.s loc_60729
0x60717  ldarg.1
0x60718  ldstr    aConfigscope// "ConfigScope"
0x6071d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60722  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x60727  br.s     loc_6072A
0x60729  ldnull
0x6072a  stloc.2
0x6072b  ldloc.2
0x6072c  brfalse.s loc_60744
0x6072e  ldarg.0
0x6072f  ldtoken  Microsoft.Crm.SharedDatabase.ConfigScope
0x60734  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60739  ldloc.2
0x6073a  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x6073f  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::_scope
0x60744  ldarg.0
0x60745  ldarg.1
0x60746  ldstr    aCached// "Cached"
0x6074b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60750  brfalse.s loc_60769
0x60752  ldarg.1
0x60753  ldstr    aCached// "Cached"
0x60758  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6075d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x60762  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x60767  br.s     loc_6076A
0x60769  ldc.i4.1
0x6076a  stfld    bool Microsoft.Crm.SharedDatabase.Table::_cached
0x6076f  ldarg.1
0x60770  ldstr    aFailovermode// "FailoverMode"
0x60775  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6077a  brfalse.s loc_6078E
0x6077c  ldarg.1
0x6077d  ldstr    aFailovermode// "FailoverMode"
0x60782  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60787  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6078c  br.s     loc_6078F
0x6078e  ldnull
0x6078f  stloc.3
0x60790  ldloc.3
0x60791  brfalse.s loc_607A9
0x60793  ldarg.0
0x60794  ldtoken  Microsoft.Crm.CrmFailoverMode
0x60799  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6079e  ldloc.3
0x6079f  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x607a4  stfld    valuetype Microsoft.Crm.CrmFailoverMode Microsoft.Crm.SharedDatabase.Table::_failoverMode
0x607a9  ldarg.1
0x607aa  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x607af  stloc.s  4
0x607b1  ldarg.0
0x607b2  ldloc.s  4
0x607b4  call     instance void Microsoft.Crm.SharedDatabase.Table::LoadColumns(class [System.Xml]System.Xml.XPath.XPathNavigator nav)
0x607b9  ldarg.0
0x607ba  ldloc.s  4
0x607bc  call     instance void Microsoft.Crm.SharedDatabase.Table::LoadRelationships(class [System.Xml]System.Xml.XPath.XPathNavigator nav)
0x607c1  ldarg.0
0x607c2  ldloc.s  4
0x607c4  call     instance void Microsoft.Crm.SharedDatabase.Table::LoadIndexes(class [System.Xml]System.Xml.XPath.XPathNavigator nav)
0x607c9  ret
```
