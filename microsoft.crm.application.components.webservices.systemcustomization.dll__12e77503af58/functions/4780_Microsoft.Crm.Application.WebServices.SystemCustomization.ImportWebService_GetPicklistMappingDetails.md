# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetPicklistMappingDetails

- ea: `0x4780`
- end: `0x4a7b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetPicklistMappingDetails`
- size: `763`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4780`

## pseudocode

```c

```

## disassembly

```asm
0x4780  ldstr    aImportfile// "importfile"
0x4785  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x478a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x478f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4794  stloc.0
0x4795  ldstr    aOutputOutput// "<Output></Output>"
0x479a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x479f  stloc.1
0x47a0  ldarg.2
0x47a1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x47a6  brtrue   loc_488A
0x47ab  ldarg.3
0x47ac  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x47b1  brtrue   loc_488A
0x47b6  ldnull
0x47b7  stloc.2
0x47b8  ldloc.0
0x47b9  ldarg.1
0x47ba  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x47bf  ldarg.2
0x47c0  ldc.i4.1
0x47c1  newarr   [mscorlib]System.String
0x47c6  dup
0x47c7  ldc.i4.0
0x47c8  ldarg.3
0x47c9  stelem.ref
0x47ca  ldarg.s  5
0x47cc  ldarg.s  4
0x47ce  ldarg.s  6
0x47d0  callvirt instance class [System]System.Collections.Generic.SortedSet`1<string>[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::GetUniqueColumnValues(valuetype [mscorlib]System.Guid, string, string[], string, string, string)
0x47d5  ldc.i4.0
0x47d6  ldelem.ref
0x47d7  stloc.2
0x47d8  leave.s  loc_4826
0x47da  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x47df  ldc.i4   0x80048492
0x47e4  bne.un.s loc_4824
0x47e6  ldloc.1
0x47e7  ldstr    aError// "Error"
0x47ec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x47f1  stloc.s  4
0x47f3  ldloc.1
0x47f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x47f9  ldloc.s  4
0x47fb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4800  pop
0x4801  ldloc.s  4
0x4803  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4808  ldstr    aErrorMessage0x// "Error_Message_0x80048492"
0x480d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4812  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x4817  ldloc.1
0x4818  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x481d  stloc.s  5
0x481f  leave    loc_4A78
0x4824  rethrow
0x4826  ldloc.1
0x4827  ldstr    aSourcevalues// "SourceValues"
0x482c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4831  stloc.3
0x4832  ldloc.1
0x4833  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4838  ldloc.3
0x4839  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x483e  pop
0x483f  ldloc.2
0x4840  callvirt instance valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<var<u1>> class [System]System.Collections.Generic.SortedSet`1<string>::GetEnumerator()
0x4845  stloc.s  6
0x4847  br.s     loc_4871
0x4849  ldloca.s 6
0x484b  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>::get_Current()
0x4850  stloc.s  7
0x4852  ldloc.1
0x4853  ldstr    aSourcevalue// "SourceValue"
0x4858  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x485d  stloc.s  8
0x485f  ldloc.s  8
0x4861  ldloc.s  7
0x4863  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x4868  ldloc.3
0x4869  ldloc.s  8
0x486b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4870  pop
0x4871  ldloca.s 6
0x4873  call     instance bool valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>::MoveNext()
0x4878  brtrue.s loc_4849
0x487a  leave.s  loc_488A
0x487c  ldloca.s 6
0x487e  constrained. valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>
0x4884  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4889  endfinally
0x488a  ldarg.s  5
0x488c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4891  brtrue   loc_4A63
0x4896  ldarg.s  4
0x4898  ldarg.s  5
0x489a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x489f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportHelper::GetPicklistOptions(string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x48a4  stloc.s  9
0x48a6  ldloc.1
0x48a7  ldstr    aPicklistvalues// "PickListValues"
0x48ac  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x48b1  stloc.s  0xA
0x48b3  ldloc.1
0x48b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48b9  ldloc.s  0xA
0x48bb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x48c0  pop
0x48c1  ldloc.s  9
0x48c3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Keys()
0x48c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, string>::GetEnumerator()
0x48cd  stloc.s  0xF
0x48cf  br.s     loc_4930
0x48d1  ldloca.s 0xF
0x48d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>::get_Current()
0x48d8  stloc.s  0x10
0x48da  ldloc.1
0x48db  ldstr    aPicklistvalue// "PickListValue"
0x48e0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x48e5  stloc.s  0x11
0x48e7  ldloc.s  0x11
0x48e9  ldloc.s  9
0x48eb  ldloc.s  0x10
0x48ed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x48f2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x48f7  ldloc.1
0x48f8  ldstr    aValue// "value"
0x48fd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x4902  stloc.s  0x12
0x4904  ldloc.s  0x12
0x4906  ldloca.s 0x10
0x4908  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x490d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4912  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x4917  ldloc.s  0x11
0x4919  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x491e  ldloc.s  0x12
0x4920  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x4925  pop
0x4926  ldloc.s  0xA
0x4928  ldloc.s  0x11
0x492a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x492f  pop
0x4930  ldloca.s 0xF
0x4932  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>::MoveNext()
0x4937  brtrue.s loc_48D1
0x4939  leave.s  loc_4949
0x493b  ldloca.s 0xF
0x493d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>
0x4943  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4948  endfinally
0x4949  ldloc.s  9
0x494b  ldloca.s 0xB
0x494d  ldloca.s 0xC
0x494f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportHelper::GetCaseInsensitivePicklistOptions(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>&, class [System.Core]System.Collections.Generic.HashSet`1<string>&)
0x4954  ldloc.1
0x4955  ldstr    aUniquepicklist// "UniquePickListValues"
0x495a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x495f  stloc.s  0xD
0x4961  ldloc.1
0x4962  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4967  ldloc.s  0xD
0x4969  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x496e  pop
0x496f  ldloc.s  0xB
0x4971  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Keys()
0x4976  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, int32>::GetEnumerator()
0x497b  stloc.s  0x13
0x497d  br.s     loc_49E2
0x497f  ldloca.s 0x13
0x4981  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, int32>::get_Current()
0x4986  stloc.s  0x14
0x4988  ldloc.1
0x4989  ldstr    aUniquepicklist_0// "UniquePickListValue"
0x498e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4993  stloc.s  0x15
0x4995  ldloc.s  0x15
0x4997  ldloc.s  0x14
0x4999  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x499e  ldloc.1
0x499f  ldstr    aValue// "value"
0x49a4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x49a9  stloc.s  0x16
0x49ab  ldloc.s  0x16
0x49ad  ldloc.s  0xB
0x49af  ldloc.s  0x14
0x49b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x49b6  stloc.s  0x17
0x49b8  ldloca.s 0x17
0x49ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49bf  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x49c4  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x49c9  ldloc.s  0x15
0x49cb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x49d0  ldloc.s  0x16
0x49d2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x49d7  pop
0x49d8  ldloc.s  0xD
0x49da  ldloc.s  0x15
0x49dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x49e1  pop
0x49e2  ldloca.s 0x13
0x49e4  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, int32>::MoveNext()
0x49e9  brtrue.s loc_497F
0x49eb  leave.s  loc_49FB
0x49ed  ldloca.s 0x13
0x49ef  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, int32>
0x49f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49fa  endfinally
0x49fb  ldloc.1
0x49fc  ldstr    aDuplicatepickl// "DuplicatePickListValues"
0x4a01  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4a06  stloc.s  0xE
0x4a08  ldloc.1
0x4a09  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4a0e  ldloc.s  0xE
0x4a10  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4a15  pop
0x4a16  ldloc.s  0xC
0x4a18  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<string>::GetEnumerator()
0x4a1d  stloc.s  0x18
0x4a1f  br.s     loc_4A4A
0x4a21  ldloca.s 0x18
0x4a23  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::get_Current()
0x4a28  stloc.s  0x19
0x4a2a  ldloc.1
0x4a2b  ldstr    aDuplicatepickl_0// "DuplicatePickListValue"
0x4a30  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4a35  stloc.s  0x1A
0x4a37  ldloc.s  0x1A
0x4a39  ldloc.s  0x19
0x4a3b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x4a40  ldloc.s  0xE
0x4a42  ldloc.s  0x1A
0x4a44  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4a49  pop
0x4a4a  ldloca.s 0x18
0x4a4c  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::MoveNext()
0x4a51  brtrue.s loc_4A21
0x4a53  leave.s  loc_4A63
0x4a55  ldloca.s 0x18
0x4a57  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>
0x4a5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a62  endfinally
0x4a63  ldloc.1
0x4a64  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4a69  stloc.s  5
0x4a6b  leave.s  loc_4A78
0x4a6d  stloc.s  0x1B
0x4a6f  ldarg.0
0x4a70  ldloc.s  0x1B
0x4a72  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4a77  throw
0x4a78  ldloc.s  5
0x4a7a  ret
```
