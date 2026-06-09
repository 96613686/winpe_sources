# Microsoft.Crm.Reporting.SRSReport::ProcessImplicitReportParameters

- ea: `0x29a0`
- end: `0x2a48`
- name: `Microsoft.Crm.Reporting.SRSReport::ProcessImplicitReportParameters`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2950`
- `0x2970`

## callees

- `0x29a0`
- `0x5070`
- `0x8750`

## pseudocode

```c

```

## disassembly

```asm
0x29a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x29a5  ldarg.2
0x29a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x29ab  ldarg.2
0x29ac  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x29b1  stloc.0
0x29b2  ldloc.0
0x29b3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_LocaleId()
0x29b8  ldloc.0
0x29b9  ldarg.2
0x29ba  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::GetCulture(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29bf  ldarg.2
0x29c0  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Reporting.SRSReportUtility::GetImplicitParameters(int32 userLocaleId, class [mscorlib]System.Globalization.CultureInfo userCultureInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x29c5  stloc.1
0x29c6  ldarg.0
0x29c7  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x29cc  ldstr    aReportparamete_0// "ReportParameter"
0x29d1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x29d6  stloc.2
0x29d7  ldloc.2
0x29d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x29dd  stloc.3
0x29de  br.s     loc_2A1F
0x29e0  ldloc.3
0x29e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x29e6  castclass [System.Xml]System.Xml.XmlNode
0x29eb  stloc.s  4
0x29ed  ldloc.s  4
0x29ef  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x29f4  ldstr    aName// "Name"
0x29f9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x29fe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2a03  stloc.s  5
0x2a05  ldloc.1
0x2a06  ldloc.s  5
0x2a08  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x2a0d  brfalse.s loc_2A1F
0x2a0f  ldarg.1
0x2a10  ldloc.s  4
0x2a12  ldloc.1
0x2a13  ldloc.s  5
0x2a15  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x2a1a  callvirt instance void ImplicitParameterProcessor::Invoke(class [System.Xml]System.Xml.XmlNode parameterNode, string value)
0x2a1f  ldloc.3
0x2a20  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a25  brtrue.s loc_29E0
0x2a27  leave.s  loc_2A47
0x2a29  ldloc.3
0x2a2a  isinst   [mscorlib]System.IDisposable
0x2a2f  stloc.s  6
0x2a31  ldloc.s  6
0x2a33  brfalse.s loc_2A3C
0x2a35  ldloc.s  6
0x2a37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3c  endfinally
0x2a3d  ldloc.2
0x2a3e  brfalse.s loc_2A46
0x2a40  ldloc.2
0x2a41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a46  endfinally
0x2a47  ret
```
