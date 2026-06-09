# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractOrgTrustElements

- ea: `0x15a10`
- end: `0x15a8f`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractOrgTrustElements`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15890`

## callees

- `0x15a90`

## string_xrefs

- `0x15a37`: `//ms-xrm:OrgTrust/ms-xrm:SecurityMode`
- `0x15a3c`: `OrgIdSecurityMode`

## pseudocode

```c

```

## disassembly

```asm
0x15a10  ldarg.0
0x15a11  ldarg.1
0x15a12  ldarg.2
0x15a13  ldstr    aMsXrmOrgtrustM// "//ms-xrm:OrgTrust/ms-xrm:AppliesTo"
0x15a18  ldstr    aOrgidappliesto// "OrgIdAppliesTo"
0x15a1d  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a22  ldarg.0
0x15a23  ldarg.1
0x15a24  ldarg.2
0x15a25  ldstr    aMsXrmOrgtrustM_0// "//ms-xrm:OrgTrust/ms-xrm:TrustVersion"
0x15a2a  ldstr    aOrgidtrustvers// "OrgIdTrustVersion"
0x15a2f  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a34  ldarg.0
0x15a35  ldarg.1
0x15a36  ldarg.2
0x15a37  ldstr    aMsXrmOrgtrustM_1// "//ms-xrm:OrgTrust/ms-xrm:SecurityMode"
0x15a3c  ldstr    aOrgidsecuritym// "OrgIdSecurityMode"
0x15a41  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a46  ldarg.0
0x15a47  ldarg.1
0x15a48  ldarg.2
0x15a49  ldstr    aMsXrmOrgtrustM_2// "//ms-xrm:OrgTrust/ms-xrm:LivePolicy"
0x15a4e  ldstr    aOrgidpolicy// "OrgIdPolicy"
0x15a53  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a58  ldarg.0
0x15a59  ldarg.1
0x15a5a  ldarg.2
0x15a5b  ldstr    aMsXrmOrgtrustM_3// "//ms-xrm:OrgTrust/ms-xrm:LiveIdAppliesT"...
0x15a60  ldstr    aOrgiddeviceapp// "OrgIdDeviceAppliesTo"
0x15a65  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a6a  ldarg.0
0x15a6b  ldarg.1
0x15a6c  ldarg.2
0x15a6d  ldstr    aMsXrmOrgtrustM_4// "//ms-xrm:OrgTrust/ms-xrm:LiveEndpoint"
0x15a72  ldstr    aOrgidendpoint// "OrgIdEndpoint"
0x15a77  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a7c  ldarg.0
0x15a7d  ldarg.1
0x15a7e  ldarg.2
0x15a7f  ldstr    aMsXrmOrgtrustM_5// "//ms-xrm:OrgTrust/ms-xrm:Identifier"
0x15a84  ldstr    aOrgididentifie// "OrgIdIdentifier"
0x15a89  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15a8e  ret
```
