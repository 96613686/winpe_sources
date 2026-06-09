# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::RenderNode

- ea: `0xc6a30`
- end: `0xc6c94`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::RenderNode`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xc6980`

## callees

- `0x46e30`
- `0xc6a30`
- `0xc7240`
- `0xc7320`

## string_xrefs

- `0xc6a4c`: `areaSolutionComponent`
- `0xc6ac5`: `areaSolutionComponent`
- `0xc6c72`: `areaSolutionComponent`
- `0xc6b1f`: `solutioncomponenttype`
- `0xc6b4f`: `Solution.SolutionComponents.Filter.ApplicationIntegrations`
- `0xc6b64`: `/_imgs/ClientExtension_16.png`
- `0xc6c51`: `componentTypeFilter=`

## pseudocode

```c

```

## disassembly

```asm
0xc6a30  ldarg.1
0xc6a31  ldstr    aNode// "node"
0xc6a36  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc6a3b  ldarg.s  5
0xc6a3d  brfalse.s loc_C6ABE
0xc6a3f  ldstr    a01_8// "{0}_{1}"
0xc6a44  stloc.0
0xc6a45  ldarg.1
0xc6a46  ldstr    aAction// "action"
0xc6a4b  ldarg.0
0xc6a4c  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6a51  ldarg.2
0xc6a52  ldc.i4.1
0xc6a53  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetGroupAction(string tabset, int32 solutionComponentType, [opt] bool isMetadataDrivenDialog)
0xc6a58  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6a5d  ldarg.1
0xc6a5e  ldstr    aId_1// "id"
0xc6a63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6a68  ldloc.0
0xc6a69  ldc.i4.2
0xc6a6a  newarr   [mscorlib]System.Object
0xc6a6f  dup
0xc6a70  ldc.i4.0
0xc6a71  ldarg.0
0xc6a72  ldarg.3
0xc6a73  ldnull
0xc6a74  ldnull
0xc6a75  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc6a7a  stelem.ref
0xc6a7b  dup
0xc6a7c  ldc.i4.1
0xc6a7d  ldc.i4.1
0xc6a7e  box      [mscorlib]System.Int32
0xc6a83  stelem.ref
0xc6a84  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc6a89  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6a8e  ldarg.1
0xc6a8f  ldstr    aCode// "code"
0xc6a94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6a99  ldloc.0
0xc6a9a  ldc.i4.2
0xc6a9b  newarr   [mscorlib]System.Object
0xc6aa0  dup
0xc6aa1  ldc.i4.0
0xc6aa2  ldarg.3
0xc6aa3  box      [mscorlib]System.Int32
0xc6aa8  stelem.ref
0xc6aa9  dup
0xc6aaa  ldc.i4.1
0xc6aab  ldc.i4.1
0xc6aac  box      [mscorlib]System.Int32
0xc6ab1  stelem.ref
0xc6ab2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc6ab7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6abc  br.s     loc_C6B01
0xc6abe  ldarg.1
0xc6abf  ldstr    aAction// "action"
0xc6ac4  ldarg.0
0xc6ac5  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6aca  ldarg.2
0xc6acb  ldc.i4.0
0xc6acc  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetGroupAction(string tabset, int32 solutionComponentType, [opt] bool isMetadataDrivenDialog)
0xc6ad1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6ad6  ldarg.1
0xc6ad7  ldstr    aId_1// "id"
0xc6adc  ldarg.0
0xc6add  ldarg.3
0xc6ade  ldnull
0xc6adf  ldnull
0xc6ae0  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc6ae5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6aea  ldarg.1
0xc6aeb  ldstr    aCode// "code"
0xc6af0  ldarga.s 3
0xc6af2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6af7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6afc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6b01  ldarg.1
0xc6b02  ldstr    aType// "type"
0xc6b07  ldc.i4   0x1BBF
0xc6b0c  stloc.1
0xc6b0d  ldloca.s 1
0xc6b0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6b14  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6b19  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6b1e  ldarg.1
0xc6b1f  ldstr    aSolutioncompon_2// "solutioncomponenttype"
0xc6b24  ldarga.s 2
0xc6b26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6b2b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6b30  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6b35  ldarg.2
0xc6b36  ldc.i4.s 0x32
0xc6b38  beq.s    loc_C6B44
0xc6b3a  ldarg.2
0xc6b3b  ldc.i4.s 0x3C
0xc6b3d  beq.s    loc_C6B82
0xc6b3f  br       loc_C6BFD
0xc6b44  ldarg.1
0xc6b45  ldstr    aDisplayname// "displayname"
0xc6b4a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc6b4f  ldstr    aSolutionSoluti_0// "Solution.SolutionComponents.Filter.Appl"...
0xc6b54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc6b59  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6b5e  ldarg.1
0xc6b5f  ldstr    aIcon_0// "icon"
0xc6b64  ldstr    aImgsClientexte// "/_imgs/ClientExtension_16.png"
0xc6b69  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6b6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6b73  callvirt instance string [mscorlib]System.Object::ToString()
0xc6b78  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6b7d  br       loc_C6C2B
0xc6b82  ldarg.s  5
0xc6b84  brfalse.s loc_C6BC5
0xc6b86  ldarg.1
0xc6b87  ldstr    aDisplayname// "displayname"
0xc6b8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc6b91  ldstr    aMetadataDriven_0// "Metadata_Driven_Dialog_Plural_Name"
0xc6b96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc6b9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6ba0  ldarg.1
0xc6ba1  ldstr    aIcon_0// "icon"
0xc6ba6  ldarg.3
0xc6ba7  ldc.i4.0
0xc6ba8  ldc.i4.1
0xc6ba9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6bae  ldc.i4.8
0xc6baf  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc6bb4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Nullable`1<int32>)
0xc6bb9  callvirt instance string [mscorlib]System.Object::ToString()
0xc6bbe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6bc3  br.s     loc_C6C2B
0xc6bc5  ldarg.1
0xc6bc6  ldstr    aDisplayname// "displayname"
0xc6bcb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc6bd0  ldstr    aDashboardsPlur// "Dashboards_Plural_Name"
0xc6bd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc6bda  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6bdf  ldarg.1
0xc6be0  ldstr    aIcon_0// "icon"
0xc6be5  ldarg.3
0xc6be6  ldc.i4.0
0xc6be7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6bec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6bf1  callvirt instance string [mscorlib]System.Object::ToString()
0xc6bf6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6bfb  br.s     loc_C6C2B
0xc6bfd  ldarg.1
0xc6bfe  ldstr    aDisplayname// "displayname"
0xc6c03  ldarg.3
0xc6c04  ldc.i4.2
0xc6c05  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xc6c0a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c0f  ldarg.1
0xc6c10  ldstr    aIcon_0// "icon"
0xc6c15  ldarg.3
0xc6c16  ldc.i4.0
0xc6c17  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6c1c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6c21  callvirt instance string [mscorlib]System.Object::ToString()
0xc6c26  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c2b  ldarg.1
0xc6c2c  ldstr    aName// "name"
0xc6c31  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter
0xc6c36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc6c3b  ldarg.2
0xc6c3c  box      [mscorlib]System.Int32
0xc6c41  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0xc6c46  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c4b  ldarg.1
0xc6c4c  ldstr    aParameter// "parameter"
0xc6c51  ldstr    aComponenttypef_0// "componentTypeFilter="
0xc6c56  ldarga.s 2
0xc6c58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6c5d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6c62  call     string [mscorlib]System.String::Concat(string, string)
0xc6c67  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c6c  ldarg.1
0xc6c6d  ldstr    aTabset_0// "tabset"
0xc6c72  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6c77  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c7c  ldarg.1
0xc6c7d  ldstr    aLevel_0// "level"
0xc6c82  ldarga.s 4
0xc6c84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6c89  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6c8e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6c93  ret
```
