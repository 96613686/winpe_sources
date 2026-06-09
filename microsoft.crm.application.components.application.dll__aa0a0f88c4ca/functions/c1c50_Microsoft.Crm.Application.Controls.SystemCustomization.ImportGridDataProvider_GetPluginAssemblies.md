# Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetPluginAssemblies

- ea: `0xc1c50`
- end: `0xc1d90`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetPluginAssemblies`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xc0af0`

## callees

- `0xc1c50`
- `0xc3eb0`
- `0xf4210`

## string_xrefs

- `0xc1c51`: `EntityGridDataProvider_Types_PluginAssembly`
- `0xc1c5d`: `importexportxml/SolutionPluginAssemblies/PluginAssembly`
- `0xc1cc3`: `pluginassembly:`

## pseudocode

```c

```

## disassembly

```asm
0xc1c50  ldarg.1
0xc1c51  ldstr    aEntitygriddata_32// "EntityGridDataProvider_Types_PluginAsse"...
0xc1c56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1c5b  stloc.0
0xc1c5c  ldarg.2
0xc1c5d  ldstr    aImportexportxm_5// "importexportxml/SolutionPluginAssemblie"...
0xc1c62  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc1c67  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xc1c6c  stloc.2
0xc1c6d  br       loc_C1D6E
0xc1c72  ldloc.2
0xc1c73  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc1c78  castclass [System.Xml]System.Xml.XmlNode
0xc1c7d  stloc.3
0xc1c7e  ldloc.3
0xc1c7f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1c84  ldstr    aName// "name"
0xc1c89  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1c8e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1c93  stloc.s  4
0xc1c95  ldloc.3
0xc1c96  ldstr    aResult// "result"
0xc1c9b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc1ca0  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xc1ca5  stloc.s  5
0xc1ca7  ldloc.s  5
0xc1ca9  brfalse.s loc_C1CAF
0xc1cab  ldloc.s  5
0xc1cad  br.s     loc_C1CB0
0xc1caf  ldc.i4.1
0xc1cb0  stloc.s  5
0xc1cb2  ldc.i4.0
0xc1cb3  stloc.s  6
0xc1cb5  br       loc_C1D65
0xc1cba  ldc.i4.s 0xA
0xc1cbc  newarr   [mscorlib]System.String
0xc1cc1  dup
0xc1cc2  ldc.i4.0
0xc1cc3  ldstr    aPluginassembly// "pluginassembly:"
0xc1cc8  ldloc.3
0xc1cc9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1cce  ldstr    aId_1// "id"
0xc1cd3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1cd8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1cdd  call     string [mscorlib]System.String::Concat(string, string)
0xc1ce2  stelem.ref
0xc1ce3  dup
0xc1ce4  ldc.i4.1
0xc1ce5  ldc.i4   0x11FD
0xc1cea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc1cef  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc1cf4  stelem.ref
0xc1cf5  dup
0xc1cf6  ldc.i4.2
0xc1cf7  ldloc.s  4
0xc1cf9  stelem.ref
0xc1cfa  dup
0xc1cfb  ldc.i4.3
0xc1cfc  ldloc.s  4
0xc1cfe  stelem.ref
0xc1cff  dup
0xc1d00  ldc.i4.4
0xc1d01  ldloc.0
0xc1d02  stelem.ref
0xc1d03  dup
0xc1d04  ldc.i4.5
0xc1d05  ldloc.3
0xc1d06  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc1d0b  ldstr    aDescription_0// "Description"
0xc1d10  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc1d15  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc1d1a  stelem.ref
0xc1d1b  dup
0xc1d1c  ldc.i4.6
0xc1d1d  ldloc.3
0xc1d1e  ldstr    aResult// "result"
0xc1d23  ldloc.s  6
0xc1d25  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1d2a  stelem.ref
0xc1d2b  dup
0xc1d2c  ldc.i4.7
0xc1d2d  ldloc.3
0xc1d2e  ldstr    aDatetimeticks// "datetimeticks"
0xc1d33  ldloc.s  6
0xc1d35  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1d3a  stelem.ref
0xc1d3b  dup
0xc1d3c  ldc.i4.8
0xc1d3d  ldloc.3
0xc1d3e  ldstr    aErrorcode_0// "errorcode"
0xc1d43  ldloc.s  6
0xc1d45  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc1d4a  stelem.ref
0xc1d4b  dup
0xc1d4c  ldc.i4.s 9
0xc1d4e  ldloc.s  4
0xc1d50  stelem.ref
0xc1d51  stloc.1
0xc1d52  ldarg.3
0xc1d53  ldloc.1
0xc1d54  newobj   instance void Row::.ctor(string[] columns)
0xc1d59  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc1d5e  pop
0xc1d5f  ldloc.s  6
0xc1d61  ldc.i4.1
0xc1d62  add
0xc1d63  stloc.s  6
0xc1d65  ldloc.s  6
0xc1d67  ldloc.s  5
0xc1d69  blt      loc_C1CBA
0xc1d6e  ldloc.2
0xc1d6f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc1d74  brtrue   loc_C1C72
0xc1d79  leave.s  loc_C1D8F
0xc1d7b  ldloc.2
0xc1d7c  isinst   [mscorlib]System.IDisposable
0xc1d81  stloc.s  7
0xc1d83  ldloc.s  7
0xc1d85  brfalse.s loc_C1D8E
0xc1d87  ldloc.s  7
0xc1d89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc1d8e  endfinally
0xc1d8f  ret
```
