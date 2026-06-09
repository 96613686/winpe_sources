# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::WriteEntitySubNode

- ea: `0xc7790`
- end: `0xc85b4`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::WriteEntitySubNode`
- size: `3620`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc6ee0`

## callees

- `0xc6e10`
- `0xc7240`
- `0xc7390`
- `0xc7790`

## string_xrefs

- `0xc787d`: `areaSolutionComponent`
- `0xc79b3`: `areaSolutionComponent`
- `0xc7ae4`: `areaSolutionComponent`
- `0xc7c07`: `areaSolutionComponent`
- `0xc7d4d`: `areaSolutionComponent`
- `0xc7e74`: `areaSolutionComponent`
- `0xc7f87`: `areaSolutionComponent`
- `0xc80ea`: `areaSolutionComponent`
- `0xc81c5`: `areaSolutionComponent`
- `0xc8303`: `areaSolutionComponent`
- `0xc8435`: `areaSolutionComponent`
- `0xc8556`: `areaSolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0xc7790  ldsfld   string [mscorlib]System.String::Empty
0xc7795  stloc.0
0xc7796  ldarg.3
0xc7797  brfalse.s loc_C77C6
0xc7799  ldarg.3
0xc779a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::HasCustomizableForms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0xc779f  brfalse.s loc_C77C3
0xc77a1  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadCustomization()
0xc77a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc77ab  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc77b0  brfalse.s loc_C77C3
0xc77b2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadSystemForm()
0xc77b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc77bc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc77c1  br.s     loc_C77C7
0xc77c3  ldc.i4.0
0xc77c4  br.s     loc_C77C7
0xc77c6  ldc.i4.1
0xc77c7  brfalse  loc_C78DD
0xc77cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc77d1  ldstr    aSystemcustomiz_29// "SystemCustomization.ManageEntityPage.UI"...
0xc77d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc77db  stloc.0
0xc77dc  ldarg.1
0xc77dd  ldstr    aNode// "node"
0xc77e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc77e7  ldarg.1
0xc77e8  ldstr    aIcon_0// "icon"
0xc77ed  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc77f2  ldc.i4.1
0xc77f3  newarr   [mscorlib]System.Char
0xc77f8  dup
0xc77f9  ldc.i4.0
0xc77fa  ldc.i4.s 0x2F
0xc77fc  stelem.i2
0xc77fd  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc7802  ldstr    aImgsIco16Forms// "/_imgs/ico_16_forms.png"
0xc7807  call     string [mscorlib]System.String::Concat(string, string)
0xc780c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc7811  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc7816  callvirt instance string [mscorlib]System.Object::ToString()
0xc781b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7820  ldarg.1
0xc7821  ldstr    aAction// "action"
0xc7826  ldarg.0
0xc7827  ldstr    aForms// "Forms"
0xc782c  ldarg.2
0xc782d  ldnull
0xc782e  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSubNodeAction(string nodeType, string entityId, string relationshipRole)
0xc7833  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7838  ldarg.1
0xc7839  ldstr    aDisplayname// "displayname"
0xc783e  ldloc.0
0xc783f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7844  ldarg.1
0xc7845  ldstr    aId_1// "id"
0xc784a  ldarg.0
0xc784b  ldc.i4   0x2649
0xc7850  ldarg.2
0xc7851  ldstr    aForm// "form"
0xc7856  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc785b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7860  ldarg.1
0xc7861  ldstr    aLevel_0// "level"
0xc7866  ldarga.s 4
0xc7868  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc786d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc7872  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7877  ldarg.1
0xc7878  ldstr    aTabset_0// "tabset"
0xc787d  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc7882  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7887  ldarg.3
0xc7888  brfalse.s loc_C78BA
0xc788a  ldarg.1
0xc788b  ldstr    aParenttypecode// "parenttypecode"
0xc7890  ldarg.3
0xc7891  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xc7896  stloc.2
0xc7897  ldloca.s 2
0xc7899  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc789e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc78a3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc78a8  ldarg.1
0xc78a9  ldstr    aParentdisplayn_0// "parentdisplayname"
0xc78ae  ldarg.0
0xc78af  ldarg.3
0xc78b0  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata meta)
0xc78b5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc78ba  ldarg.1
0xc78bb  ldstr    aType// "type"
0xc78c0  ldc.i4   0x406
0xc78c5  stloc.2
0xc78c6  ldloca.s 2
0xc78c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc78cd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc78d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc78d7  ldarg.1
0xc78d8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc78dd  ldarg.3
0xc78de  brfalse.s loc_C78FC
0xc78e0  ldarg.3
0xc78e1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::HasCustomizableViews(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0xc78e6  brfalse.s loc_C78F9
0xc78e8  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadQuery()
0xc78ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc78f2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc78f7  br.s     loc_C78FD
0xc78f9  ldc.i4.0
0xc78fa  br.s     loc_C78FD
0xc78fc  ldc.i4.1
0xc78fd  brfalse  loc_C7A13
0xc7902  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc7907  ldstr    aSystemcustomiz_30// "SystemCustomization.ManageEntityPage.UI"...
0xc790c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc7911  stloc.0
0xc7912  ldarg.1
0xc7913  ldstr    aNode// "node"
0xc7918  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc791d  ldarg.1
0xc791e  ldstr    aIcon_0// "icon"
0xc7923  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc7928  ldc.i4.1
0xc7929  newarr   [mscorlib]System.Char
0xc792e  dup
0xc792f  ldc.i4.0
0xc7930  ldc.i4.s 0x2F
0xc7932  stelem.i2
0xc7933  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc7938  ldstr    aImgsIco16Views// "/_imgs/ico_16_views.png"
0xc793d  call     string [mscorlib]System.String::Concat(string, string)
0xc7942  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc7947  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc794c  callvirt instance string [mscorlib]System.Object::ToString()
0xc7951  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7956  ldarg.1
0xc7957  ldstr    aAction// "action"
0xc795c  ldarg.0
0xc795d  ldstr    aViews// "Views"
0xc7962  ldarg.2
0xc7963  ldnull
0xc7964  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSubNodeAction(string nodeType, string entityId, string relationshipRole)
0xc7969  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc796e  ldarg.1
0xc796f  ldstr    aDisplayname// "displayname"
0xc7974  ldloc.0
0xc7975  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc797a  ldarg.1
0xc797b  ldstr    aId_1// "id"
0xc7980  ldarg.0
0xc7981  ldc.i4   0x2649
0xc7986  ldarg.2
0xc7987  ldstr    aView// "view"
0xc798c  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc7991  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7996  ldarg.1
0xc7997  ldstr    aLevel_0// "level"
0xc799c  ldarga.s 4
0xc799e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc79a3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc79a8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc79ad  ldarg.1
0xc79ae  ldstr    aTabset_0// "tabset"
0xc79b3  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc79b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc79bd  ldarg.3
0xc79be  brfalse.s loc_C79F0
0xc79c0  ldarg.1
0xc79c1  ldstr    aParenttypecode// "parenttypecode"
0xc79c6  ldarg.3
0xc79c7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xc79cc  stloc.2
0xc79cd  ldloca.s 2
0xc79cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc79d4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc79d9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc79de  ldarg.1
0xc79df  ldstr    aParentdisplayn_0// "parentdisplayname"
0xc79e4  ldarg.0
0xc79e5  ldarg.3
0xc79e6  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata meta)
0xc79eb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc79f0  ldarg.1
0xc79f1  ldstr    aType// "type"
0xc79f6  ldc.i4   0x406
0xc79fb  stloc.2
0xc79fc  ldloca.s 2
0xc79fe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc7a03  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc7a08  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7a0d  ldarg.1
0xc7a0e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc7a13  ldarg.3
0xc7a14  brfalse.s loc_C7A1E
0xc7a16  ldarg.3
0xc7a17  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsEnabledForCharts()
0xc7a1c  brfalse.s loc_C7A2F
0xc7a1e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadSavedQueryVisualizations()
0xc7a23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc7a28  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc7a2d  br.s     loc_C7A30
0xc7a2f  ldc.i4.0
0xc7a30  brfalse  loc_C7B44
0xc7a35  ldarg.1
0xc7a36  ldstr    aNode// "node"
0xc7a3b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc7a40  ldarg.1
0xc7a41  ldstr    aIcon_0// "icon"
0xc7a46  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc7a4b  ldc.i4.1
0xc7a4c  newarr   [mscorlib]System.Char
0xc7a51  dup
0xc7a52  ldc.i4.0
0xc7a53  ldc.i4.s 0x2F
0xc7a55  stelem.i2
0xc7a56  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc7a5b  ldstr    aImgsIco16Visua// "/_imgs/ico_16_visualizations.gif"
0xc7a60  call     string [mscorlib]System.String::Concat(string, string)
0xc7a65  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc7a6a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc7a6f  callvirt instance string [mscorlib]System.Object::ToString()
0xc7a74  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7a79  ldarg.1
0xc7a7a  ldstr    aAction// "action"
0xc7a7f  ldarg.0
0xc7a80  ldstr    aChart// "Chart"
0xc7a85  ldarg.2
0xc7a86  ldnull
0xc7a87  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSubNodeAction(string nodeType, string entityId, string relationshipRole)
0xc7a8c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7a91  ldarg.1
0xc7a92  ldstr    aDisplayname// "displayname"
0xc7a97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc7a9c  ldstr    aSystemcustomiz_31// "SystemCustomization.ManageEntityPage.Vi"...
0xc7aa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc7aa6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7aab  ldarg.1
0xc7aac  ldstr    aId_1// "id"
0xc7ab1  ldarg.0
0xc7ab2  ldc.i4   0x2649
0xc7ab7  ldarg.2
0xc7ab8  ldstr    aChart_0// "chart"
0xc7abd  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc7ac2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7ac7  ldarg.1
0xc7ac8  ldstr    aLevel_0// "level"
0xc7acd  ldarga.s 4
0xc7acf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc7ad4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc7ad9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7ade  ldarg.1
0xc7adf  ldstr    aTabset_0// "tabset"
0xc7ae4  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc7ae9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7aee  ldarg.3
0xc7aef  brfalse.s loc_C7B21
0xc7af1  ldarg.1
0xc7af2  ldstr    aParenttypecode// "parenttypecode"
0xc7af7  ldarg.3
0xc7af8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xc7afd  stloc.2
0xc7afe  ldloca.s 2
0xc7b00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc7b05  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc7b0a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7b0f  ldarg.1
0xc7b10  ldstr    aParentdisplayn_0// "parentdisplayname"
0xc7b15  ldarg.0
0xc7b16  ldarg.3
0xc7b17  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetDisplayName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata meta)
0xc7b1c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7b21  ldarg.1
0xc7b22  ldstr    aType// "type"
0xc7b27  ldc.i4   0x457
0xc7b2c  stloc.2
0xc7b2d  ldloca.s 2
0xc7b2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc7b34  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc7b39  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc7b3e  ldarg.1
0xc7b3f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc7b44  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadAttribute()
0xc7b49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc7b4e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc7b53  brfalse  loc_C7C67
0xc7b58  ldarg.1
0xc7b59  ldstr    aNode// "node"
0xc7b5e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc7b63  ldarg.1
0xc7b64  ldstr    aIcon_0// "icon"
0xc7b69  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc7b6e  ldc.i4.1
0xc7b6f  newarr   [mscorlib]System.Char
0xc7b74  dup
0xc7b75  ldc.i4.0
0xc7b76  ldc.i4.s 0x2F
0xc7b78  stelem.i2
0xc7b79  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc7b7e  ldstr    aImgsIco18Attri// "/_imgs/ico_18_attributes.gif"
0xc7b83  call     string [mscorlib]System.String::Concat(string, string)
  ... truncated ...
```
