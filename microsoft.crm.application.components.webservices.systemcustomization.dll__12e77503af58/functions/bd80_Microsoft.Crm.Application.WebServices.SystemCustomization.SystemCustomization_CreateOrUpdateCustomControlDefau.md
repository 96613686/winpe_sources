# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateOrUpdateCustomControlDefaultConfig

- ea: `0xbd80`
- end: `0xbee1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateOrUpdateCustomControlDefaultConfig`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xbd80`

## string_xrefs

- `0xbd8c`: `xmlns`
- `0xbdfe`: `customcontroldefaultconfig`
- `0xbe12`: `controldescriptionxml`
- `0xbe7b`: `controldescriptionxml`
- `0xbea2`: `controldescriptionxml`
- `0xbeaf`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0xbd80  ldarg.1
0xbd81  brtrue.s loc_BD84
0xbd83  ret
0xbd84  ldarg.1
0xbd85  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xbd8a  stloc.0
0xbd8b  ldloc.0
0xbd8c  ldstr    aXmlns// "xmlns"
0xbd91  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0xbd96  stloc.1
0xbd97  ldloc.1
0xbd98  ldc.i4.m1
0xbd99  beq.s    loc_BDBF
0xbd9b  ldloc.0
0xbd9c  ldc.i4.0
0xbd9d  ldloc.1
0xbd9e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xbda3  stloc.s  8
0xbda5  ldloc.0
0xbda6  ldloc.1
0xbda7  ldc.i4.5
0xbda8  add
0xbda9  callvirt instance string [mscorlib]System.String::Substring(int32)
0xbdae  stloc.s  9
0xbdb0  ldloc.s  8
0xbdb2  ldstr    aNoneAttribute// "none-attribute"
0xbdb7  ldloc.s  9
0xbdb9  call     string [mscorlib]System.String::Concat(string, string, string)
0xbdbe  stloc.0
0xbdbf  ldloc.0
0xbdc0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xbdc5  dup
0xbdc6  ldstr    aWrapper// "//wrapper"
0xbdcb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbdd0  stloc.2
0xbdd1  ldstr    aPrimaryetc// "//primaryetc"
0xbdd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbddb  stloc.3
0xbddc  ldloc.2
0xbddd  brfalse.s loc_BDE2
0xbddf  ldloc.3
0xbde0  brtrue.s loc_BDE3
0xbde2  ret
0xbde3  ldloc.3
0xbde4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xbde9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbdee  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xbdf3  stloc.s  4
0xbdf5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0xbdfa  stloc.s  5
0xbdfc  ldloc.s  5
0xbdfe  ldstr    aCustomcontrold_2// "customcontroldefaultconfig"
0xbe03  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0xbe08  ldloc.s  5
0xbe0a  ldc.i4.1
0xbe0b  newarr   [mscorlib]System.String
0xbe10  dup
0xbe11  ldc.i4.0
0xbe12  ldstr    aControldescrip// "controldescriptionxml"
0xbe17  stelem.ref
0xbe18  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xbe1d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0xbe22  ldloc.s  5
0xbe24  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xbe29  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xbe2e  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xbe33  ldc.i4.0
0xbe34  ldloc.s  4
0xbe36  box      [mscorlib]System.Int32
0xbe3b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xbe40  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbe45  pop
0xbe46  ldloc.s  5
0xbe48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbe4d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbe52  stloc.s  6
0xbe54  ldloc.2
0xbe55  ldloc.3
0xbe56  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xbe5b  pop
0xbe5c  ldloc.2
0xbe5d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xbe62  stloc.s  7
0xbe64  ldloc.s  6
0xbe66  brfalse.s loc_BE92
0xbe68  ldloc.s  6
0xbe6a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xbe6f  ldc.i4.0
0xbe70  ble.s    loc_BE92
0xbe72  ldloc.s  6
0xbe74  ldc.i4.0
0xbe75  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xbe7a  dup
0xbe7b  ldstr    aControldescrip// "controldescriptionxml"
0xbe80  ldloc.s  7
0xbe82  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xbe87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbe8c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbe91  ret
0xbe92  ldc.i4   0x261B
0xbe97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbe9c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbea1  dup
0xbea2  ldstr    aControldescrip// "controldescriptionxml"
0xbea7  ldloc.s  7
0xbea9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xbeae  dup
0xbeaf  ldstr    aCustomcontrold_3// "customcontroldefaultconfigid"
0xbeb4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xbeb9  box      [mscorlib]System.Guid
0xbebe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xbec3  dup
0xbec4  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xbec9  ldloc.s  4
0xbecb  box      [mscorlib]System.Int32
0xbed0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xbed5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbeda  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbedf  pop
0xbee0  ret
```
