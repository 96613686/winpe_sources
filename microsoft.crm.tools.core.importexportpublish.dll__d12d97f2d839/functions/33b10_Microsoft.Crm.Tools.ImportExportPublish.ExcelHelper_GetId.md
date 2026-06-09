# Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetId

- ea: `0x33b10`
- end: `0x33c86`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetId`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x33530`

## callees

- `0x33b10`
- `0x33c90`
- `0x33cb0`

## string_xrefs

- `0x33bdd`: `FieldSecurityProfile`
- `0x33b95`: `PluginAssembly`
- `0x33bb9`: `ServiceEndpoint`
- `0x33b83`: `template`
- `0x33b3a`: `securityrole`

## pseudocode

```c

```

## disassembly

```asm
0x33b10  ldarg.1
0x33b11  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b16  ldstr    aLanguage// "language"
0x33b1b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b20  brfalse.s loc_33B28
0x33b22  ldsfld   string [mscorlib]System.String::Empty
0x33b27  ret
0x33b28  ldsfld   string [mscorlib]System.String::Empty
0x33b2d  stloc.0
0x33b2e  ldsfld   string [mscorlib]System.String::Empty
0x33b33  stloc.1
0x33b34  ldarg.1
0x33b35  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b3a  ldstr    aSecurityrole_0// "securityrole"
0x33b3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b44  brfalse.s loc_33B51
0x33b46  ldstr    aRoleid// "roleid"
0x33b4b  stloc.1
0x33b4c  br       loc_33BEF
0x33b51  ldarg.1
0x33b52  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b57  ldstr    aWorkflow_1// "workflow"
0x33b5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b61  brtrue.s loc_33B75
0x33b63  ldarg.1
0x33b64  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b69  ldstr    aPublishworkflo// "publishworkflow"
0x33b6e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b73  brfalse.s loc_33B7D
0x33b75  ldstr    aWorkflowid_0// "workflowid"
0x33b7a  stloc.1
0x33b7b  br.s     loc_33BEF
0x33b7d  ldarg.1
0x33b7e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b83  ldstr    aTemplate_0// "template"
0x33b88  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b8d  brtrue.s loc_33BE9
0x33b8f  ldarg.1
0x33b90  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33b95  ldstr    aPluginassembly_0// "PluginAssembly"
0x33b9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33b9f  brtrue.s loc_33BE9
0x33ba1  ldarg.1
0x33ba2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33ba7  ldstr    aSdkmessageproc// "SdkMessageProcessingStep"
0x33bac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33bb1  brtrue.s loc_33BE9
0x33bb3  ldarg.1
0x33bb4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33bb9  ldstr    aServiceendpoin// "ServiceEndpoint"
0x33bbe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33bc3  brtrue.s loc_33BE9
0x33bc5  ldarg.1
0x33bc6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33bcb  ldstr    aConnectionrole// "ConnectionRole"
0x33bd0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33bd5  brtrue.s loc_33BE9
0x33bd7  ldarg.1
0x33bd8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33bdd  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x33be2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33be7  brfalse.s loc_33BEF
0x33be9  ldstr    aId// "id"
0x33bee  stloc.1
0x33bef  ldloc.1
0x33bf0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33bf5  brtrue.s loc_33C0E
0x33bf7  ldarg.1
0x33bf8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33bfd  ldloc.1
0x33bfe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x33c03  stloc.2
0x33c04  ldloc.2
0x33c05  brfalse.s loc_33C0E
0x33c07  ldloc.2
0x33c08  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33c0d  stloc.0
0x33c0e  ldarg.0
0x33c0f  ldarg.1
0x33c10  ldarg.2
0x33c11  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetErrorCode(class [System.Xml]System.Xml.XmlNode parentNode, int32 resultIndex)
0x33c16  ldarg.0
0x33c17  ldc.i4   0x8004847C
0x33c1c  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetErrorCodeInHexString(int32 errorCode)
0x33c21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33c26  brfalse.s loc_33C84
0x33c28  ldarg.1
0x33c29  ldstr    aResult// "result"
0x33c2e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x33c33  stloc.3
0x33c34  ldloc.3
0x33c35  brfalse.s loc_33C78
0x33c37  ldloc.3
0x33c38  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x33c3d  ldarg.2
0x33c3e  ble.s    loc_33C78
0x33c40  ldloc.3
0x33c41  ldarg.2
0x33c42  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33c47  ldstr    aParametersPara// "parameters/parameter"
0x33c4c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x33c51  stloc.s  4
0x33c53  ldloc.s  4
0x33c55  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x33c5a  brfalse.s loc_33C6A
0x33c5c  ldloc.s  4
0x33c5e  ldc.i4.0
0x33c5f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x33c64  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33c69  stloc.0
0x33c6a  leave.s  loc_33C84
0x33c6c  ldloc.s  4
0x33c6e  brfalse.s loc_33C77
0x33c70  ldloc.s  4
0x33c72  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33c77  endfinally
0x33c78  leave.s  loc_33C84
0x33c7a  ldloc.3
0x33c7b  brfalse.s loc_33C83
0x33c7d  ldloc.3
0x33c7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33c83  endfinally
0x33c84  ldloc.0
0x33c85  ret
```
