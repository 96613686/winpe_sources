# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::FetchStatusTransitionEntityFieldList

- ea: `0xb7f0`
- end: `0xb92d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::FetchStatusTransitionEntityFieldList`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb7f0`

## pseudocode

```c

```

## disassembly

```asm
0xb7f0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0xb7f5  stloc.0
0xb7f6  ldloc.0
0xb7f7  ldstr    aSelect// "select"
0xb7fc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xb801  stloc.1
0xb802  ldloc.0
0xb803  ldstr    aDisablesorting// "disablesorting"
0xb808  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xb80d  stloc.2
0xb80e  ldloc.2
0xb80f  ldstr    aFalse// "false"
0xb814  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xb819  ldloc.1
0xb81a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb81f  ldloc.2
0xb820  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0xb825  pop
0xb826  ldloc.0
0xb827  ldloc.1
0xb828  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xb82d  pop
0xb82e  ldnull
0xb82f  stloc.3
0xb830  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb835  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb83a  ldarg.2
0xb83b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb840  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSet(valuetype [mscorlib]System.Guid)
0xb845  stloc.s  4
0xb847  ldloc.s  4
0xb849  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Options()
0xb84e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Keys()
0xb853  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0xb858  stloc.s  5
0xb85a  br       loc_B8FB
0xb85f  ldloc.s  5
0xb861  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0xb866  stloc.s  6
0xb868  ldloc.s  4
0xb86a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Options()
0xb86f  ldloc.s  6
0xb871  ldloca.s 3
0xb873  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::TryGetValue(var<u1>, !!T0)
0xb878  pop
0xb879  ldloc.3
0xb87a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0xb87f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xb884  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0xb889  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb88e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb893  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xb898  stloc.s  7
0xb89a  ldloc.s  7
0xb89c  ldarg.1
0xb89d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb8a2  brfalse.s loc_B8FB
0xb8a4  ldloc.0
0xb8a5  ldstr    aOption// "option"
0xb8aa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xb8af  stloc.s  8
0xb8b1  ldloc.s  8
0xb8b3  ldloc.s  7
0xb8b5  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xb8ba  ldloc.0
0xb8bb  ldstr    aValue// "value"
0xb8c0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xb8c5  stloc.s  9
0xb8c7  ldloc.s  9
0xb8c9  ldloc.3
0xb8ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_OptionId()
0xb8cf  stloc.s  0xA
0xb8d1  ldloca.s 0xA
0xb8d3  constrained. [mscorlib]System.Guid
0xb8d9  callvirt instance string [mscorlib]System.Object::ToString()
0xb8de  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xb8e3  ldloc.s  8
0xb8e5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb8ea  ldloc.s  9
0xb8ec  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0xb8f1  pop
0xb8f2  ldloc.1
0xb8f3  ldloc.s  8
0xb8f5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xb8fa  pop
0xb8fb  ldloc.s  5
0xb8fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb902  brtrue   loc_B85F
0xb907  leave.s  loc_B915
0xb909  ldloc.s  5
0xb90b  brfalse.s loc_B914
0xb90d  ldloc.s  5
0xb90f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb914  endfinally
0xb915  ldloc.0
0xb916  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xb91b  stloc.s  0xB
0xb91d  leave.s  loc_B92A
0xb91f  stloc.s  0xC
0xb921  ldarg.0
0xb922  ldloc.s  0xC
0xb924  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb929  throw
0xb92a  ldloc.s  0xB
0xb92c  ret
```
