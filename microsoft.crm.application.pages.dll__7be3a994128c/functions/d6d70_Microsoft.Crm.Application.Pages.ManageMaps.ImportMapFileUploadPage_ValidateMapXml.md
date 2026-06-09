# Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::ValidateMapXml

- ea: `0xd6d70`
- end: `0xd72fe`
- name: `Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::ValidateMapXml`
- size: `1422`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd75c0`

## callees

- `0xd6d70`
- `0xd7300`
- `0xd7510`

## string_xrefs

- `0xd70b1`: `createdon`
- `0xd6dc2`: `ImportMap_Error_NotWellFormedXml`
- `0xd6e51`: `ValidateImportMapXml hit exception. Message: {0} Details: {1}`
- `0xd6e77`: `ImportMap_Error_InvalidImportXml`
- `0xd6ec7`: `ImportMap_Error_InvalidImportXml`
- `0xd6f33`: `ImportMap_Error_InvalidImportXml`
- `0xd70bf`: `overriddencreatedon`
- `0xd71fe`: `ImportMap_Error_AttributeNotValidForCreate`

## pseudocode

```c

```

## disassembly

```asm
0xd6d70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xd6d75  stloc.0
0xd6d76  ldsfld   string [mscorlib]System.String::Empty
0xd6d7b  stloc.1
0xd6d7c  ldnull
0xd6d7d  stloc.2
0xd6d7e  ldarg.0
0xd6d7f  ldfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapXml
0xd6d84  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xd6d89  stloc.2
0xd6d8a  leave.s  loc_D6DDD
0xd6d8c  stloc.s  8
0xd6d8e  ldloc.s  8
0xd6d90  ldarg.0
0xd6d91  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xd6d96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xd6d9b  ldc.i4.0
0xd6d9c  ldstr    aErrorCouldNotP// "Error! Could not parse input file. Mess"...
0xd6da1  ldc.i4.2
0xd6da2  newarr   [mscorlib]System.Object
0xd6da7  dup
0xd6da8  ldc.i4.0
0xd6da9  ldloc.s  8
0xd6dab  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd6db0  stelem.ref
0xd6db1  dup
0xd6db2  ldc.i4.1
0xd6db3  ldloc.s  8
0xd6db5  stelem.ref
0xd6db6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6dbb  ldarg.0
0xd6dbc  ldarg.0
0xd6dbd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6dc2  ldstr    aImportmapError// "ImportMap_Error_NotWellFormedXml"
0xd6dc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6dcc  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd6dd1  ldarg.0
0xd6dd2  ldc.i4.1
0xd6dd3  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd6dd8  leave    loc_D72FD
0xd6ddd  ldarg.0
0xd6dde  ldloc.2
0xd6ddf  call     instance void Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::AddDummyTargetValueForIgnoredPicklistMap(class [System.Xml]System.Xml.XmlDocument mapDoc)
0xd6de4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xd6de9  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0xd6dee  ldstr    aResourcesImpor_1// "/_resources/ImportMapSchema.xsd"
0xd6df3  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0xd6df8  stloc.3
0xd6df9  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::.ctor()
0xd6dfe  stloc.s  4
0xd6e00  ldloc.s  4
0xd6e02  ldnull
0xd6e03  ldloc.3
0xd6e04  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0xd6e09  pop
0xd6e0a  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0xd6e0f  stloc.s  5
0xd6e11  ldloc.s  5
0xd6e13  ldc.i4.4
0xd6e14  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0xd6e19  ldloc.s  5
0xd6e1b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0xd6e20  ldloc.s  4
0xd6e22  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchemaSet)
0xd6e27  ldloc.2
0xd6e28  newobj   instance void [System.Xml]System.Xml.XmlNodeReader::.ctor(class [System.Xml]System.Xml.XmlNode)
0xd6e2d  ldloc.s  5
0xd6e2f  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.XmlReaderSettings)
0xd6e34  stloc.s  6
0xd6e36  ldloc.s  6
0xd6e38  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xd6e3d  brtrue.s loc_D6E36
0xd6e3f  leave.s  loc_D6E92
0xd6e41  stloc.s  9
0xd6e43  ldloc.s  9
0xd6e45  ldarg.0
0xd6e46  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xd6e4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xd6e50  ldc.i4.0
0xd6e51  ldstr    aValidateimport// "ValidateImportMapXml hit exception. Mes"...
0xd6e56  ldc.i4.2
0xd6e57  newarr   [mscorlib]System.Object
0xd6e5c  dup
0xd6e5d  ldc.i4.0
0xd6e5e  ldloc.s  9
0xd6e60  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd6e65  stelem.ref
0xd6e66  dup
0xd6e67  ldc.i4.1
0xd6e68  ldloc.s  9
0xd6e6a  stelem.ref
0xd6e6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6e70  ldarg.0
0xd6e71  ldarg.0
0xd6e72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6e77  ldstr    aImportmapError_0// "ImportMap_Error_InvalidImportXml"
0xd6e7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6e81  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd6e86  ldarg.0
0xd6e87  ldc.i4.1
0xd6e88  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd6e8d  leave    loc_D72FD
0xd6e92  ldloc.2
0xd6e93  ldstr    aMap// "/Map"
0xd6e98  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xd6e9d  stloc.s  7
0xd6e9f  ldloc.s  7
0xd6ea1  brtrue.s loc_D6EDE
0xd6ea3  ldnull
0xd6ea4  ldarg.0
0xd6ea5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xd6eaa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xd6eaf  ldc.i4.0
0xd6eb0  ldstr    aRootNodeNotPre// "Root node not present in Map."
0xd6eb5  ldc.i4.0
0xd6eb6  newarr   [mscorlib]System.Object
0xd6ebb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6ec0  ldarg.0
0xd6ec1  ldarg.0
0xd6ec2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6ec7  ldstr    aImportmapError_0// "ImportMap_Error_InvalidImportXml"
0xd6ecc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6ed1  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd6ed6  ldarg.0
0xd6ed7  ldc.i4.1
0xd6ed8  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd6edd  ret
0xd6ede  ldloc.s  7
0xd6ee0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xd6ee5  ldstr    aName_0// "Name"
0xd6eea  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xd6eef  brfalse.s loc_D6F0F
0xd6ef1  ldarg.0
0xd6ef2  ldloc.s  7
0xd6ef4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xd6ef9  ldstr    aName_0// "Name"
0xd6efe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xd6f03  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xd6f08  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapName
0xd6f0d  br.s     loc_D6F4A
0xd6f0f  ldnull
0xd6f10  ldarg.0
0xd6f11  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xd6f16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xd6f1b  ldc.i4.0
0xd6f1c  ldstr    aMapDoesNotHave// "Map does not have Name attribute"
0xd6f21  ldc.i4.0
0xd6f22  newarr   [mscorlib]System.Object
0xd6f27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6f2c  ldarg.0
0xd6f2d  ldarg.0
0xd6f2e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6f33  ldstr    aImportmapError_0// "ImportMap_Error_InvalidImportXml"
0xd6f38  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6f3d  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd6f42  ldarg.0
0xd6f43  ldc.i4.1
0xd6f44  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd6f49  ret
0xd6f4a  ldloc.2
0xd6f4b  ldstr    aMapEntitymapsE_1// "/Map/EntityMaps/EntityMap"
0xd6f50  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xd6f55  stloc.s  0xA
0xd6f57  ldloc.s  0xA
0xd6f59  brfalse  loc_D72C8
0xd6f5e  ldloc.s  0xA
0xd6f60  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xd6f65  stloc.s  0xB
0xd6f67  br       loc_D72A5
0xd6f6c  ldloc.s  0xB
0xd6f6e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd6f73  castclass [System.Xml]System.Xml.XmlNode
0xd6f78  stloc.s  0xC
0xd6f7a  ldloc.s  0xC
0xd6f7c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xd6f81  ldstr    aTargetentityna_0// "TargetEntityName"
0xd6f86  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xd6f8b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xd6f90  stloc.s  0xD
0xd6f92  ldnull
0xd6f93  stloc.s  0xE
0xd6f95  ldsfld   string [mscorlib]System.String::Empty
0xd6f9a  stloc.s  0xF
0xd6f9c  ldarg.0
0xd6f9d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xd6fa2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xd6fa7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd6fac  stloc.s  0x10
0xd6fae  ldloc.s  0x10
0xd6fb0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd6fb5  ldloc.s  0xD
0xd6fb7  ldc.i4.1
0xd6fb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xd6fbd  stloc.s  0xE
0xd6fbf  ldloc.s  0xE
0xd6fc1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xd6fc6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6fcb  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd6fd0  ldloc.s  0x10
0xd6fd2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd6fd7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xd6fdc  stloc.s  0xF
0xd6fde  leave.s  loc_D7042
0xd6fe0  pop
0xd6fe1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd6fe6  ldarg.0
0xd6fe7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd6fec  ldstr    aImportmapError_1// "ImportMap_Error_InvalidEntityName"
0xd6ff1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6ff6  ldc.i4.1
0xd6ff7  newarr   [mscorlib]System.Object
0xd6ffc  dup
0xd6ffd  ldc.i4.0
0xd6ffe  ldloc.s  0xD
0xd7000  stelem.ref
0xd7001  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd7006  stloc.1
0xd7007  ldloc.0
0xd7008  ldloc.1
0xd7009  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xd700e  pop
0xd700f  ldarg.0
0xd7010  ldc.i4.1
0xd7011  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd7016  ldarg.0
0xd7017  ldloc.0
0xd7018  callvirt instance string [mscorlib]System.Object::ToString()
0xd701d  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd7022  ldarg.0
0xd7023  ldarg.0
0xd7024  ldfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd7029  ldstr    asc_14103E// "\r\n"
0xd702e  ldstr    asc_113A60// ";"
0xd7033  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd7038  stfld    string Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::validationErrors
0xd703d  leave    loc_D72FD
0xd7042  ldloc.s  0xC
0xd7044  ldstr    aAttributemapsA// "AttributeMaps/AttributeMap"
0xd7049  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xd704e  stloc.s  0x11
0xd7050  ldloc.s  0x11
0xd7052  brfalse  loc_D7297
0xd7057  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xd705c  stloc.s  0x12
0xd705e  ldloc.s  0x11
0xd7060  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xd7065  stloc.s  0x13
0xd7067  br       loc_D7274
0xd706c  ldloc.s  0x13
0xd706e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd7073  castclass [System.Xml]System.Xml.XmlNode
0xd7078  stloc.s  0x14
0xd707a  ldloc.s  0x14
0xd707c  ldstr    aTargetattribut// "TargetAttributeName"
0xd7081  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xd7086  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xd708b  stloc.s  0x15
0xd708d  ldloc.s  0x14
0xd708f  ldstr    aSourceattribut_0// "SourceAttributeName"
0xd7094  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xd7099  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xd709e  stloc.s  0x16
0xd70a0  ldloc.s  0x14
0xd70a2  ldstr    aProcesscode// "ProcessCode"
0xd70a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xd70ac  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xd70b1  ldstr    aCreatedon// "createdon"
0xd70b6  ldloc.s  0x15
0xd70b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd70bd  brfalse.s loc_D70C6
0xd70bf  ldstr    aOverriddencrea// "overriddencreatedon"
0xd70c4  stloc.s  0x15
0xd70c6  ldc.i4.1
0xd70c7  stloc.s  0x17
0xd70c9  ldloca.s 0x17
0xd70cb  constrained. ProcessCodeEnum
0xd70d1  callvirt instance string [mscorlib]System.Object::ToString()
0xd70d6  ldc.i4.5
0xd70d7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd70dc  brtrue   loc_D7274
0xd70e1  ldloc.s  0x12
0xd70e3  ldloc.s  0x15
0xd70e5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0xd70ea  brfalse.s loc_D7128
0xd70ec  ldarg.0
0xd70ed  ldc.i4.1
0xd70ee  stfld    bool Microsoft.Crm.Application.Pages.ManageMaps.ImportMapFileUploadPage::mapValidationErrorOccurred
0xd70f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd70f8  ldarg.0
0xd70f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd70fe  ldstr    aErrorMessage0x_33// "Error_Message_0x8004033e"
0xd7103  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd7108  ldc.i4.2
0xd7109  newarr   [mscorlib]System.Object
0xd710e  dup
0xd710f  ldc.i4.0
0xd7110  ldloc.s  0xF
0xd7112  stelem.ref
0xd7113  dup
0xd7114  ldc.i4.1
  ... truncated ...
```
