# Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::ConvertToExcelFormat

- ea: `0x32e10`
- end: `0x33528`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::ConvertToExcelFormat`
- size: `1816`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x66d40`

## callees

- `0x32e10`
- `0x33530`
- `0x33630`
- `0x33660`
- `0x33d60`
- `0x33d80`
- `0x33da0`
- `0x33dd0`
- `0x33de0`
- `0x33df0`
- `0x340f0`
- `0x341d0`
- `0x34340`
- `0x344c0`
- `0x345c0`
- `0x96420`

## string_xrefs

- `0x32e2b`: `importexportxml`
- `0x32f44`: `ImportJobTemplate.xml is invalid. No worksheet {0} found`
- `0x3332d`: `ImportJobTemplate.xml is invalid. No worksheet {0} found`
- `0x32f6e`: `importexportxml/solutionManifests/solutionManifest`
- `0x3331d`: `Components`
- `0x3333a`: `Components`
- `0x33357`: `importexportxml/*/*`

## pseudocode

```c

```

## disassembly

```asm
0x32e10  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x32e15  stloc.0
0x32e16  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x32e1b  stloc.1
0x32e1c  ldarg.0
0x32e1d  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::LoadTemplate()
0x32e22  stloc.2
0x32e23  ldarg.1
0x32e24  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x32e29  stloc.3
0x32e2a  ldloc.3
0x32e2b  ldstr    aImportexportxm_95// "importexportxml"
0x32e30  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32e35  stloc.s  4
0x32e37  ldarg.0
0x32e38  ldarg.2
0x32e39  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32e3e  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_mdCache
0x32e43  ldarg.0
0x32e44  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_mdCache
0x32e49  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x32e4e  stloc.s  5
0x32e50  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x32e55  stloc.s  6
0x32e57  ldarg.0
0x32e58  ldarg.2
0x32e59  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_context
0x32e5e  ldarg.0
0x32e5f  ldarg.2
0x32e60  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x32e65  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x32e6a  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x32e6f  ldstr    asc_9A18C// ""
0x32e74  stloc.s  7
0x32e76  ldloc.s  4
0x32e78  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x32e7d  ldstr    aStart// "start"
0x32e82  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x32e87  brfalse  loc_32F27
0x32e8c  ldloc.s  4
0x32e8e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x32e93  ldstr    aStop// "stop"
0x32e98  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x32e9d  brfalse  loc_32F27
0x32ea2  ldloc.s  4
0x32ea4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x32ea9  ldstr    aStart// "start"
0x32eae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x32eb3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x32eb8  stloc.s  9
0x32eba  ldloc.s  4
0x32ebc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x32ec1  ldstr    aStop// "stop"
0x32ec6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x32ecb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x32ed0  stloc.s  0xA
0x32ed2  ldloca.s 0
0x32ed4  ldloc.s  9
0x32ed6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32edb  call     int64 [mscorlib]System.Convert::ToInt64(string, class [mscorlib]System.IFormatProvider)
0x32ee0  call     instance void [mscorlib]System.DateTime::.ctor(int64)
0x32ee5  ldloca.s 1
0x32ee7  ldloc.s  0xA
0x32ee9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32eee  call     int64 [mscorlib]System.Convert::ToInt64(string, class [mscorlib]System.IFormatProvider)
0x32ef3  call     instance void [mscorlib]System.DateTime::.ctor(int64)
0x32ef8  ldloc.1
0x32ef9  ldloc.0
0x32efa  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x32eff  stloc.s  0xB
0x32f01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32f06  ldstr    a000// "{0:0.0}"
0x32f0b  ldc.i4.1
0x32f0c  newarr   [mscorlib]System.Object
0x32f11  dup
0x32f12  ldc.i4.0
0x32f13  ldloca.s 0xB
0x32f15  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x32f1a  box      [mscorlib]System.Double
0x32f1f  stelem.ref
0x32f20  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32f25  stloc.s  7
0x32f27  ldarg.0
0x32f28  ldloc.2
0x32f29  ldstr    aSolution// "Solution"
0x32f2e  call     instance class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::ReadRowNodes(class [System.Xml]System.Xml.XmlDocument xdoc, string worksheetName)
0x32f33  stloc.s  0xC
0x32f35  ldloc.s  0xC
0x32f37  brfalse.s loc_32F44
0x32f39  ldloc.s  0xC
0x32f3b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x32f40  ldc.i4.s 0x19
0x32f42  bge.s    loc_32F6D
0x32f44  ldstr    aImportjobtempl// "ImportJobTemplate.xml is invalid. No wo"...
0x32f49  ldc.i4.1
0x32f4a  newarr   [mscorlib]System.Object
0x32f4f  dup
0x32f50  ldc.i4.0
0x32f51  ldstr    aSolution// "Solution"
0x32f56  stelem.ref
0x32f57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x32f5c  ldc.i4   0x80044251
0x32f61  ldc.i4.0
0x32f62  newarr   [mscorlib]System.Object
0x32f67  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x32f6c  throw
0x32f6d  ldloc.3
0x32f6e  ldstr    aImportexportxm_96// "importexportxml/solutionManifests/solut"...
0x32f73  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32f78  stloc.s  0xD
0x32f7a  ldarg.0
0x32f7b  ldloc.s  0xD
0x32f7d  ldstr    aLanguagecode// "languagecode"
0x32f82  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0x32f87  stloc.s  0xE
0x32f89  ldarg.0
0x32f8a  ldloc.2
0x32f8b  ldloc.s  0xC
0x32f8d  ldc.i4.1
0x32f8e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32f93  ldarg.0
0x32f94  ldloc.s  0xD
0x32f96  ldstr    aUniquename_0// "UniqueName"
0x32f9b  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x32fa0  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x32fa5  ldarg.0
0x32fa6  ldloc.2
0x32fa7  ldloc.s  0xC
0x32fa9  ldc.i4.2
0x32faa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32faf  ldarg.0
0x32fb0  ldloc.s  0xD
0x32fb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fb7  ldstr    aLocalizednames_2// "LocalizedNames/LocalizedName[@languagec"...
0x32fbc  ldc.i4.1
0x32fbd  newarr   [mscorlib]System.Object
0x32fc2  dup
0x32fc3  ldc.i4.0
0x32fc4  ldloc.s  0xE
0x32fc6  stelem.ref
0x32fc7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fcc  ldstr    aDescription// "description"
0x32fd1  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetAttribute(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath, string attributeName)
0x32fd6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x32fdb  ldarg.0
0x32fdc  ldloc.2
0x32fdd  ldloc.s  0xC
0x32fdf  ldc.i4.3
0x32fe0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x32fe5  ldarg.0
0x32fe6  ldloc.s  0xD
0x32fe8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fed  ldstr    aDescriptionsDe_1// "Descriptions/Description[@languagecode="...
0x32ff2  ldc.i4.1
0x32ff3  newarr   [mscorlib]System.Object
0x32ff8  dup
0x32ff9  ldc.i4.0
0x32ffa  ldloc.s  0xE
0x32ffc  stelem.ref
0x32ffd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x33002  ldstr    aDescription// "description"
0x33007  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetAttribute(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath, string attributeName)
0x3300c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33011  ldarg.0
0x33012  ldloc.2
0x33013  ldloc.s  0xC
0x33015  ldc.i4.4
0x33016  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3301b  ldarg.0
0x3301c  ldloc.s  0xD
0x3301e  ldstr    aVersion_0// "Version"
0x33023  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x33028  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x3302d  ldarg.0
0x3302e  ldloc.2
0x3302f  ldloc.s  0xC
0x33031  ldc.i4.5
0x33032  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33037  ldarg.0
0x33038  ldarg.0
0x33039  ldloc.s  0xD
0x3303b  ldstr    aManaged// "Managed"
0x33040  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x33045  ldloc.s  6
0x33047  ldloc.s  5
0x33049  ldarg.2
0x3304a  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetLabelForManaged(string value, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService localizedLabelService, int32 langId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3304f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33054  ldarg.0
0x33055  ldloc.2
0x33056  ldloc.s  0xC
0x33058  ldc.i4.8
0x33059  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3305e  ldarg.0
0x3305f  ldloc.s  0xD
0x33061  ldstr    aPublisherUniqu_0// "Publisher/UniqueName"
0x33066  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x3306b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33070  ldarg.0
0x33071  ldloc.2
0x33072  ldloc.s  0xC
0x33074  ldc.i4.s 9
0x33076  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3307b  ldarg.0
0x3307c  ldloc.s  0xD
0x3307e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33083  ldstr    aPublisherLocal// "Publisher/LocalizedNames/LocalizedName["...
0x33088  ldc.i4.1
0x33089  newarr   [mscorlib]System.Object
0x3308e  dup
0x3308f  ldc.i4.0
0x33090  ldloc.s  0xE
0x33092  stelem.ref
0x33093  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x33098  ldstr    aDescription// "description"
0x3309d  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetAttribute(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath, string attributeName)
0x330a2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x330a7  ldarg.0
0x330a8  ldloc.2
0x330a9  ldloc.s  0xC
0x330ab  ldc.i4.s 0xA
0x330ad  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x330b2  ldarg.0
0x330b3  ldloc.s  0xD
0x330b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x330ba  ldstr    aPublisherDescr// "Publisher/Descriptions/Description[@lan"...
0x330bf  ldc.i4.1
0x330c0  newarr   [mscorlib]System.Object
0x330c5  dup
0x330c6  ldc.i4.0
0x330c7  ldloc.s  0xE
0x330c9  stelem.ref
0x330ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x330cf  ldstr    aDescription// "description"
0x330d4  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetAttribute(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath, string attributeName)
0x330d9  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x330de  ldarg.0
0x330df  ldloc.2
0x330e0  ldloc.s  0xC
0x330e2  ldc.i4.s 0xB
0x330e4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x330e9  ldarg.0
0x330ea  ldloc.s  0xD
0x330ec  ldstr    aPublisherEmail// "Publisher/EMailAddress"
0x330f1  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x330f6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x330fb  ldarg.0
0x330fc  ldloc.2
0x330fd  ldloc.s  0xC
0x330ff  ldc.i4.s 0xC
0x33101  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33106  ldarg.0
0x33107  ldloc.s  0xD
0x33109  ldstr    aPublisherSuppo// "Publisher/SupportingWebsiteUrl"
0x3310e  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x33113  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33118  ldarg.0
0x33119  ldloc.2
0x3311a  ldloc.s  0xC
0x3311c  ldc.i4.s 0xD
0x3311e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33123  ldarg.0
0x33124  ldloc.s  0xD
0x33126  ldstr    aPublisherAddre// "Publisher/Addresses/Address/City"
0x3312b  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x33130  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33135  ldarg.0
0x33136  ldloc.2
0x33137  ldloc.s  0xC
0x33139  ldc.i4.s 0xE
0x3313b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33140  ldarg.0
0x33141  ldloc.s  0xD
0x33143  ldstr    aPublisherAddre_0// "Publisher/Addresses/Address/Country"
0x33148  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x3314d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x33152  ldarg.0
0x33153  ldloc.2
0x33154  ldloc.s  0xC
0x33156  ldc.i4.s 0xF
0x33158  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3315d  ldarg.0
0x3315e  ldloc.s  0xD
0x33160  ldstr    aPublisherAddre_1// "Publisher/Addresses/Address/Line1"
0x33165  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x3316a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x3316f  ldarg.0
0x33170  ldloc.2
0x33171  ldloc.s  0xC
0x33173  ldc.i4.s 0x10
0x33175  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x3317a  ldarg.0
0x3317b  ldloc.s  0xD
0x3317d  ldstr    aPublisherAddre_2// "Publisher/Addresses/Address/Line2"
0x33182  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetItem(class [System.Xml]System.Xml.XmlNode parentNode, string nodePath)
0x33187  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::CreateCell(class [System.Xml]System.Xml.XmlDocument xdoc, class [System.Xml]System.Xml.XmlNode parent, string content)
0x3318c  ldarg.0
0x3318d  ldloc.2
0x3318e  ldloc.s  0xC
0x33190  ldc.i4.s 0x11
  ... truncated ...
```
