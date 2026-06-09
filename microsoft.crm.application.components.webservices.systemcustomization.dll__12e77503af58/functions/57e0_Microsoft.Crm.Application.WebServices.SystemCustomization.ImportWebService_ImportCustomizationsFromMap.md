# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ImportCustomizationsFromMap

- ea: `0x57e0`
- end: `0x5972`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ImportCustomizationsFromMap`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x57e0`
- `0x5a60`
- `0x5d20`
- `0x5e50`
- `0x6900`

## pseudocode

```c

```

## disassembly

```asm
0x57e0  ldarg.1
0x57e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x57e6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_MapXml()
0x57f0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x57f5  stloc.0
0x57f6  ldloc.0
0x57f7  ldstr    aCustomizations// "//Customizations"
0x57fc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5801  stloc.1
0x5802  ldloc.0
0x5803  ldstr    aCustomizations_0// "//Customizations/Entities/Entity"
0x5808  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x580d  stloc.2
0x580e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5813  stloc.3
0x5814  ldarg.0
0x5815  ldloc.2
0x5816  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateNewEntitiesAndPublish(class [System.Xml]System.Xml.XmlNodeList entitiyNodeList)
0x581b  ldloc.2
0x581c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5821  stloc.s  5
0x5823  br.s     loc_5892
0x5825  ldloc.s  5
0x5827  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x582c  castclass [System.Xml]System.Xml.XmlNode
0x5831  stloc.s  6
0x5833  ldarg.0
0x5834  ldloc.s  6
0x5836  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessEntityCustomizationsForAttributes(class [System.Xml]System.Xml.XmlNode entityNode)
0x583b  stloc.s  7
0x583d  ldloc.s  7
0x583f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5844  brtrue.s loc_5892
0x5846  ldloc.3
0x5847  ldloc.s  7
0x5849  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x584e  ldloc.s  6
0x5850  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5855  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x585a  brfalse.s loc_5883
0x585c  ldloc.s  6
0x585e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5863  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5868  ldc.i4.1
0x5869  bne.un.s loc_5892
0x586b  ldloc.s  6
0x586d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x5872  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5877  ldstr    aLogicalname// "LogicalName"
0x587c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5881  brfalse.s loc_5892
0x5883  ldloc.s  6
0x5885  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x588a  ldloc.s  6
0x588c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x5891  pop
0x5892  ldloc.s  5
0x5894  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5899  brtrue.s loc_5825
0x589b  leave.s  loc_58B2
0x589d  ldloc.s  5
0x589f  isinst   [mscorlib]System.IDisposable
0x58a4  stloc.s  8
0x58a6  ldloc.s  8
0x58a8  brfalse.s loc_58B1
0x58aa  ldloc.s  8
0x58ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58b1  endfinally
0x58b2  ldarg.0
0x58b3  ldloc.0
0x58b4  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateRequiredPicklistValues(class [System.Xml]System.Xml.XmlDocument mapDoc)
0x58b9  stloc.s  4
0x58bb  ldloc.3
0x58bc  ldloc.s  4
0x58be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x58c3  ldloc.3
0x58c4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x58c9  ldc.i4.0
0x58ca  ble.s    loc_58D4
0x58cc  ldarg.0
0x58cd  ldloc.3
0x58ce  ldloc.0
0x58cf  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishCustomizations(class [mscorlib]System.Collections.Generic.List`1<string> entitiesToPublish, class [System.Xml]System.Xml.XmlDocument mapDoc)
0x58d4  leave.s  loc_5919
0x58d6  stloc.s  9
0x58d8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x58dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x58e2  ldc.i4.s 0x18
0x58e4  ldstr    aErrorInCustomi// "Error in customization: {0}"
0x58e9  ldc.i4.1
0x58ea  newarr   [mscorlib]System.Object
0x58ef  dup
0x58f0  ldc.i4.0
0x58f1  ldloc.s  9
0x58f3  callvirt instance string [mscorlib]System.Object::ToString()
0x58f8  stelem.ref
0x58f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x58fe  ldloc.3
0x58ff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5904  ldc.i4.0
0x5905  ble.s    loc_590F
0x5907  ldarg.0
0x5908  ldloc.3
0x5909  ldloc.0
0x590a  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishCustomizations(class [mscorlib]System.Collections.Generic.List`1<string> entitiesToPublish, class [System.Xml]System.Xml.XmlDocument mapDoc)
0x590f  ldloc.0
0x5910  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5915  stloc.s  0xA
0x5917  leave.s  loc_596F
0x5919  leave.s  loc_5925
0x591b  ldloc.2
0x591c  brfalse.s loc_5924
0x591e  ldloc.2
0x591f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5924  endfinally
0x5925  ldloc.1
0x5926  brfalse.s loc_595A
0x5928  ldloc.1
0x5929  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x592e  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5933  ldc.i4.1
0x5934  bne.un.s loc_595A
0x5936  ldloc.1
0x5937  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x593c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5941  ldstr    aEntities// "Entities"
0x5946  call     bool [mscorlib]System.String::op_Equality(string, string)
0x594b  brfalse.s loc_595A
0x594d  ldloc.1
0x594e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x5953  ldloc.1
0x5954  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x5959  pop
0x595a  ldloc.0
0x595b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5960  stloc.s  0xA
0x5962  leave.s  loc_596F
0x5964  stloc.s  0xB
0x5966  ldarg.0
0x5967  ldloc.s  0xB
0x5969  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x596e  throw
0x596f  ldloc.s  0xA
0x5971  ret
```
