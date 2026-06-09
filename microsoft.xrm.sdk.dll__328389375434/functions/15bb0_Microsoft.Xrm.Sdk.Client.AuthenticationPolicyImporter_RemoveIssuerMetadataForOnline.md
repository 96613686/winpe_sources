# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::RemoveIssuerMetadataForOnline

- ea: `0x15bb0`
- end: `0x15c4d`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::RemoveIssuerMetadataForOnline`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15b20`

## callees

- `0x15bb0`

## string_xrefs

- `0x15bb6`: `SignedSupportingTokens`
- `0x15bbb`: `http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702`
- `0x15be6`: `http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702`
- `0x15bfa`: `http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702`
- `0x15bd2`: `http://schemas.xmlsoap.org/ws/2004/09/policy`
- `0x15be1`: `IssuedToken`

## pseudocode

```c

```

## disassembly

```asm
0x15bb0  ldarg.0
0x15bb1  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x15bb6  ldstr    aSignedsupporti// "SignedSupportingTokens"
0x15bbb  ldstr    aHttpDocsOasisO_0// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0x15bc0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection::Find(string, string)
0x15bc5  stloc.0
0x15bc6  ldloc.0
0x15bc7  brfalse  loc_15C4C
0x15bcc  ldloc.0
0x15bcd  ldstr    aPolicy// "Policy"
0x15bd2  ldstr    aHttpSchemasXml_1// "http://schemas.xmlsoap.org/ws/2004/09/p"...
0x15bd7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string, string)
0x15bdc  stloc.1
0x15bdd  ldloc.1
0x15bde  brfalse.s loc_15C4C
0x15be0  ldloc.1
0x15be1  ldstr    aIssuedtoken// "IssuedToken"
0x15be6  ldstr    aHttpDocsOasisO_0// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0x15beb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string, string)
0x15bf0  stloc.2
0x15bf1  ldloc.2
0x15bf2  brfalse.s loc_15C4C
0x15bf4  ldloc.2
0x15bf5  ldstr    aIssuer// "Issuer"
0x15bfa  ldstr    aHttpDocsOasisO_0// "http://docs.oasis-open.org/ws-sx/ws-sec"...
0x15bff  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string, string)
0x15c04  stloc.3
0x15c05  ldloc.3
0x15c06  brfalse.s loc_15C4C
0x15c08  ldloc.3
0x15c09  ldstr    aMetadata// "Metadata"
0x15c0e  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2005/08/addressing"
0x15c13  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string, string)
0x15c18  stloc.s  4
0x15c1a  ldloc.s  4
0x15c1c  brfalse.s loc_15C2A
0x15c1e  ldloc.s  4
0x15c20  ldsfld   string [mscorlib]System.String::Empty
0x15c25  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x15c2a  ldloc.3
0x15c2b  ldstr    aAddress// "Address"
0x15c30  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2005/08/addressing"
0x15c35  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string, string)
0x15c3a  stloc.s  5
0x15c3c  ldloc.s  5
0x15c3e  brfalse.s loc_15C4C
0x15c40  ldloc.s  5
0x15c42  ldstr    aUrnNone// "urn://none"
0x15c47  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x15c4c  ret
```
