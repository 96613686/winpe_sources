# Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::BeforeUserMapping

- ea: `0x12910`
- end: `0x12a6c`
- name: `Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::BeforeUserMapping`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x122b0`
- `0x12540`
- `0x127a0`
- `0x127c0`
- `0x127d0`
- `0x127e0`
- `0x127f0`
- `0x12810`
- `0x12910`

## string_xrefs

- `0x12916`: `MapByMappingFile running. Mapping users using UserMappingXMLString.`
- `0x12957`: `/MappingConfiguration/UserMapping`
- `0x129cf`: `/MappingConfiguration/DomainMapping`

## pseudocode

```c

```

## disassembly

```asm
0x12910  ldarg.0
0x12911  call     instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::BeforeUserMapping()
0x12916  ldstr    aMapbymappingfi// "MapByMappingFile running. Mapping users"...
0x1291b  ldc.i4.0
0x1291c  newarr   [mscorlib]System.Object
0x12921  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteFormat(string, object[])
0x12926  ldarg.0
0x12927  call     instance string Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::get_UserMappingString()
0x1292c  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x12931  stloc.1
0x12932  ldloc.1
0x12933  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [mscorlib]System.IO.TextReader)
0x12938  stloc.0
0x12939  leave.s  loc_1294F
0x1293b  stloc.s  4
0x1293d  ldarg.0
0x1293e  ldloc.s  4
0x12940  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapExceptionError::.ctor(class [mscorlib]System.Exception)
0x12945  call     instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::set_MappingResult(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult value)
0x1294a  leave    loc_12A6B
0x1294f  ldloc.0
0x12950  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathDocument::CreateNavigator()
0x12955  stloc.2
0x12956  ldloc.2
0x12957  ldstr    aMappingconfigu// "/MappingConfiguration/UserMapping"
0x1295c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x12961  stloc.3
0x12962  ldarg.0
0x12963  ldloc.3
0x12964  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x12969  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1296e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(int32, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x12973  call     instance void Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::set_Accounts(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x12978  br.s     loc_129C6
0x1297a  ldloc.3
0x1297b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x12980  stloc.2
0x12981  ldloc.2
0x12982  ldstr    aOld// "old"
0x12987  ldsfld   string [mscorlib]System.String::Empty
0x1298c  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x12991  stloc.s  5
0x12993  ldloc.2
0x12994  ldstr    aNew// "new"
0x12999  ldsfld   string [mscorlib]System.String::Empty
0x1299e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x129a3  stloc.s  6
0x129a5  ldloc.s  5
0x129a7  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::IsDomainAccountValid(string)
0x129ac  brfalse.s loc_129C6
0x129ae  ldloc.s  6
0x129b0  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::IsDomainAccountValid(string)
0x129b5  brfalse.s loc_129C6
0x129b7  ldarg.0
0x129b8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::get_Accounts()
0x129bd  ldloc.s  5
0x129bf  ldloc.s  6
0x129c1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x129c6  ldloc.3
0x129c7  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x129cc  brtrue.s loc_1297A
0x129ce  ldloc.2
0x129cf  ldstr    aMappingconfigu_0// "/MappingConfiguration/DomainMapping"
0x129d4  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x129d9  stloc.3
0x129da  ldarg.0
0x129db  ldloc.3
0x129dc  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x129e1  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x129e6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(int32, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x129eb  call     instance void Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::set_Domains(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x129f0  br.s     loc_12A50
0x129f2  ldloc.3
0x129f3  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x129f8  stloc.2
0x129f9  ldloc.2
0x129fa  ldstr    aOld// "old"
0x129ff  ldsfld   string [mscorlib]System.String::Empty
0x12a04  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x12a09  stloc.s  7
0x12a0b  ldloc.2
0x12a0c  ldstr    aNew// "new"
0x12a11  ldsfld   string [mscorlib]System.String::Empty
0x12a16  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x12a1b  stloc.s  8
0x12a1d  ldloc.s  7
0x12a1f  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::IsDomainValid(string)
0x12a24  brtrue.s loc_12A2F
0x12a26  ldloc.s  7
0x12a28  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.FederatedUserInformation::ValidateUserPrincipalName(string)
0x12a2d  brfalse.s loc_12A50
0x12a2f  ldloc.s  8
0x12a31  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::IsDomainValid(string)
0x12a36  brtrue.s loc_12A41
0x12a38  ldloc.s  8
0x12a3a  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.FederatedUserInformation::ValidateUserPrincipalName(string)
0x12a3f  brfalse.s loc_12A50
0x12a41  ldarg.0
0x12a42  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::get_Domains()
0x12a47  ldloc.s  7
0x12a49  ldloc.s  8
0x12a4b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a50  ldloc.3
0x12a51  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x12a56  brtrue.s loc_129F2
0x12a58  ldarg.0
0x12a59  ldc.i4.1
0x12a5a  call     instance void Microsoft.Crm.Tools.Admin.ByMappingFileUserMapper::set_Initialized(bool value)
0x12a5f  leave.s  loc_12A6B
0x12a61  ldloc.1
0x12a62  brfalse.s loc_12A6A
0x12a64  ldloc.1
0x12a65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12a6a  endfinally
0x12a6b  ret
```
