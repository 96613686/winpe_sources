# Microsoft.Crm.Application.Forms.FormDescriptorCache::GetTileFormDescriptor_0

- ea: `0x31480`
- end: `0x31721`
- name: `Microsoft.Crm.Application.Forms.FormDescriptorCache::GetTileFormDescriptor_0`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x6be10`

## callees

- `0x16b80`
- `0x16b90`
- `0x1bcb0`
- `0x1be70`
- `0x31480`
- `0x317f0`
- `0x31f30`
- `0x339d0`
- `0x33a80`
- `0x5be20`

## string_xrefs

- `0x314ed`: `formxml`
- `0x315ba`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x31480  ldstr    aFormHasmarginF// "<form hasmargin=\"false\" shownavigatio"...
0x31485  stloc.0
0x31486  ldnull
0x31487  stloc.1
0x31488  ldsfld   string [mscorlib]System.String::Empty
0x3148d  stloc.2
0x3148e  ldc.i4.0
0x3148f  stloc.s  6
0x31491  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x31496  callvirt instance bool Microsoft.Crm.Application.Utility.ClientContext::get_IsMobileClientWebDialog()
0x3149b  brtrue.s loc_314B4
0x3149d  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x314a2  ldarg.1
0x314a3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x314a8  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x314ad  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x314b2  br.s     loc_314C9
0x314b4  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x314b9  ldarg.1
0x314ba  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x314bf  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserUICulture()
0x314c4  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x314c9  stloc.s  7
0x314cb  ldarg.0
0x314cc  ldloc.s  7
0x314ce  newobj   instance void Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::.ctor(valuetype [mscorlib]System.Guid formId, int32 baseLanguageId)
0x314d3  ldarg.1
0x314d4  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve(class Microsoft.Crm.Application.Forms.FormDescriptorCacheKey key, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x314d9  stloc.1
0x314da  ldloc.1
0x314db  ldstr    aFormid// "formid"
0x314e0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x314e5  unbox.any [mscorlib]System.Guid
0x314ea  starg.s  0
0x314ec  ldloc.1
0x314ed  ldstr    aFormxml// "formxml"
0x314f2  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x314f7  castclass [mscorlib]System.String
0x314fc  stloc.2
0x314fd  ldloc.1
0x314fe  ldstr    aObjecttypecode// "objecttypecode"
0x31503  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31508  brtrue.s loc_3150D
0x3150a  ldc.i4.0
0x3150b  br.s     loc_3151D
0x3150d  ldloc.1
0x3150e  ldstr    aObjecttypecode// "objecttypecode"
0x31513  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31518  unbox.any [mscorlib]System.Int32
0x3151d  stloc.3
0x3151e  ldloc.1
0x3151f  ldstr    aType// "type"
0x31524  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31529  unbox.any [mscorlib]System.Int32
0x3152e  call     valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::ConvertSdkFormTypeToAppFormType(int32 formType)
0x31533  stloc.s  4
0x31535  ldloc.1
0x31536  ldstr    aVersionnumber// "versionnumber"
0x3153b  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31540  unbox.any [mscorlib]System.Int64
0x31545  stloc.s  5
0x31547  ldloc.1
0x31548  ldstr    aFormpresentati// "formpresentation"
0x3154d  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31552  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode
0x31557  stloc.s  6
0x31559  ldnull
0x3155a  stloc.s  8
0x3155c  ldloc.2
0x3155d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31562  brtrue   loc_3171E
0x31567  ldloc.2
0x31568  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3156d  ldloc.0
0x3156e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x31573  stloc.s  9
0x31575  ldstr    aFormTabsTabCol// "form/tabs/tab/columns/column/sections/s"...
0x3157a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x3157f  stloc.s  0xA
0x31581  ldc.i4.0
0x31582  stloc.s  0xB
0x31584  ldloc.s  0xA
0x31586  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x3158b  ldc.i4.0
0x3158c  ble      loc_316FE
0x31591  ldloc.s  0xA
0x31593  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x31598  stloc.s  0xC
0x3159a  br       loc_316DB
0x3159f  ldloc.s  0xC
0x315a1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x315a6  castclass [System.Xml]System.Xml.XmlNode
0x315ab  stloc.s  0xD
0x315ad  ldloc.s  0xD
0x315af  ldstr    aControl// "control"
0x315b4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x315b9  dup
0x315ba  ldstr    aClassid// "classid"
0x315bf  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x315c4  stloc.s  0xE
0x315c6  ldstr    aDatafieldname// "datafieldname"
0x315cb  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x315d0  stloc.s  0xF
0x315d2  ldloc.s  0xE
0x315d4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x315d9  brtrue   loc_316DB
0x315de  ldloc.s  0xF
0x315e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x315e5  brtrue   loc_316DB
0x315ea  ldloc.s  0xB
0x315ec  ldc.i4.4
0x315ed  bge      loc_316DB
0x315f2  ldloc.s  0xE
0x315f4  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x315f9  ldstr    a6f3fb987393b4d// "{6F3FB987-393B-4D2D-859F-9D0F0349B6AD}"
0x315fe  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x31603  brtrue.s loc_3161B
0x31605  ldloc.s  0xE
0x31607  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x3160c  ldstr    aF94db24f263d44// "{F94DB24F-263D-44A7-B38E-A35E9854812B}"
0x31611  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x31616  brfalse  loc_316DB
0x3161b  ldloc.s  9
0x3161d  ldloc.s  0xD
0x3161f  ldc.i4.1
0x31620  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x31625  stloc.s  0x10
0x31627  ldloc.s  0xE
0x31629  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x3162e  ldstr    aE0dece4b6fc84a// "{E0DECE4B-6FC8-4A8F-A065-082708572369}"
0x31633  call     bool [mscorlib]System.String::op_Equality(string, string)
0x31638  brfalse.s loc_316AA
0x3163a  ldloc.s  9
0x3163c  ldc.i4.1
0x3163d  ldstr    aEnablehtmlbind// "EnableHtmlBinding"
0x31642  ldsfld   string [mscorlib]System.String::Empty
0x31647  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x3164c  stloc.s  0x11
0x3164e  ldloc.s  0x11
0x31650  ldstr    aFalse// "false"
0x31655  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x3165a  ldloc.s  0x10
0x3165c  ldstr    aControlParamet// "/control/parameters"
0x31661  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x31666  stloc.s  0x12
0x31668  ldloc.s  0x12
0x3166a  brtrue.s loc_316A0
0x3166c  ldloc.s  9
0x3166e  ldc.i4.1
0x3166f  ldstr    aParameters// "parameters"
0x31674  ldsfld   string [mscorlib]System.String::Empty
0x31679  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x3167e  stloc.s  0x12
0x31680  ldloc.s  0x12
0x31682  ldloc.s  0x11
0x31684  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x31689  pop
0x3168a  ldloc.s  0x10
0x3168c  ldstr    aControl_1// "/control"
0x31691  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x31696  ldloc.s  0x12
0x31698  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3169d  pop
0x3169e  br.s     loc_316AA
0x316a0  ldloc.s  0x12
0x316a2  ldloc.s  0x11
0x316a4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x316a9  pop
0x316aa  ldloc.s  9
0x316ac  ldstr    aFormTabsTabCol_0// "form/tabs/tab/columns/column/sections/s"...
0x316b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x316b6  ldloc.s  9
0x316b8  ldc.i4.1
0x316b9  ldstr    aRow// "row"
0x316be  ldsfld   string [mscorlib]System.String::Empty
0x316c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x316c8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x316cd  ldloc.s  0x10
0x316cf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x316d4  pop
0x316d5  ldloc.s  0xB
0x316d7  ldc.i4.1
0x316d8  add
0x316d9  stloc.s  0xB
0x316db  ldloc.s  0xC
0x316dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x316e2  brtrue   loc_3159F
0x316e7  leave.s  loc_3170C
0x316e9  ldloc.s  0xC
0x316eb  isinst   [mscorlib]System.IDisposable
0x316f0  stloc.s  0x13
0x316f2  ldloc.s  0x13
0x316f4  brfalse.s loc_316FD
0x316f6  ldloc.s  0x13
0x316f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x316fd  endfinally
0x316fe  leave.s  loc_3170C
0x31700  ldloc.s  0xA
0x31702  brfalse.s loc_3170B
0x31704  ldloc.s  0xA
0x31706  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3170b  endfinally
0x3170c  ldloc.3
0x3170d  ldloc.s  9
0x3170f  ldarg.0
0x31710  ldloc.s  4
0x31712  ldloc.s  5
0x31714  ldloc.s  6
0x31716  ldarg.1
0x31717  newobj   instance void Microsoft.Crm.Application.FormDescriptor::.ctor(int32 typeCode, class [System.Xml]System.Xml.XmlNode formXml, valuetype [mscorlib]System.Guid formId, valuetype Microsoft.Crm.Application.FormType formType, int64 versionNumber, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode formPresentation, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3171c  stloc.s  8
0x3171e  ldloc.s  8
0x31720  ret
```
