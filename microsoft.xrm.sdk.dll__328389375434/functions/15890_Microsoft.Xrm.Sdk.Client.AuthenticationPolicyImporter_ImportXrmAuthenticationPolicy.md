# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportXrmAuthenticationPolicy

- ea: `0x15890`
- end: `0x1599a`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportXrmAuthenticationPolicy`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15710`

## callees

- `0x15720`
- `0x157f0`
- `0x15890`
- `0x159a0`
- `0x15a10`
- `0x15a90`
- `0x15c60`
- `0x15ce0`

## string_xrefs

- `0x15976`: `//ms-xrm:SecureTokenService/ms-xrm:Identifier`
- `0x1597b`: `SecureTokenServiceIdentifier`
- `0x158ab`: `http://schemas.microsoft.com/xrm/2012/Contracts/Services`
- `0x15952`: `http://schemas.microsoft.com/xrm/2012/Contracts/Services`

## pseudocode

```c

```

## disassembly

```asm
0x15890  ldarg.0
0x15891  ldarg.1
0x15892  call     instance bool Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportPolicyLegacy(class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext context)
0x15897  stloc.0
0x15898  ldarg.0
0x15899  ldarg.1
0x1589a  call     instance bool Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportFailoverPolicy(class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext context)
0x1589f  pop
0x158a0  ldarg.1
0x158a1  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x158a6  ldstr    aAuthentication// "AuthenticationPolicy"
0x158ab  ldstr    aHttpSchemasMic_16// "http://schemas.microsoft.com/xrm/2012/C"...
0x158b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection::Find(string, string)
0x158b5  stloc.1
0x158b6  ldloc.1
0x158b7  brfalse  loc_15999
0x158bc  ldarg.1
0x158bd  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x158c2  callvirt T0x2B00005C
0x158c7  stloc.2
0x158c8  ldnull
0x158c9  stloc.3
0x158ca  ldloc.2
0x158cb  ldnull
0x158cc  ceq
0x158ce  ldloc.0
0x158cf  or
0x158d0  brfalse.s loc_15924
0x158d2  ldloc.0
0x158d3  brfalse.s loc_158E2
0x158d5  ldarg.1
0x158d6  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x158db  ldloc.2
0x158dc  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Remove(var<u1>)
0x158e1  pop
0x158e2  ldloc.2
0x158e3  brfalse.s loc_158F8
0x158e5  ldloc.2
0x158e6  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x158eb  ldstr    aAppliesto// "AppliesTo"
0x158f0  ldloca.s 3
0x158f2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x158f7  pop
0x158f8  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationPolicy::.ctor()
0x158fd  stloc.2
0x158fe  ldloc.3
0x158ff  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x15904  brtrue.s loc_15917
0x15906  ldloc.2
0x15907  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x1590c  ldstr    aLivepartneride// "LivePartnerIdentifier"
0x15911  ldloc.3
0x15912  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x15917  ldarg.1
0x15918  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x1591d  ldc.i4.0
0x1591e  ldloc.2
0x1591f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Insert(int32, var<u1>)
0x15924  ldarg.1
0x15925  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.PolicyAssertionCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::GetBindingAssertions()
0x1592a  ldloc.1
0x1592b  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Remove(var<u1>)
0x15930  pop
0x15931  ldloc.1
0x15932  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x15937  stloc.s  4
0x15939  ldloc.s  4
0x1593b  brfalse.s loc_15999
0x1593d  ldloc.s  4
0x1593f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0x15944  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x15949  stloc.s  5
0x1594b  ldloc.s  5
0x1594d  ldstr    aMsXrm// "ms-xrm"
0x15952  ldstr    aHttpSchemasMic_16// "http://schemas.microsoft.com/xrm/2012/C"...
0x15957  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1595c  ldloc.2
0x1595d  ldloc.s  4
0x1595f  ldloc.s  5
0x15961  ldarg.0
0x15962  ldfld    string Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::MsXrmAuthentication
0x15967  ldstr    aAuthentication_0// "AuthenticationType"
0x1596c  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15971  ldloc.2
0x15972  ldloc.s  4
0x15974  ldloc.s  5
0x15976  ldstr    aMsXrmSecuretok// "//ms-xrm:SecureTokenService/ms-xrm:Iden"...
0x1597b  ldstr    aSecuretokenser// "SecureTokenServiceIdentifier"
0x15980  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractValue(class Microsoft.Xrm.Sdk.Client.XrmPolicy xrmPolicy, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr, string query, string name)
0x15985  ldloc.2
0x15986  ldloc.s  4
0x15988  ldloc.s  5
0x1598a  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractLiveTrustElements(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicyBindingElement, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr)
0x1598f  ldloc.2
0x15990  ldloc.s  4
0x15992  ldloc.s  5
0x15994  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ExtractOrgTrustElements(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicyBindingElement, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr)
0x15999  ret
```
