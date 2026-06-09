# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetData

- ea: `0xae30`
- end: `0xae65`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomizationHandler::GetData`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xacb0`

## string_xrefs

- `0xae30`: `<root xmlns="http://schemas.microsoft.com/crm/2009/WebServices">`

## pseudocode

```c

```

## disassembly

```asm
0xae30  ldstr    aRootXmlnsHttpS// "<root xmlns=\"http://schemas.microsoft."...
0xae35  ldarg.1
0xae36  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0xae3b  ldstr    aData// "data"
0xae40  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xae45  ldstr    aRoot// "</root>"
0xae4a  call     string [mscorlib]System.String::Concat(string, string, string)
0xae4f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xae54  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xae59  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xae5e  ldc.i4.0
0xae5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xae64  ret
```
