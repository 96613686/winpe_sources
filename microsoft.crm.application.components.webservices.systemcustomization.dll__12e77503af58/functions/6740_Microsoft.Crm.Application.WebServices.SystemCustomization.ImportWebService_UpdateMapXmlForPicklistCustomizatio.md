# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPicklistCustomizationFailure

- ea: `0x6740`
- end: `0x6878`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPicklistCustomizationFailure`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5a60`

## callees

- `0x6740`

## pseudocode

```c

```

## disassembly

```asm
0x6740  ldarg.s  4
0x6742  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6747  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x674c  stloc.0
0x674d  ldarg.1
0x674e  ldstr    aPicklistcustom// "PicklistCustomizationError"
0x6753  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6758  stloc.1
0x6759  ldarg.1
0x675a  ldstr    aErrorcode// "ErrorCode"
0x675f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6764  stloc.2
0x6765  ldloc.2
0x6766  ldloc.0
0x6767  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x676c  stloc.s  0xA
0x676e  ldloca.s 0xA
0x6770  ldstr    aX// "X"
0x6775  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x677a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x677f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6784  ldloc.1
0x6785  ldloc.2
0x6786  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x678b  pop
0x678c  ldarg.1
0x678d  ldstr    aErrormessage// "ErrorMessage"
0x6792  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6797  stloc.3
0x6798  ldloc.3
0x6799  ldloc.0
0x679a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x679f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x67a4  ldloc.1
0x67a5  ldloc.3
0x67a6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x67ab  pop
0x67ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x67b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x67b6  ldarg.2
0x67b7  ldc.i4.1
0x67b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x67bd  dup
0x67be  ldarg.3
0x67bf  ldc.i4.1
0x67c0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x67c5  stloc.s  4
0x67c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x67cc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x67d1  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x67d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x67db  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x67e0  stloc.s  5
0x67e2  ldloc.s  4
0x67e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x67e9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x67ee  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x67f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x67f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x67fd  stloc.s  6
0x67ff  ldarg.1
0x6800  ldstr    aEntitydisplayn// "EntityDisplayName"
0x6805  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x680a  stloc.s  7
0x680c  ldarg.1
0x680d  ldstr    aAttributedispl// "AttributeDisplayName"
0x6812  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6817  stloc.s  8
0x6819  ldloc.s  7
0x681b  ldloc.s  5
0x681d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6822  ldloc.1
0x6823  ldloc.s  7
0x6825  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x682a  pop
0x682b  ldloc.s  8
0x682d  ldloc.s  6
0x682f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6834  ldloc.1
0x6835  ldloc.s  8
0x6837  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x683c  pop
0x683d  ldarg.1
0x683e  ldstr    aMapCustomizati_0// "/Map/Customizations"
0x6843  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6848  stloc.s  9
0x684a  ldloc.s  9
0x684c  brtrue.s loc_686E
0x684e  ldarg.1
0x684f  ldstr    aCustomizations_1// "Customizations"
0x6854  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6859  stloc.s  9
0x685b  ldarg.1
0x685c  ldstr    aMap// "/Map"
0x6861  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6866  ldloc.s  9
0x6868  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x686d  pop
0x686e  ldloc.s  9
0x6870  ldloc.1
0x6871  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6876  pop
0x6877  ret
```
