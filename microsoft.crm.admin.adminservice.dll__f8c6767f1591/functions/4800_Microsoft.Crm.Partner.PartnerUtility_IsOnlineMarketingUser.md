# Microsoft.Crm.Partner.PartnerUtility::IsOnlineMarketingUser

- ea: `0x4800`
- end: `0x48b0`
- name: `Microsoft.Crm.Partner.PartnerUtility::IsOnlineMarketingUser`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4800`

## string_xrefs

- `0x4836`: `DeploymentXml`
- `0x4856`: `DeploymentXml`
- `0x4888`: `/PartnerSolutionDeploymentConfig/CrmUser/AuthenticationInfo`

## pseudocode

```c

```

## disassembly

```asm
0x4800  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x4805  ldarg.0
0x4806  ldarg.1
0x4807  ldc.i4.1
0x4808  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetAuthInfo(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType)
0x480d  stloc.0
0x480e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x4813  stloc.1
0x4814  ldloc.1
0x4815  ldstr    aName// "Name"
0x481a  ldstr    aOnlineMarketin// "Online Marketing"
0x481f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4824  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4829  ldstr    aPartnersolutio_2// "PartnerSolution"
0x482e  ldc.i4.1
0x482f  newarr   [mscorlib]System.String
0x4834  dup
0x4835  ldc.i4.0
0x4836  ldstr    aDeploymentxml// "DeploymentXml"
0x483b  stelem.ref
0x483c  ldloc.1
0x483d  ldc.i4   0x11C
0x4842  ldstr    aIsonlinemarket// "IsOnlineMarketingUser"
0x4847  ldstr    aDA1SSrcCrmlive_7// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Partn"...
0x484c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x4851  stloc.2
0x4852  ldloc.2
0x4853  brfalse.s loc_48AE
0x4855  ldloc.2
0x4856  ldstr    aDeploymentxml// "DeploymentXml"
0x485b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4860  castclass [mscorlib]System.String
0x4865  stloc.3
0x4866  ldloc.3
0x4867  ldstr    asc_4C848// "<?"
0x486c  ldc.i4.5
0x486d  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4872  stloc.s  4
0x4874  ldloc.s  4
0x4876  ldc.i4.0
0x4877  ble.s    loc_4882
0x4879  ldloc.3
0x487a  ldloc.s  4
0x487c  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4881  stloc.3
0x4882  ldloc.3
0x4883  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4888  ldstr    aPartnersolutio_5// "/PartnerSolutionDeploymentConfig/CrmUse"...
0x488d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4892  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4897  ldc.i4.0
0x4898  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x489d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x48a2  ldloc.0
0x48a3  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x48a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x48ad  ret
0x48ae  ldc.i4.0
0x48af  ret
```
