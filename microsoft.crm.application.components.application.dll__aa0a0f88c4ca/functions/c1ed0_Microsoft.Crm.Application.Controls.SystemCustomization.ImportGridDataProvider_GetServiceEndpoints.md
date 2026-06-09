# Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetServiceEndpoints

- ea: `0xc1ed0`
- end: `0xc2010`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetServiceEndpoints`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc0af0`

## callees

- `0xc1ed0`
- `0xc3eb0`
- `0xf4210`

## string_xrefs

- `0xc1ed1`: `EntityGridDataProvider_Types_ServiceEndpoint`
- `0xc1edd`: `importexportxml/ServiceEndpoints/ServiceEndpoint`
- `0xc1f43`: `serviceendpoint:`

## pseudocode

```c

```

## disassembly

```asm
0xc1ed0  ldarg.1
0xc1ed1  ldstr    aEntitygriddata_34// "EntityGridDataProvider_Types_ServiceEnd"...
0xc1ed6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1edb  stloc.0
0xc1edc  ldarg.2
0xc1edd  ldstr    aImportexportxm_7// "importexportxml/ServiceEndpoints/Servic"...
0xc1ee2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc1ee7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xc1eec  stloc.2
0xc1eed  br       loc_C1FEE
0xc1ef2  ldloc.2
0xc1ef3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc1ef8  castclass [System.Xml]System.Xml.XmlNode
0xc1efd  stloc.3
0xc1efe  ldloc.3
0xc1eff  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1f04  ldstr    aName// "name"
0xc1f09  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1f0e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1f13  stloc.s  4
0xc1f15  ldloc.3
0xc1f16  ldstr    aResult// "result"
0xc1f1b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc1f20  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xc1f25  stloc.s  5
0xc1f27  ldloc.s  5
0xc1f29  brfalse.s loc_C1F2F
0xc1f2b  ldloc.s  5
0xc1f2d  br.s     loc_C1F30
0xc1f2f  ldc.i4.1
0xc1f30  stloc.s  5
0xc1f32  ldc.i4.0
0xc1f33  stloc.s  6
0xc1f35  br       loc_C1FE5
0xc1f3a  ldc.i4.s 0xA
0xc1f3c  newarr   [mscorlib]System.String
0xc1f41  dup
0xc1f42  ldc.i4.0
0xc1f43  ldstr    aServiceendpoin// "serviceendpoint:"
0xc1f48  ldloc.3
0xc1f49  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1f4e  ldstr    aId_1// "id"
0xc1f53  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1f58  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1f5d  call     string [mscorlib]System.String::Concat(string, string)
0xc1f62  stelem.ref
0xc1f63  dup
0xc1f64  ldc.i4.1
0xc1f65  ldc.i4   0x120A
0xc1f6a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc1f6f  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc1f74  stelem.ref
0xc1f75  dup
0xc1f76  ldc.i4.2
0xc1f77  ldloc.s  4
0xc1f79  stelem.ref
0xc1f7a  dup
0xc1f7b  ldc.i4.3
0xc1f7c  ldloc.s  4
0xc1f7e  stelem.ref
0xc1f7f  dup
0xc1f80  ldc.i4.4
0xc1f81  ldloc.0
0xc1f82  stelem.ref
0xc1f83  dup
0xc1f84  ldc.i4.5
0xc1f85  ldloc.3
0xc1f86  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1f8b  ldstr    aDescription_0// "Description"
0xc1f90  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1f95  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1f9a  stelem.ref
0xc1f9b  dup
0xc1f9c  ldc.i4.6
0xc1f9d  ldloc.3
0xc1f9e  ldstr    aResult// "result"
0xc1fa3  ldloc.s  6
0xc1fa5  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1faa  stelem.ref
0xc1fab  dup
0xc1fac  ldc.i4.7
0xc1fad  ldloc.3
0xc1fae  ldstr    aDatetimeticks// "datetimeticks"
0xc1fb3  ldloc.s  6
0xc1fb5  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1fba  stelem.ref
0xc1fbb  dup
0xc1fbc  ldc.i4.8
0xc1fbd  ldloc.3
0xc1fbe  ldstr    aErrorcode_0// "errorcode"
0xc1fc3  ldloc.s  6
0xc1fc5  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1fca  stelem.ref
0xc1fcb  dup
0xc1fcc  ldc.i4.s 9
0xc1fce  ldloc.s  4
0xc1fd0  stelem.ref
0xc1fd1  stloc.1
0xc1fd2  ldarg.3
0xc1fd3  ldloc.1
0xc1fd4  newobj   instance void Row::.ctor(string[] columns)
0xc1fd9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc1fde  pop
0xc1fdf  ldloc.s  6
0xc1fe1  ldc.i4.1
0xc1fe2  add
0xc1fe3  stloc.s  6
0xc1fe5  ldloc.s  6
0xc1fe7  ldloc.s  5
0xc1fe9  blt      loc_C1F3A
0xc1fee  ldloc.2
0xc1fef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc1ff4  brtrue   loc_C1EF2
0xc1ff9  leave.s  loc_C200F
0xc1ffb  ldloc.2
0xc1ffc  isinst   [mscorlib]System.IDisposable
0xc2001  stloc.s  7
0xc2003  ldloc.s  7
0xc2005  brfalse.s loc_C200E
0xc2007  ldloc.s  7
0xc2009  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc200e  endfinally
0xc200f  ret
```
