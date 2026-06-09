# Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigFromXmlSettings

- ea: `0x5f70`
- end: `0x608b`
- name: `Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigFromXmlSettings`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5f20`
- `0x5f40`

## callees

- `0x5e00`
- `0x5e20`
- `0x5e40`
- `0x5e60`
- `0x5e80`
- `0x5f70`

## string_xrefs

- `0x5f9c`: `webhooksconfig`

## pseudocode

```c

```

## disassembly

```asm
0x5f70  ldarg.1
0x5f71  brtrue.s loc_5F76
0x5f73  ldarg.1
0x5f74  br.s     loc_5F7C
0x5f76  ldarg.1
0x5f77  callvirt instance string [mscorlib]System.String::Trim()
0x5f7c  starg.s  1
0x5f7e  ldarg.1
0x5f7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5f84  brtrue   loc_608A
0x5f89  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x5f8e  dup
0x5f8f  ldnull
0x5f90  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x5f95  dup
0x5f96  ldarg.1
0x5f97  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x5f9c  ldstr    aWebhooksconfig// "webhooksconfig"
0x5fa1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x5fa6  stloc.0
0x5fa7  ldloc.0
0x5fa8  brfalse  loc_608A
0x5fad  ldloc.0
0x5fae  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5fb3  ldc.i4.0
0x5fb4  ble      loc_608A
0x5fb9  ldloc.0
0x5fba  ldc.i4.0
0x5fbb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x5fc0  dup
0x5fc1  ldstr    aConnectionlimi// "connectionlimit"
0x5fc6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5fcb  stloc.1
0x5fcc  ldloc.1
0x5fcd  brfalse.s loc_5FE5
0x5fcf  ldarg.0
0x5fd0  ldloc.1
0x5fd1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5fd6  callvirt instance string [mscorlib]System.String::Trim()
0x5fdb  call     int32 [mscorlib]System.Int32::Parse(string)
0x5fe0  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_ConnectionLimit(int32 value)
0x5fe5  dup
0x5fe6  ldstr    aLeasetimeoutin// "leasetimeoutinsecs"
0x5feb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5ff0  stloc.1
0x5ff1  ldloc.1
0x5ff2  brfalse.s loc_6010
0x5ff4  ldarg.0
0x5ff5  ldloc.1
0x5ff6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ffb  callvirt instance string [mscorlib]System.String::Trim()
0x6000  call     int32 [mscorlib]System.Int32::Parse(string)
0x6005  ldc.i4   0x3E8
0x600a  mul
0x600b  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_ConnectionLeaseTimeoutInMilliSeconds(int32 value)
0x6010  dup
0x6011  ldstr    aMaxidletimeins// "maxidletimeinsecs"
0x6016  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x601b  stloc.1
0x601c  ldloc.1
0x601d  brfalse.s loc_603B
0x601f  ldarg.0
0x6020  ldloc.1
0x6021  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6026  callvirt instance string [mscorlib]System.String::Trim()
0x602b  call     int32 [mscorlib]System.Int32::Parse(string)
0x6030  ldc.i4   0x3E8
0x6035  mul
0x6036  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_MaxIdleTimeInMilliSeconds(int32 value)
0x603b  dup
0x603c  ldstr    aHttptimeoutins// "httptimeoutinsecs"
0x6041  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6046  stloc.1
0x6047  ldloc.1
0x6048  brfalse.s loc_6066
0x604a  ldarg.0
0x604b  ldloc.1
0x604c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6051  callvirt instance string [mscorlib]System.String::Trim()
0x6056  call     int32 [mscorlib]System.Int32::Parse(string)
0x605b  ldc.i4   0x3E8
0x6060  mul
0x6061  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_HttpRequestTimeoutInMilliSeconds(int32 value)
0x6066  ldstr    aRetrycount// "retrycount"
0x606b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6070  stloc.1
0x6071  ldloc.1
0x6072  brfalse.s loc_608A
0x6074  ldarg.0
0x6075  ldloc.1
0x6076  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x607b  callvirt instance string [mscorlib]System.String::Trim()
0x6080  call     int32 [mscorlib]System.Int32::Parse(string)
0x6085  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_RetryCountForTransientHttpErrors(int32 value)
0x608a  ret
```
