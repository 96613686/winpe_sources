# Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::FillPropertiesFromXml_0

- ea: `0x40480`
- end: `0x405d4`
- name: `Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::FillPropertiesFromXml_0`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x40470`

## callees

- `0xbc50`
- `0x40480`
- `0x40600`
- `0x40620`
- `0x40640`
- `0x40660`
- `0x40680`
- `0x406a0`
- `0x406c0`

## string_xrefs

- `0x404fc`: `PrivilegeId`
- `0x4051a`: `PrivilegeId`
- `0x40527`: `PrivilegeId`
- `0x40482`: `RoleTemplatePrivilegeId`
- `0x4048f`: `RoleTemplatePrivilegeId`
- `0x404b0`: `RoleTemplateId`
- `0x404ce`: `RoleTemplateId`
- `0x404db`: `RoleTemplateId`
- `0x404c1`: `RoleTemplatePrivilege XML requires the RoleTemplateId`
- `0x4050d`: `RoleTemplatePrivilege XML requires the PrivilegeId`

## pseudocode

```c

```

## disassembly

```asm
0x40480  ldarg.0
0x40481  ldarg.1
0x40482  ldstr    aRoletemplatepr_1// "RoleTemplatePrivilegeId"
0x40487  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4048c  brfalse.s loc_404A5
0x4048e  ldarg.1
0x4048f  ldstr    aRoletemplatepr_1// "RoleTemplatePrivilegeId"
0x40494  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40499  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4049e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x404a3  br.s     loc_404AA
0x404a5  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x404aa  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_RoleTemplatePrivilegeId(valuetype [mscorlib]System.Guid value)
0x404af  ldarg.1
0x404b0  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x404b5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x404ba  ldnull
0x404bb  ceq
0x404bd  ldarg.2
0x404be  and
0x404bf  brfalse.s loc_404CC
0x404c1  ldstr    aRoletemplatepr_2// "RoleTemplatePrivilege XML requires the "...
0x404c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x404cb  throw
0x404cc  ldarg.0
0x404cd  ldarg.1
0x404ce  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x404d3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x404d8  brfalse.s loc_404F1
0x404da  ldarg.1
0x404db  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x404e0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x404e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x404ea  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x404ef  br.s     loc_404F6
0x404f1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x404f6  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_RoleTemplateId(valuetype [mscorlib]System.Guid value)
0x404fb  ldarg.1
0x404fc  ldstr    aPrivilegeid_0// "PrivilegeId"
0x40501  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40506  ldnull
0x40507  ceq
0x40509  ldarg.2
0x4050a  and
0x4050b  brfalse.s loc_40518
0x4050d  ldstr    aRoletemplatepr_3// "RoleTemplatePrivilege XML requires the "...
0x40512  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x40517  throw
0x40518  ldarg.0
0x40519  ldarg.1
0x4051a  ldstr    aPrivilegeid_0// "PrivilegeId"
0x4051f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40524  brfalse.s loc_4053D
0x40526  ldarg.1
0x40527  ldstr    aPrivilegeid_0// "PrivilegeId"
0x4052c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40531  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40536  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4053b  br.s     loc_40542
0x4053d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x40542  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x40547  ldarg.1
0x40548  ldstr    aIsbasic// "IsBasic"
0x4054d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40552  brfalse.s loc_4056A
0x40554  ldarg.0
0x40555  ldarg.1
0x40556  ldstr    aIsbasic// "IsBasic"
0x4055b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40560  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x40565  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsBasic(bool value)
0x4056a  ldarg.1
0x4056b  ldstr    aIslocal// "IsLocal"
0x40570  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40575  brfalse.s loc_4058D
0x40577  ldarg.0
0x40578  ldarg.1
0x40579  ldstr    aIslocal// "IsLocal"
0x4057e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40583  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x40588  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsLocal(bool value)
0x4058d  ldarg.1
0x4058e  ldstr    aIsdeep// "IsDeep"
0x40593  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40598  brfalse.s loc_405B0
0x4059a  ldarg.0
0x4059b  ldarg.1
0x4059c  ldstr    aIsdeep// "IsDeep"
0x405a1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x405a6  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x405ab  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsDeep(bool value)
0x405b0  ldarg.1
0x405b1  ldstr    aIsglobal// "IsGlobal"
0x405b6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x405bb  brfalse.s loc_405D3
0x405bd  ldarg.0
0x405be  ldarg.1
0x405bf  ldstr    aIsglobal// "IsGlobal"
0x405c4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x405c9  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x405ce  callvirt instance void Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescription::set_IsGlobal(bool value)
0x405d3  ret
```
