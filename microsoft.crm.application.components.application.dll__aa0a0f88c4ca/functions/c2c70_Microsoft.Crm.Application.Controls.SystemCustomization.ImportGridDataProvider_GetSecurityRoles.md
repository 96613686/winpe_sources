# Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetSecurityRoles

- ea: `0xc2c70`
- end: `0xc2da4`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetSecurityRoles`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc0af0`

## callees

- `0xc2c70`
- `0xc3eb0`
- `0xf4210`

## string_xrefs

- `0xc2c71`: `importexportxml/securityroles/securityrole`
- `0xc2cd6`: `securityrole:`
- `0xc2d17`: `EntityGridDataProvider_Types_SecurityRole`
- `0xc2d25`: `EntityGridDataProvider_Types_SecurityRole_Description`

## pseudocode

```c

```

## disassembly

```asm
0xc2c70  ldarg.2
0xc2c71  ldstr    aImportexportxm_16// "importexportxml/securityroles/securityr"...
0xc2c76  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc2c7b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xc2c80  stloc.1
0xc2c81  br       loc_C2D82
0xc2c86  ldloc.1
0xc2c87  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc2c8c  castclass [System.Xml]System.Xml.XmlNode
0xc2c91  stloc.2
0xc2c92  ldloc.2
0xc2c93  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc2c98  ldstr    aName// "name"
0xc2c9d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc2ca2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc2ca7  stloc.3
0xc2ca8  ldloc.2
0xc2ca9  ldstr    aResult// "result"
0xc2cae  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc2cb3  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xc2cb8  stloc.s  4
0xc2cba  ldloc.s  4
0xc2cbc  brfalse.s loc_C2CC2
0xc2cbe  ldloc.s  4
0xc2cc0  br.s     loc_C2CC3
0xc2cc2  ldc.i4.1
0xc2cc3  stloc.s  4
0xc2cc5  ldc.i4.0
0xc2cc6  stloc.s  5
0xc2cc8  br       loc_C2D79
0xc2ccd  ldc.i4.s 0xA
0xc2ccf  newarr   [mscorlib]System.String
0xc2cd4  dup
0xc2cd5  ldc.i4.0
0xc2cd6  ldstr    aSecurityrole// "securityrole:"
0xc2cdb  ldloc.2
0xc2cdc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc2ce1  ldstr    aRoleid// "roleid"
0xc2ce6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc2ceb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc2cf0  call     string [mscorlib]System.String::Concat(string, string)
0xc2cf5  stelem.ref
0xc2cf6  dup
0xc2cf7  ldc.i4.1
0xc2cf8  ldc.i4   0x40C
0xc2cfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc2d02  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc2d07  stelem.ref
0xc2d08  dup
0xc2d09  ldc.i4.2
0xc2d0a  ldloc.3
0xc2d0b  stelem.ref
0xc2d0c  dup
0xc2d0d  ldc.i4.3
0xc2d0e  ldsfld   string [mscorlib]System.String::Empty
0xc2d13  stelem.ref
0xc2d14  dup
0xc2d15  ldc.i4.4
0xc2d16  ldarg.1
0xc2d17  ldstr    aEntitygriddata_53// "EntityGridDataProvider_Types_SecurityRo"...
0xc2d1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc2d21  stelem.ref
0xc2d22  dup
0xc2d23  ldc.i4.5
0xc2d24  ldarg.1
0xc2d25  ldstr    aEntitygriddata_54// "EntityGridDataProvider_Types_SecurityRo"...
0xc2d2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc2d2f  stelem.ref
0xc2d30  dup
0xc2d31  ldc.i4.6
0xc2d32  ldloc.2
0xc2d33  ldstr    aResult// "result"
0xc2d38  ldloc.s  5
0xc2d3a  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc2d3f  stelem.ref
0xc2d40  dup
0xc2d41  ldc.i4.7
0xc2d42  ldloc.2
0xc2d43  ldstr    aDatetimeticks// "datetimeticks"
0xc2d48  ldloc.s  5
0xc2d4a  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc2d4f  stelem.ref
0xc2d50  dup
0xc2d51  ldc.i4.8
0xc2d52  ldloc.2
0xc2d53  ldstr    aErrorcode_0// "errorcode"
0xc2d58  ldloc.s  5
0xc2d5a  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc2d5f  stelem.ref
0xc2d60  dup
0xc2d61  ldc.i4.s 9
0xc2d63  ldloc.3
0xc2d64  stelem.ref
0xc2d65  stloc.0
0xc2d66  ldarg.3
0xc2d67  ldloc.0
0xc2d68  newobj   instance void Row::.ctor(string[] columns)
0xc2d6d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc2d72  pop
0xc2d73  ldloc.s  5
0xc2d75  ldc.i4.1
0xc2d76  add
0xc2d77  stloc.s  5
0xc2d79  ldloc.s  5
0xc2d7b  ldloc.s  4
0xc2d7d  blt      loc_C2CCD
0xc2d82  ldloc.1
0xc2d83  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc2d88  brtrue   loc_C2C86
0xc2d8d  leave.s  loc_C2DA3
0xc2d8f  ldloc.1
0xc2d90  isinst   [mscorlib]System.IDisposable
0xc2d95  stloc.s  6
0xc2d97  ldloc.s  6
0xc2d99  brfalse.s loc_C2DA2
0xc2d9b  ldloc.s  6
0xc2d9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc2da2  endfinally
0xc2da3  ret
```
