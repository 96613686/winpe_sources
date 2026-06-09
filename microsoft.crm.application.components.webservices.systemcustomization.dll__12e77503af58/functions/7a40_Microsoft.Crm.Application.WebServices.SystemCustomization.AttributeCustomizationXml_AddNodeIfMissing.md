# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing

- ea: `0x7a40`
- end: `0x7a49`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7780`

## callees

- `0x7a50`

## pseudocode

```c

```

## disassembly

```asm
0x7a40  ldarg.0
0x7a41  ldarg.1
0x7a42  ldnull
0x7a43  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7a48  ret
```
