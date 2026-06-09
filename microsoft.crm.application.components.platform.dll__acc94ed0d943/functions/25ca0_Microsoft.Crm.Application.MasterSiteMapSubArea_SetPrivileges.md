# Microsoft.Crm.Application.MasterSiteMapSubArea::SetPrivileges

- ea: `0x25ca0`
- end: `0x25dbc`
- name: `Microsoft.Crm.Application.MasterSiteMapSubArea::SetPrivileges`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x258d0`

## callees

- `0x11590`
- `0x21590`
- `0x227a0`
- `0x23ae0`
- `0x25120`
- `0x25ca0`
- `0x260b0`

## string_xrefs

- `0x25cf3`: `Privilege`
- `0x25d35`: `Privilege`
- `0x25d5e`: `Unknown Named Privilege '{0}' in sitemap`

## pseudocode

```c

```

## disassembly

```asm
0x25ca0  ldarg.1
0x25ca1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x25ca6  stloc.0
0x25ca7  br       loc_25D9A
0x25cac  ldloc.0
0x25cad  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x25cb2  castclass [System.Xml]System.Xml.XmlNode
0x25cb7  stloc.1
0x25cb8  ldloc.1
0x25cb9  ldstr    aEntity_0// "Entity"
0x25cbe  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25cc3  stloc.2
0x25cc4  ldnull
0x25cc5  stloc.3
0x25cc6  ldloc.2
0x25cc7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25ccc  brtrue.s loc_25CE5
0x25cce  ldarg.0
0x25ccf  call     instance class Microsoft.Crm.Application.SiteMapGroup Microsoft.Crm.Application.SiteMapSubArea::get_ParentGroup()
0x25cd4  callvirt instance class Microsoft.Crm.Application.SiteMapArea Microsoft.Crm.Application.SiteMapGroup::get_ParentArea()
0x25cd9  callvirt instance class Microsoft.Crm.Application.SiteMap Microsoft.Crm.Application.SiteMapArea::get_SiteMap()
0x25cde  ldloc.2
0x25cdf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.SiteMap::TryGetEntity(string entityName)
0x25ce4  stloc.3
0x25ce5  ldloc.3
0x25ce6  brfalse.s loc_25D34
0x25ce8  ldtoken  Microsoft.Crm.Application.Types.PrivilegeId
0x25ced  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25cf2  ldloc.1
0x25cf3  ldstr    aPrivilege// "Privilege"
0x25cf8  ldc.i4.1
0x25cf9  stloc.s  5
0x25cfb  ldloca.s 5
0x25cfd  constrained. Microsoft.Crm.Application.Types.PrivilegeId
0x25d03  callvirt instance string [mscorlib]System.Object::ToString()
0x25d08  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25d0d  ldc.i4.0
0x25d0e  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x25d13  unbox.any Microsoft.Crm.Application.Types.PrivilegeId
0x25d18  stloc.s  4
0x25d1a  ldloc.s  4
0x25d1c  ldsfld   valuetype Microsoft.Crm.Application.Types.PrivilegeId Microsoft.Crm.Application.MasterSiteMapSubArea::_validPrivileges
0x25d21  and
0x25d22  stloc.s  4
0x25d24  ldarg.0
0x25d25  ldfld    class Microsoft.Crm.Application.PrivilegeIdDictionary Microsoft.Crm.Application.MasterSiteMapSubArea::_privileges
0x25d2a  ldloc.3
0x25d2b  ldloc.s  4
0x25d2d  callvirt instance void Microsoft.Crm.Application.PrivilegeIdDictionary::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, valuetype Microsoft.Crm.Application.Types.PrivilegeId value)
0x25d32  br.s     loc_25D9A
0x25d34  ldloc.1
0x25d35  ldstr    aPrivilege// "Privilege"
0x25d3a  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25d3f  stloc.s  6
0x25d41  ldtoken  [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges
0x25d46  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25d4b  ldloc.s  6
0x25d4d  ldc.i4.s 0x18
0x25d4f  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x25d54  stloc.s  7
0x25d56  ldloc.s  7
0x25d58  ldnull
0x25d59  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x25d5e  ldstr    aUnknownNamedPr// "Unknown Named Privilege '{0}' in sitema"...
0x25d63  ldc.i4.1
0x25d64  newarr   [mscorlib]System.Object
0x25d69  dup
0x25d6a  ldc.i4.0
0x25d6b  ldloc.s  6
0x25d6d  stelem.ref
0x25d6e  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x25d73  ldloc.s  7
0x25d75  ldnull
0x25d76  ldnull
0x25d77  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x25d7c  castclass [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0x25d81  stloc.s  8
0x25d83  ldarg.0
0x25d84  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.MasterSiteMapSubArea::_nonEntityPrivileges
0x25d89  ldloc.s  8
0x25d8b  ldfld    string [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition::guid
0x25d90  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25d95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x25d9a  ldloc.0
0x25d9b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25da0  brtrue   loc_25CAC
0x25da5  leave.s  loc_25DBB
0x25da7  ldloc.0
0x25da8  isinst   [mscorlib]System.IDisposable
0x25dad  stloc.s  9
0x25daf  ldloc.s  9
0x25db1  brfalse.s loc_25DBA
0x25db3  ldloc.s  9
0x25db5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25dba  endfinally
0x25dbb  ret
```
