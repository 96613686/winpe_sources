# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractLiveTrustElements

- ea: `0x159a0`
- end: `0x15a0d`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractLiveTrustElements`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15720`
- `0x15890`

## callees

- `0x15a90`

## string_xrefs

- `0x159c7`: `//ms-xrm:LiveTrust/ms-xrm:SecurityMode`
- `0x159cc`: `LiveTrustSecurityMode`

## pseudocode

```c

```

## disassembly

```asm
0x159a0  ldarg.0
0x159a1  ldarg.1
0x159a2  ldarg.2
0x159a3  ldstr    aMsXrmLivetrust// "//ms-xrm:LiveTrust/ms-xrm:AppliesTo"
0x159a8  ldstr    aAppliesto// "AppliesTo"
0x159ad  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x159b2  ldarg.0
0x159b3  ldarg.1
0x159b4  ldarg.2
0x159b5  ldstr    aMsXrmLivetrust_0// "//ms-xrm:LiveTrust/ms-xrm:TrustVersion"
0x159ba  ldstr    aLivetrusttrust// "LiveTrustTrustVersion"
0x159bf  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x159c4  ldarg.0
0x159c5  ldarg.1
0x159c6  ldarg.2
0x159c7  ldstr    aMsXrmLivetrust_1// "//ms-xrm:LiveTrust/ms-xrm:SecurityMode"
0x159cc  ldstr    aLivetrustsecur// "LiveTrustSecurityMode"
0x159d1  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x159d6  ldarg.0
0x159d7  ldarg.1
0x159d8  ldarg.2
0x159d9  ldstr    aMsXrmLivetrust_2// "//ms-xrm:LiveTrust/ms-xrm:LivePolicy"
0x159de  ldstr    aLivetrustlivep// "LiveTrustLivePolicy"
0x159e3  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x159e8  ldarg.0
0x159e9  ldarg.1
0x159ea  ldarg.2
0x159eb  ldstr    aMsXrmLivetrust_3// "//ms-xrm:LiveTrust/ms-xrm:LiveIdApplies"...
0x159f0  ldstr    aLivetrustlivei// "LiveTrustLiveIdAppliesTo"
0x159f5  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x159fa  ldarg.0
0x159fb  ldarg.1
0x159fc  ldarg.2
0x159fd  ldstr    aMsXrmLivetrust_4// "//ms-xrm:LiveTrust/ms-xrm:LiveEndpoint"
0x15a02  ldstr    aLiveendpoint// "LiveEndpoint"
0x15a07  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a0c  ret
```
