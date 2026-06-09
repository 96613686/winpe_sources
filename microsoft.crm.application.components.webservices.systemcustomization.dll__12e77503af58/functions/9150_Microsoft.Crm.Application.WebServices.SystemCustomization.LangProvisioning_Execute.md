# Microsoft.Crm.Application.WebServices.SystemCustomization.LangProvisioning::Execute

- ea: `0x9150`
- end: `0x9242`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LangProvisioning::Execute`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb3c0`

## callees

- `0x9150`

## string_xrefs

- `0x9184`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x9150  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9155  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckLanguageSettingsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x915a  brtrue.s loc_916D
0x915c  ldc.i4   0x80040277
0x9161  ldc.i4.0
0x9162  newarr   [mscorlib]System.Object
0x9167  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x916c  throw
0x916d  ldarg.0
0x916e  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x9173  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9178  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x917d  stloc.0
0x917e  ldloc.0
0x917f  ldstr    aMbs// "mbs"
0x9184  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2009/W"...
0x9189  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x918e  ldarg.0
0x918f  ldstr    aMbsLanguagesMb// "/mbs:languages//mbs:language"
0x9194  ldloc.0
0x9195  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x919a  stloc.1
0x919b  ldloc.1
0x919c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x91a1  stloc.2
0x91a2  br.s     loc_9219
0x91a4  ldloc.2
0x91a5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x91aa  castclass [System.Xml]System.Xml.XmlNode
0x91af  dup
0x91b0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x91b5  ldstr    aLanguageid// "languageid"
0x91ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x91bf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x91c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91c9  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x91ce  stloc.3
0x91cf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x91d4  ldstr    aAction// "action"
0x91d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x91de  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x91e3  stloc.s  4
0x91e5  ldloc.s  4
0x91e7  ldstr    aEnable// "enable"
0x91ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91f1  brfalse.s loc_9200
0x91f3  ldloc.3
0x91f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x91f9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::ProvisionLanguage(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x91fe  br.s     loc_9219
0x9200  ldloc.s  4
0x9202  ldstr    aDisable// "disable"
0x9207  call     bool [mscorlib]System.String::op_Equality(string, string)
0x920c  brfalse.s loc_9219
0x920e  ldloc.3
0x920f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9214  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::DeprovisionLanguage(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9219  ldloc.2
0x921a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x921f  brtrue.s loc_91A4
0x9221  leave.s  loc_9241
0x9223  ldloc.2
0x9224  isinst   [mscorlib]System.IDisposable
0x9229  stloc.s  5
0x922b  ldloc.s  5
0x922d  brfalse.s loc_9236
0x922f  ldloc.s  5
0x9231  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9236  endfinally
0x9237  ldloc.1
0x9238  brfalse.s loc_9240
0x923a  ldloc.1
0x923b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9240  endfinally
0x9241  ret
```
