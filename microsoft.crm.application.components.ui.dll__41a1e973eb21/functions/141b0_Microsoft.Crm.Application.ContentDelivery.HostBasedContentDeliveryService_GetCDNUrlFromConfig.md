# Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrlFromConfig

- ea: `0x141b0`
- end: `0x141f1`
- name: `Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrlFromConfig`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14200`

## callees

- `0x141a0`
- `0x143c0`

## string_xrefs

- `0x141b0`: `CDN.config`

## pseudocode

```c

```

## disassembly

```asm
0x141b0  ldstr    aCdnConfig// "CDN.config"
0x141b5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x141ba  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::get_EnvironmentType()
0x141bf  stloc.0
0x141c0  ldstr    aCdnEndpoint// "//cdn/endpoint/"
0x141c5  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetBuildType()
0x141ca  ldstr    asc_34356// "/"
0x141cf  ldloc.0
0x141d0  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x141d5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x141da  stloc.1
0x141db  ldstr    aHttps// "https://"
0x141e0  ldloc.1
0x141e1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x141e6  ldstr    asc_34356// "/"
0x141eb  call     string [mscorlib]System.String::Concat(string, string, string)
0x141f0  ret
```
