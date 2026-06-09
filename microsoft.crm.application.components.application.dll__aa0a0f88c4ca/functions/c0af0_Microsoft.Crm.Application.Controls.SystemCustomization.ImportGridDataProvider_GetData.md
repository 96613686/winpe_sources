# Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetData

- ea: `0xc0af0`
- end: `0xc161f`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetData`
- size: `2863`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xc0af0`
- `0xc1620`
- `0xc17f0`
- `0xc1940`
- `0xc1a80`
- `0xc1c50`
- `0xc1d90`
- `0xc1ed0`
- `0xc2010`
- `0xc2220`
- `0xc2370`
- `0xc24c0`
- `0xc2610`
- `0xc2860`
- `0xc2a40`
- `0xc2b10`
- `0xc2c70`
- `0xc2db0`
- `0xc2ef0`
- `0xc3040`
- `0xc3190`
- `0xc32a0`
- `0xc33e0`
- `0xc3660`
- `0xc37f0`
- `0xc3950`
- `0xc3a90`
- `0xc3ae0`
- `0xc3ba0`
- `0xc3d20`
- `0xc3ea0`
- `0xf4210`

## string_xrefs

- `0xc0c11`: `EntityGridDataProvider_Types_ClientExtensions`
- `0xc0d8d`: `EntityGridDataProvider_Types_ClientExtensions`
- `0xc0b02`: `importxml`
- `0xc0b98`: `importexportxml/nodes/node`
- `0xc0bd2`: `isvconfig`
- `0xc0bea`: `node:isvconfig`
- `0xc0bfb`: `EntityGridDataProvider_ISVConfig`
- `0xc0c1f`: `EntityGridDataProvider_ISVConfig_Description`
- `0xc0e10`: `importexportxml/settings/setting`

## pseudocode

```c

```

## disassembly

