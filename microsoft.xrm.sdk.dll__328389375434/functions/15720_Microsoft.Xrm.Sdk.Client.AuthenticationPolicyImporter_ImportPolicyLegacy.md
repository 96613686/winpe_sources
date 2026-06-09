# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportPolicyLegacy

- ea: `0x15720`
- end: `0x157ea`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportPolicyLegacy`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15890`

## callees

- `0x15720`
- `0x157f0`
- `0x159a0`
- `0x15a90`
- `0x15c60`
- `0x15ce0`

## string_xrefs

- `0x15733`: `http://schemas.microsoft.com/xrm/2011/Contracts/Services`
- `0x157ac`: `http://schemas.microsoft.com/xrm/2011/Contracts/Services`
- `0x157ce`: `//ms-xrm:SecureTokenService/ms-xrm:Identifier`
- `0x157d3`: `SecureTokenServiceIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x15720  ldarg.0
0x15721  ldarg.1
0x15722  call     instance bool Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportFailoverPolicy(class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext context)
0x15727  pop
0x15728  ldarg.1
0x15729  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x1572e  ldstr    aAuthentication// "AuthenticationPolicy"
0x15733  ldstr    aHttpSchemasMic_15// "http://schemas.microsoft.com/xrm/2011/C"...
0x15738  callvirt instance class [System.Xml]System.Xml.XmlElement [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection::Find(string, string)
0x1573d  stloc.0
0x1573e  ldloc.0
0x1573f  brfalse  loc_157E8
0x15744  ldc.i4.1
0x15745  stloc.1
0x15746  ldarg.1
0x15747  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x1574c  callvirt T0x2B00005C
0x15751  stloc.2
0x15752  ldloc.2
0x15753  brtrue.s loc_1576A
0x15755  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationPolicy::.ctor()
0x1575a  stloc.2
0x1575b  ldarg.1
0x1575c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x15761  ldc.i4.0
0x15762  ldloc.2
0x15763  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Insert(int32, var<u1>)
0x15768  br.s     loc_1577E
0x1576a  ldloc.2
0x1576b  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x15770  ldstr    aOrgidappliesto// "OrgIdAppliesTo"
0x15775  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1577a  brfalse.s loc_1577E
0x1577c  ldc.i4.0
0x1577d  stloc.1
0x1577e  ldarg.1
0x1577f  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x15784  ldloc.0
0x15785  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Remove(var<u1>)
0x1578a  pop
0x1578b  ldloc.1
0x1578c  brfalse.s loc_157E6
0x1578e  ldloc.0
0x1578f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x15794  stloc.3
0x15795  ldloc.3
0x15796  brfalse.s loc_157E6
0x15798  ldloc.3
0x15799  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0x1579e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x157a3  stloc.s  4
0x157a5  ldloc.s  4
0x157a7  ldstr    aMsXrm// "ms-xrm"
0x157ac  ldstr    aHttpSchemasMic_15// "http://schemas.microsoft.com/xrm/2011/C"...
0x157b1  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x157b6  ldloc.2
0x157b7  ldloc.3
0x157b8  ldloc.s  4
0x157ba  ldarg.0
0x157bb  ldfld    string Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::MsXrmAuthentication
0x157c0  ldstr    aAuthentication_0// "AuthenticationType"
0x157c5  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x157ca  ldloc.2
0x157cb  ldloc.3
0x157cc  ldloc.s  4
0x157ce  ldstr    aMsXrmSecuretok// "//ms-xrm:SecureTokenService/ms-xrm:Iden"...
0x157d3  ldstr    aSecuretokenser// "SecureTokenServiceIdentifier"
0x157d8  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x157dd  ldloc.2
0x157de  ldloc.3
0x157df  ldloc.s  4
0x157e1  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractLiveTrustElements(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicyBindingElement, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr)
0x157e6  ldc.i4.1
0x157e7  ret
0x157e8  ldc.i4.0
0x157e9  ret
```
