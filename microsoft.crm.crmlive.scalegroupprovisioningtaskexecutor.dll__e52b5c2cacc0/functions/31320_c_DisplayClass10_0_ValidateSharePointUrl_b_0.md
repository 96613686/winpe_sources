# <>c__DisplayClass10_0::<ValidateSharePointUrl>b__0

- ea: `0x31320`
- end: `0x3137d`
- name: `<>c__DisplayClass10_0::<ValidateSharePointUrl>b__0`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x31320`

## string_xrefs

- `0x31348`: `/siteUrlsXml/siteUrl`
- `0x31367`: `/siteUrlsXml/errorlog`

## pseudocode

```c

```

## disassembly

```asm
0x31320  ldarg.0
0x31321  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SharePointDocumentService <>c__DisplayClass10_0::sharepointDocumentService
0x31326  ldarg.0
0x31327  ldfld    string <>c__DisplayClass10_0::validateUrlRequest
0x3132c  ldarg.1
0x3132d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SharePointDocumentService::ValidateUrl(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31332  stloc.0
0x31333  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x31338  stloc.1
0x31339  ldloc.1
0x3133a  ldnull
0x3133b  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x31340  ldloc.1
0x31341  ldloc.0
0x31342  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x31347  ldloc.1
0x31348  ldstr    aSiteurlsxmlSit_0// "/siteUrlsXml/siteUrl"
0x3134d  ldnull
0x3134e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x31353  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x31358  ldstr    aTrue// "true"
0x3135d  ldc.i4.3
0x3135e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x31363  brfalse.s loc_31366
0x31365  ret
0x31366  ldloc.1
0x31367  ldstr    aSiteurlsxmlErr// "/siteUrlsXml/errorlog"
0x3136c  ldnull
0x3136d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x31372  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x31377  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x3137c  throw
```