```asm
0xc0af0  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xc0af5  stloc.0
0xc0af6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc0afb  stloc.1
0xc0afc  ldarg.0
0xc0afd  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc0b02  ldstr    aImportxml// "importxml"
0xc0b07  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc0b0c  stloc.2
0xc0b0d  ldloc.2
0xc0b0e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xc0b13  stloc.3
0xc0b14  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xc0b19  stloc.s  5
0xc0b1b  ldarg.0
0xc0b1c  ldloc.1
0xc0b1d  ldloc.3
0xc0b1e  ldloc.0
0xc0b1f  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetFileUpgrade(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b24  ldarg.0
0xc0b25  ldloc.1
0xc0b26  ldloc.3
0xc0b27  ldloc.0
0xc0b28  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetFileSkuUpgrade(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b2d  ldarg.0
0xc0b2e  ldloc.1
0xc0b2f  ldloc.3
0xc0b30  ldloc.0
0xc0b31  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetFileXsdValidation(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b36  ldarg.0
0xc0b37  ldloc.1
0xc0b38  ldloc.3
0xc0b39  ldloc.0
0xc0b3a  ldloc.s  5
0xc0b3c  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetEntities(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xc0b41  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xc0b46  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xc0b4b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0xc0b50  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xc0b55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc0b5a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc0b5f  brfalse.s loc_C0B73
0xc0b61  ldarg.0
0xc0b62  ldloc.1
0xc0b63  ldloc.3
0xc0b64  ldloc.0
0xc0b65  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetApps(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b6a  ldarg.0
0xc0b6b  ldloc.1
0xc0b6c  ldloc.3
0xc0b6d  ldloc.0
0xc0b6e  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetAppSitmaps(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b73  ldarg.0
0xc0b74  ldloc.1
0xc0b75  ldloc.3
0xc0b76  ldloc.0
0xc0b77  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetRelationships(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b7c  ldarg.0
0xc0b7d  ldloc.1
0xc0b7e  ldloc.3
0xc0b7f  ldloc.0
0xc0b80  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetCalculatedFields(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDocument, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b85  ldarg.0
0xc0b86  ldloc.1
0xc0b87  ldloc.3
0xc0b88  ldloc.0
0xc0b89  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetDateTimeFields(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDocument, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b8e  ldarg.0
0xc0b8f  ldloc.1
0xc0b90  ldloc.3
0xc0b91  ldloc.0
0xc0b92  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetEntityMaps(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager rm, class [System.Xml]System.Xml.XmlDocument importXmlDoc, class [mscorlib]System.Collections.ArrayList itemList)
0xc0b97  ldloc.3
0xc0b98  ldstr    aImportexportxm// "importexportxml/nodes/node"
0xc0b9d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc0ba2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xc0ba7  stloc.s  6
0xc0ba9  br       loc_C0DEC
0xc0bae  ldloc.s  6
0xc0bb0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc0bb5  castclass [System.Xml]System.Xml.XmlNode
0xc0bba  stloc.s  7
0xc0bbc  ldloc.s  7
0xc0bbe  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc0bc3  ldstr    aId_1// "id"
0xc0bc8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xc0bcd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc0bd2  ldstr    aIsvconfig// "isvconfig"
0xc0bd7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc0bdc  brfalse  loc_C0C75
0xc0be1  ldc.i4.s 0xA
0xc0be3  newarr   [mscorlib]System.String
0xc0be8  dup
0xc0be9  ldc.i4.0
0xc0bea  ldstr    aNodeIsvconfig// "node:isvconfig"
0xc0bef  stelem.ref
0xc0bf0  dup
0xc0bf1  ldc.i4.1
0xc0bf2  ldstr    aSystementityGi// "systemEntity.gif"
0xc0bf7  stelem.ref
0xc0bf8  dup
0xc0bf9  ldc.i4.2
0xc0bfa  ldloc.1
0xc0bfb  ldstr    aEntitygriddata_2// "EntityGridDataProvider_ISVConfig"
0xc0c00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0c05  stelem.ref
0xc0c06  dup
0xc0c07  ldc.i4.3
0xc0c08  ldstr    asc_F537C// ""
0xc0c0d  stelem.ref
0xc0c0e  dup
0xc0c0f  ldc.i4.4
0xc0c10  ldloc.1
0xc0c11  ldstr    aEntitygriddata// "EntityGridDataProvider_Types_ClientExte"...
0xc0c16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0c1b  stelem.ref
0xc0c1c  dup
0xc0c1d  ldc.i4.5
0xc0c1e  ldloc.1
0xc0c1f  ldstr    aEntitygriddata_3// "EntityGridDataProvider_ISVConfig_Descri"...
0xc0c24  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0c29  stelem.ref
0xc0c2a  dup
0xc0c2b  ldc.i4.6
0xc0c2c  ldloc.s  7
0xc0c2e  ldstr    aResult// "result"
0xc0c33  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0c38  stelem.ref
0xc0c39  dup
0xc0c3a  ldc.i4.7
0xc0c3b  ldloc.s  7
0xc0c3d  ldstr    aDatetimeticks// "datetimeticks"
0xc0c42  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0c47  stelem.ref
0xc0c48  dup
0xc0c49  ldc.i4.8
0xc0c4a  ldloc.s  7
0xc0c4c  ldstr    aErrorcode_0// "errorcode"
0xc0c51  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0c56  stelem.ref
0xc0c57  dup
0xc0c58  ldc.i4.s 9
0xc0c5a  ldsfld   string [mscorlib]System.String::Empty
0xc0c5f  stelem.ref
0xc0c60  stloc.s  4
0xc0c62  ldloc.0
0xc0c63  ldloc.s  4
0xc0c65  newobj   instance void Row::.ctor(string[] columns)
0xc0c6a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc0c6f  pop
0xc0c70  br       loc_C0DEC
0xc0c75  ldloc.s  7
0xc0c77  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc0c7c  ldstr    aId_1// "id"
0xc0c81  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xc0c86  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc0c8b  ldstr    aRelationshipro// "relationshiproles"
0xc0c90  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc0c95  brfalse  loc_C0D38
0xc0c9a  ldc.i4.s 0xA
0xc0c9c  newarr   [mscorlib]System.String
0xc0ca1  dup
0xc0ca2  ldc.i4.0
0xc0ca3  ldstr    aNodeRelationsh// "node:relationshiproles"
0xc0ca8  stelem.ref
0xc0ca9  dup
0xc0caa  ldc.i4.1
0xc0cab  ldc.i4   0x1194
0xc0cb0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc0cb5  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc0cba  stelem.ref
0xc0cbb  dup
0xc0cbc  ldc.i4.2
0xc0cbd  ldloc.1
0xc0cbe  ldstr    aEntitygriddata_4// "EntityGridDataProvider_RelationshipRole"...
0xc0cc3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0cc8  stelem.ref
0xc0cc9  dup
0xc0cca  ldc.i4.3
0xc0ccb  ldstr    asc_F537C// ""
0xc0cd0  stelem.ref
0xc0cd1  dup
0xc0cd2  ldc.i4.4
0xc0cd3  ldloc.1
0xc0cd4  ldstr    aEntitygriddata_5// "EntityGridDataProvider_Types_Relationsh"...
0xc0cd9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0cde  stelem.ref
0xc0cdf  dup
0xc0ce0  ldc.i4.5
0xc0ce1  ldloc.1
0xc0ce2  ldstr    aEntitygriddata_6// "EntityGridDataProvider_RelationshipRole"...
0xc0ce7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0cec  stelem.ref
0xc0ced  dup
0xc0cee  ldc.i4.6
0xc0cef  ldloc.s  7
0xc0cf1  ldstr    aResult// "result"
0xc0cf6  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0cfb  stelem.ref
0xc0cfc  dup
0xc0cfd  ldc.i4.7
0xc0cfe  ldloc.s  7
0xc0d00  ldstr    aDatetimeticks// "datetimeticks"
0xc0d05  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0d0a  stelem.ref
0xc0d0b  dup
0xc0d0c  ldc.i4.8
0xc0d0d  ldloc.s  7
0xc0d0f  ldstr    aErrorcode_0// "errorcode"
0xc0d14  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0d19  stelem.ref
0xc0d1a  dup
0xc0d1b  ldc.i4.s 9
0xc0d1d  ldsfld   string [mscorlib]System.String::Empty
0xc0d22  stelem.ref
0xc0d23  stloc.s  4
0xc0d25  ldloc.0
0xc0d26  ldloc.s  4
0xc0d28  newobj   instance void Row::.ctor(string[] columns)
0xc0d2d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc0d32  pop
0xc0d33  br       loc_C0DEC
0xc0d38  ldloc.s  7
0xc0d3a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc0d3f  ldstr    aId_1// "id"
0xc0d44  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xc0d49  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc0d4e  ldstr    aSitemap_1// "sitemap"
0xc0d53  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc0d58  brfalse  loc_C0DEC
0xc0d5d  ldc.i4.s 0xA
0xc0d5f  newarr   [mscorlib]System.String
0xc0d64  dup
0xc0d65  ldc.i4.0
0xc0d66  ldstr    aNodeSitemap// "node:sitemap"
0xc0d6b  stelem.ref
0xc0d6c  dup
0xc0d6d  ldc.i4.1
0xc0d6e  ldstr    aSystementityGi// "systemEntity.gif"
0xc0d73  stelem.ref
0xc0d74  dup
0xc0d75  ldc.i4.2
0xc0d76  ldloc.1
0xc0d77  ldstr    aEntitygriddata_0// "EntityGridDataProvider_SiteMap"
0xc0d7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0d81  stelem.ref
0xc0d82  dup
0xc0d83  ldc.i4.3
0xc0d84  ldstr    asc_F537C// ""
0xc0d89  stelem.ref
0xc0d8a  dup
0xc0d8b  ldc.i4.4
0xc0d8c  ldloc.1
0xc0d8d  ldstr    aEntitygriddata// "EntityGridDataProvider_Types_ClientExte"...
0xc0d92  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0d97  stelem.ref
0xc0d98  dup
0xc0d99  ldc.i4.5
0xc0d9a  ldloc.1
0xc0d9b  ldstr    aEntitygriddata_7// "EntityGridDataProvider_SiteMap_Descript"...
0xc0da0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc0da5  stelem.ref
0xc0da6  dup
0xc0da7  ldc.i4.6
0xc0da8  ldloc.s  7
0xc0daa  ldstr    aResult// "result"
0xc0daf  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0db4  stelem.ref
0xc0db5  dup
0xc0db6  ldc.i4.7
0xc0db7  ldloc.s  7
0xc0db9  ldstr    aDatetimeticks// "datetimeticks"
0xc0dbe  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0dc3  stelem.ref
0xc0dc4  dup
0xc0dc5  ldc.i4.8
0xc0dc6  ldloc.s  7
0xc0dc8  ldstr    aErrorcode_0// "errorcode"
0xc0dcd  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p)
0xc0dd2  stelem.ref
0xc0dd3  dup
0xc0dd4  ldc.i4.s 9
0xc0dd6  ldsfld   string [mscorlib]System.String::Empty
0xc0ddb  stelem.ref
0xc0ddc  stloc.s  4
0xc0dde  ldloc.0
0xc0ddf  ldloc.s  4
0xc0de1  newobj   instance void Row::.ctor(string[] columns)
0xc0de6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc0deb  pop
0xc0dec  ldloc.s  6
0xc0dee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc0df3  brtrue   loc_C0BAE
0xc0df8  leave.s  loc_C0E0F
0xc0dfa  ldloc.s  6
0xc0dfc  isinst   [mscorlib]System.IDisposable
0xc0e01  stloc.s  8
0xc0e03  ldloc.s  8
0xc0e05  brfalse.s loc_C0E0E
0xc0e07  ldloc.s  8
  ... truncated ...
```
