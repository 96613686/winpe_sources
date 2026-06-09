# Microsoft.Crm.Sdk.RequestBase::ReadXml

- ea: `0x4790`
- end: `0x490a`
- name: `Microsoft.Crm.Sdk.RequestBase::ReadXml`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40b0`

## callees

- `0x4370`
- `0x43f0`
- `0x4490`
- `0x4500`
- `0x4790`
- `0x4a20`
- `0x4a80`
- `0x4ab0`
- `0x4b80`
- `0x61e0`
- `0x6270`

## string_xrefs

- `0x47b6`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x4790  ldarg.1
0x4791  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x4796  stloc.0
0x4797  ldarg.0
0x4798  ldloc.0
0x4799  ldarg.1
0x479a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x479f  newobj   instance void Microsoft.Crm.Sdk.ParsingContext::.ctor(class Microsoft.Crm.Sdk.RequestBase request, string namespaceName, class [System.Xml]System.Xml.XmlReader reader, valuetype [mscorlib]System.Guid organizationId)
0x47a4  stloc.1
0x47a5  ldloc.1
0x47a6  ldstr    aRequest// "Request"
0x47ab  callvirt instance void Microsoft.Crm.Sdk.ParsingContext::EnsureStartElement(string localName)
0x47b0  ldloc.1
0x47b1  ldstr    aType// "type"
0x47b6  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x47bb  callvirt instance string Microsoft.Crm.Sdk.ParsingContext::GetRequiredAttributeValue(string localName, string ns)
0x47c0  stloc.2
0x47c1  ldarg.0
0x47c2  ldloc.2
0x47c3  ldloc.0
0x47c4  ldloc.1
0x47c5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.ParsingContext::get_OrganizationId()
0x47ca  call     class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBuilderFactory::Create(string requestName, string targetNamespace, valuetype [mscorlib]System.Guid organizationId)
0x47cf  stfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x47d4  ldarg.0
0x47d5  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x47da  callvirt instance bool Microsoft.Crm.Sdk.IRequestBuilder::get_SupportsDynamicEntities()
0x47df  brfalse.s loc_4801
0x47e1  ldarg.0
0x47e2  ldloc.1
0x47e3  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x47e8  ldsfld   string [mscorlib]System.String::Empty
0x47ed  callvirt instance string Microsoft.Crm.Sdk.ParsingContext::GetRequiredAttributeValue(string localName, string ns)
0x47f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47f7  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x47fc  stfld    bool Microsoft.Crm.Sdk.RequestBase::_returnDynamicEntities
0x4801  ldarg.1
0x4802  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x4807  pop
0x4808  ldarg.0
0x4809  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x480e  brtrue.s loc_4826
0x4810  ldstr    aUnknownRequest// "Unknown request type: "
0x4815  ldloc.2
0x4816  call     string [mscorlib]System.String::Concat(string, string)
0x481b  ldstr    aRequestType// "Request/@type"
0x4820  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x4825  throw
0x4826  ldarg.0
0x4827  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::.ctor()
0x482c  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::_inputParameters
0x4831  ldarg.0
0x4832  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::_inputParameters
0x4837  ldstr    aOptionalparame// "OptionalParameters"
0x483c  ldarg.0
0x483d  ldloc.1
0x483e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] Microsoft.Crm.Sdk.RequestBase::ReadOptionalParameters(class Microsoft.Crm.Sdk.ParsingContext context)
0x4843  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x4848  ldarg.0
0x4849  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x484e  callvirt instance bool Microsoft.Crm.Sdk.IRequestBuilder::get_SupportsDynamicEntities()
0x4853  brfalse.s loc_4870
0x4855  ldarg.0
0x4856  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::_inputParameters
0x485b  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x4860  ldarg.0
0x4861  ldfld    bool Microsoft.Crm.Sdk.RequestBase::_returnDynamicEntities
0x4866  box      [mscorlib]System.Boolean
0x486b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x4870  newobj   instance void Microsoft.Crm.Sdk.RequestParser::.ctor()
0x4875  ldloc.1
0x4876  ldarg.0
0x4877  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x487c  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.RequestParser::Parse(class Microsoft.Crm.Sdk.ParsingContext context, class Microsoft.Crm.Sdk.IRequestBuilder requestBuilder)
0x4881  stloc.3
0x4882  ldloc.3
0x4883  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x4888  stloc.s  4
0x488a  br.s     loc_48BE
0x488c  ldloc.s  4
0x488e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4893  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x4898  stloc.s  5
0x489a  ldarg.0
0x489b  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::_inputParameters
0x48a0  ldloca.s 5
0x48a2  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x48a7  castclass [mscorlib]System.String
0x48ac  ldloc.3
0x48ad  ldloca.s 5
0x48af  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x48b4  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x48b9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x48be  ldloc.s  4
0x48c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x48c5  brtrue.s loc_488C
0x48c7  leave.s  loc_48DE
0x48c9  ldloc.s  4
0x48cb  isinst   [mscorlib]System.IDisposable
0x48d0  stloc.s  6
0x48d2  ldloc.s  6
0x48d4  brfalse.s loc_48DD
0x48d6  ldloc.s  6
0x48d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48dd  endfinally
0x48de  ldarg.1
0x48df  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x48e4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x48e9  ldc.i4.s 0x1A
0x48eb  ldstr    aParsedRequest0// "Parsed request: {0}"
0x48f0  ldc.i4.1
0x48f1  newarr   [mscorlib]System.Object
0x48f6  dup
0x48f7  ldc.i4.0
0x48f8  ldarg.0
0x48f9  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::_requestBuilder
0x48fe  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0x4903  stelem.ref
0x4904  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4909  ret
```
