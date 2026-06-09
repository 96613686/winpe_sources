# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::LoadFromDatabase

- ea: `0x1db0`
- end: `0x22de`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::LoadFromDatabase`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x19d0`

## callees

- `0x1a80`
- `0x1aa0`
- `0x1ac0`
- `0x1ae0`
- `0x1b00`
- `0x1b20`
- `0x1c00`
- `0x1c20`
- `0x1c40`
- `0x1c50`
- `0x1c60`
- `0x1c80`
- `0x1cb0`
- `0x1cc0`
- `0x1ce0`
- `0x1d00`
- `0x1d20`
- `0x1d40`
- `0x1d60`
- `0x1db0`

## string_xrefs

- `0x1dc1`: `orgService`
- `0x1db1`: `configurationId`
- `0x1dcc`: `ServiceEndpoint`
- `0x1de6`: `ServiceEndpoint`
- `0x1e41`: `sastoken`
- `0x211b`: `sastoken`
- `0x2186`: `sastoken`
- `0x1e6e`: `serviceendpointid`
- `0x2012`: `serviceendpointid`
- `0x2021`: `serviceendpointid`
- `0x20a6`: `serviceendpointid`
- `0x215e`: `serviceendpointid`
- `0x2215`: `serviceendpointid`
- `0x2074`: `A SASKey has not been configured for ServiceEndpoint {0} [{1}]`
- `0x212c`: `A SASToken has not been configured for ServiceEndpoint {0} [{1}]`
- `0x21e3`: `AuthValue or Url has not been configured for ServiceEndpoint {0} [{1}]`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.1
0x1db1  ldstr    aConfigurationi// "configurationId"
0x1db6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1dbb  ldarg.2
0x1dbc  box      [mscorlib]System.Guid
0x1dc1  ldstr    aOrgservice// "orgService"
0x1dc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1dcb  ldarg.1
0x1dcc  ldstr    aServiceendpoin_3// "ServiceEndpoint"
0x1dd1  ldarg.2
0x1dd2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1dd7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ddc  stloc.0
0x1ddd  ldarg.2
0x1dde  ldc.i4.0
0x1ddf  ldc.i4.0
0x1de0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1de5  stloc.1
0x1de6  ldstr    aServiceendpoin_3// "ServiceEndpoint"
0x1deb  ldloc.1
0x1dec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1df1  stloc.2
0x1df2  ldloc.2
0x1df3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1df8  ldc.i4.s 0x10
0x1dfa  newarr   [mscorlib]System.String
0x1dff  dup
0x1e00  ldc.i4.0
0x1e01  ldstr    aSolutionnamesp_0// "solutionnamespace"
0x1e06  stelem.ref
0x1e07  dup
0x1e08  ldc.i4.1
0x1e09  ldstr    aPath// "path"
0x1e0e  stelem.ref
0x1e0f  dup
0x1e10  ldc.i4.2
0x1e11  ldstr    aContract// "contract"
0x1e16  stelem.ref
0x1e17  dup
0x1e18  ldc.i4.3
0x1e19  ldstr    aNamespaceforma// "namespaceformat"
0x1e1e  stelem.ref
0x1e1f  dup
0x1e20  ldc.i4.4
0x1e21  ldstr    aNamespaceaddre// "namespaceaddress"
0x1e26  stelem.ref
0x1e27  dup
0x1e28  ldc.i4.5
0x1e29  ldstr    aAuthtype// "authtype"
0x1e2e  stelem.ref
0x1e2f  dup
0x1e30  ldc.i4.6
0x1e31  ldstr    aSaskey// "saskey"
0x1e36  stelem.ref
0x1e37  dup
0x1e38  ldc.i4.7
0x1e39  ldstr    aSaskeyname// "saskeyname"
0x1e3e  stelem.ref
0x1e3f  dup
0x1e40  ldc.i4.8
0x1e41  ldstr    aSastoken// "sastoken"
0x1e46  stelem.ref
0x1e47  dup
0x1e48  ldc.i4.s 9
0x1e4a  ldstr    aMessageformat// "messageformat"
0x1e4f  stelem.ref
0x1e50  dup
0x1e51  ldc.i4.s 0xA
0x1e53  ldstr    aUserclaim// "userclaim"
0x1e58  stelem.ref
0x1e59  dup
0x1e5a  ldc.i4.s 0xB
0x1e5c  ldstr    aConnectionmode// "connectionmode"
0x1e61  stelem.ref
0x1e62  dup
0x1e63  ldc.i4.s 0xC
0x1e65  ldstr    aName// "name"
0x1e6a  stelem.ref
0x1e6b  dup
0x1e6c  ldc.i4.s 0xD
0x1e6e  ldstr    aServiceendpoin_4// "serviceendpointid"
0x1e73  stelem.ref
0x1e74  dup
0x1e75  ldc.i4.s 0xE
0x1e77  ldstr    aAuthvalue// "authvalue"
0x1e7c  stelem.ref
0x1e7d  dup
0x1e7e  ldc.i4.s 0xF
0x1e80  ldstr    aUrl// "url"
0x1e85  stelem.ref
0x1e86  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1e8b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x1e90  stloc.3
0x1e91  ldloc.1
0x1e92  ldc.i4.1
0x1e93  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x1e98  ldloc.1
0x1e99  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1e9e  stloc.s  4
0x1ea0  ldloc.3
0x1ea1  ldloc.0
0x1ea2  ldloc.2
0x1ea3  ldloc.1
0x1ea4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ea9  stloc.s  5
0x1eab  ldarg.0
0x1eac  ldsfld   string [System]System.Uri::UriSchemeHttps
0x1eb1  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Scheme(string value)
0x1eb6  ldarg.0
0x1eb7  ldloc.s  5
0x1eb9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1ebe  ldstr    aSolutionnamesp_0// "solutionnamespace"
0x1ec3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1ec8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1ecd  callvirt instance string [mscorlib]System.Object::ToString()
0x1ed2  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_SolutionName(string value)
0x1ed7  ldarg.0
0x1ed8  ldloc.s  5
0x1eda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1edf  ldstr    aPath// "path"
0x1ee4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1ee9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1eee  callvirt instance string [mscorlib]System.Object::ToString()
0x1ef3  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Path(string value)
0x1ef8  ldarg.0
0x1ef9  ldloc.s  5
0x1efb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1f00  ldstr    aContract// "contract"
0x1f05  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1f0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1f0f  unbox.any ContractType
0x1f14  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Contract(valuetype ContractType value)
0x1f19  ldloc.s  5
0x1f1b  ldstr    aMessageformat// "messageformat"
0x1f20  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1f25  brfalse.s loc_1F30
0x1f27  ldarg.0
0x1f28  ldc.i4.1
0x1f29  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_MessageFormat(valuetype MessageFormatType value)
0x1f2e  br.s     loc_1F51
0x1f30  ldarg.0
0x1f31  ldloc.s  5
0x1f33  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1f38  ldstr    aMessageformat// "messageformat"
0x1f3d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1f42  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1f47  unbox.any MessageFormatType
0x1f4c  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_MessageFormat(valuetype MessageFormatType value)
0x1f51  ldloc.s  5
0x1f53  ldstr    aNamespaceforma// "namespaceformat"
0x1f58  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1f5d  brfalse.s loc_1F68
0x1f5f  ldarg.0
0x1f60  ldc.i4.1
0x1f61  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_NamespaceFormat(valuetype NamespaceFormatType value)
0x1f66  br.s     loc_1F89
0x1f68  ldarg.0
0x1f69  ldloc.s  5
0x1f6b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1f70  ldstr    aNamespaceforma// "namespaceformat"
0x1f75  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1f7a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1f7f  unbox.any NamespaceFormatType
0x1f84  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_NamespaceFormat(valuetype NamespaceFormatType value)
0x1f89  ldarg.0
0x1f8a  call     instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceFormat()
0x1f8f  ldc.i4.2
0x1f90  bne.un.s loc_1FB3
0x1f92  ldarg.0
0x1f93  ldloc.s  5
0x1f95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1f9a  ldstr    aNamespaceaddre// "namespaceaddress"
0x1f9f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1fa4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1fa9  callvirt instance string [mscorlib]System.Object::ToString()
0x1fae  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_NamespaceAddress(string value)
0x1fb3  ldloc.s  5
0x1fb5  ldstr    aAuthtype// "authtype"
0x1fba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1fbf  brfalse.s loc_1FCA
0x1fc1  ldarg.0
0x1fc2  ldc.i4.1
0x1fc3  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_AuthType(valuetype AuthenticationType value)
0x1fc8  br.s     loc_1FEB
0x1fca  ldarg.0
0x1fcb  ldloc.s  5
0x1fcd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1fd2  ldstr    aAuthtype// "authtype"
0x1fd7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1fdc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1fe1  unbox.any AuthenticationType
0x1fe6  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_AuthType(valuetype AuthenticationType value)
0x1feb  ldloc.s  5
0x1fed  ldstr    aName// "name"
0x1ff2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ff7  brtrue.s loc_2010
0x1ff9  ldarg.0
0x1ffa  ldloc.s  5
0x1ffc  ldstr    aName// "name"
0x2001  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2006  castclass [mscorlib]System.String
0x200b  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Name(string value)
0x2010  ldloc.s  5
0x2012  ldstr    aServiceendpoin_4// "serviceendpointid"
0x2017  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x201c  brtrue.s loc_2044
0x201e  ldarg.0
0x201f  ldloc.s  5
0x2021  ldstr    aServiceendpoin_4// "serviceendpointid"
0x2026  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x202b  unbox.any [mscorlib]System.Guid
0x2030  stloc.s  6
0x2032  ldloca.s 6
0x2034  constrained. [mscorlib]System.Guid
0x203a  callvirt instance string [mscorlib]System.Object::ToString()
0x203f  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ServiceEndpointId(string value)
0x2044  ldarg.0
0x2045  call     instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0x204a  ldc.i4.2
0x204b  bne.un   loc_210D
0x2050  ldloc.s  5
0x2052  ldstr    aSaskey// "saskey"
0x2057  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x205c  ldloc.s  5
0x205e  ldstr    aSaskeyname// "saskeyname"
0x2063  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2068  stloc.s  7
0x206a  ldloc.s  7
0x206c  or
0x206d  brfalse.s loc_20C6
0x206f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2074  ldstr    aASaskeyHasNotB// "A SASKey has not been configured for Se"...
0x2079  ldc.i4.2
0x207a  newarr   [mscorlib]System.Object
0x207f  dup
0x2080  ldc.i4.0
0x2081  ldloc.s  5
0x2083  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x2088  ldstr    aName// "name"
0x208d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x2092  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x2097  callvirt instance string [mscorlib]System.Object::ToString()
0x209c  stelem.ref
0x209d  dup
0x209e  ldc.i4.1
0x209f  ldloc.s  5
0x20a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x20a6  ldstr    aServiceendpoin_4// "serviceendpointid"
0x20ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x20b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x20b5  callvirt instance string [mscorlib]System.Object::ToString()
0x20ba  stelem.ref
0x20bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x20c5  throw
0x20c6  ldarg.0
0x20c7  ldloc.s  5
0x20c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x20ce  ldstr    aSaskeyname// "saskeyname"
0x20d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x20d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x20dd  callvirt instance string [mscorlib]System.Object::ToString()
0x20e2  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_SASKeyName(string value)
0x20e7  ldarg.0
0x20e8  ldloc.s  5
0x20ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x20ef  ldstr    aSaskey// "saskey"
0x20f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x20f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x20fe  callvirt instance string [mscorlib]System.Object::ToString()
0x2103  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_SASKey(string value)
0x2108  br       loc_229D
0x210d  ldarg.0
0x210e  call     instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType()
0x2113  ldc.i4.3
0x2114  bne.un   loc_21A4
0x2119  ldloc.s  5
0x211b  ldstr    aSastoken// "sastoken"
0x2120  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2125  brfalse.s loc_217E
0x2127  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x212c  ldstr    aASastokenHasNo// "A SASToken has not been configured for "...
0x2131  ldc.i4.2
0x2132  newarr   [mscorlib]System.Object
0x2137  dup
0x2138  ldc.i4.0
0x2139  ldloc.s  5
0x213b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x2140  ldstr    aName// "name"
0x2145  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x214a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x214f  callvirt instance string [mscorlib]System.Object::ToString()
0x2154  stelem.ref
0x2155  dup
0x2156  ldc.i4.1
0x2157  ldloc.s  5
0x2159  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x215e  ldstr    aServiceendpoin_4// "serviceendpointid"
0x2163  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x2168  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
  ... truncated ...
```
