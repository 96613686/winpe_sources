# Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectInNewAppDomain

- ea: `0x1590`
- end: `0x1713`
- name: `Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectInNewAppDomain`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18c0`

## callees

- `0x1040`
- `0x12e0`
- `0x12f0`
- `0x1300`
- `0x1310`
- `0x1320`
- `0x1330`
- `0x1340`
- `0x1350`
- `0x1360`
- `0x1370`
- `0x1380`
- `0x1390`
- `0x13a0`
- `0x13b0`
- `0x13c0`
- `0x13e0`
- `0x13f0`
- `0x1400`
- `0x1410`
- `0x1590`

## pseudocode

```c

```

## disassembly

```asm
0x1590  ldnull
0x1591  stloc.0
0x1592  newobj   instance void [mscorlib]System.AppDomainSetup::.ctor()
0x1597  stloc.1
0x1598  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x159d  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x15a2  stloc.2
0x15a3  ldloc.2
0x15a4  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x15a9  stloc.s  5
0x15ab  ldloc.s  5
0x15ad  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x15b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x15bc  ldstr    aXrmdeployment// "XRMDEPLOYMENT"
0x15c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15c6  brfalse.s loc_15E1
0x15c8  ldloc.1
0x15c9  ldloc.s  5
0x15cb  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x15d0  ldstr    aBin// "bin"
0x15d5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15da  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x15df  br.s     loc_15E8
0x15e1  ldloc.1
0x15e2  ldloc.2
0x15e3  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x15e8  leave.s  loc_15F4
0x15ea  pop
0x15eb  ldloc.1
0x15ec  ldloc.2
0x15ed  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x15f2  leave.s  loc_15F4
0x15f4  ldnull
0x15f5  stloc.3
0x15f6  ldc.i4.1
0x15f7  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x15fc  stloc.3
0x15fd  ldstr    aAppdomain// "AppDomain: "
0x1602  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1607  stloc.s  6
0x1609  ldloca.s 6
0x160b  ldstr    aB// "B"
0x1610  call     instance string [mscorlib]System.Guid::ToString(string)
0x1615  call     string [mscorlib]System.String::Concat(string, string)
0x161a  ldnull
0x161b  ldloc.1
0x161c  ldloc.3
0x161d  ldnull
0x161e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::CreateDomain(string, class [mscorlib]System.Security.Policy.Evidence, class [mscorlib]System.AppDomainSetup, class [mscorlib]System.Security.PermissionSet, class [mscorlib]System.Security.Policy.StrongName[])
0x1623  stloc.0
0x1624  ldloc.0
0x1625  ldtoken  Microsoft.Crm.LegacyFeatureCheck.PluginAssembly
0x162a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x162f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1634  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1639  ldtoken  Microsoft.Crm.LegacyFeatureCheck.PluginAssembly
0x163e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1643  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1648  callvirt instance object [mscorlib]System.AppDomain::CreateInstanceAndUnwrap(string, string)
0x164d  castclass Microsoft.Crm.LegacyFeatureCheck.PluginAssembly
0x1652  stloc.s  4
0x1654  ldloc.s  4
0x1656  ldarg.0
0x1657  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Contents()
0x165c  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Contents(string value)
0x1661  ldloc.s  4
0x1663  ldarg.0
0x1664  call     instance valuetype Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Source()
0x1669  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Source(valuetype Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation value)
0x166e  ldloc.s  4
0x1670  ldarg.0
0x1671  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Name()
0x1676  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Name(string value)
0x167b  ldloc.s  4
0x167d  ldarg.0
0x167e  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Version()
0x1683  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Version(string value)
0x1688  ldloc.s  4
0x168a  ldarg.0
0x168b  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Path()
0x1690  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Path(string value)
0x1695  ldloc.s  4
0x1697  ldarg.0
0x1698  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Culture()
0x169d  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Culture(string value)
0x16a2  ldloc.s  4
0x16a4  ldarg.0
0x16a5  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_PublicKeyToken()
0x16aa  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_PublicKeyToken(string value)
0x16af  ldloc.s  4
0x16b1  ldarg.1
0x16b2  ldarg.0
0x16b3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Id()
0x16b8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginStepsForAssembly(valuetype [mscorlib]System.Guid pluginAssemblyId)
0x16bd  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_PluginSteps(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> value)
0x16c2  ldloc.0
0x16c3  ldloc.s  4
0x16c5  ldftn    instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::InspectAssembly()
0x16cb  newobj   instance void [mscorlib]System.CrossAppDomainDelegate::.ctor(object, native int)
0x16d0  callvirt instance void [mscorlib]System.AppDomain::DoCallBack(class [mscorlib]System.CrossAppDomainDelegate)
0x16d5  ldarg.0
0x16d6  ldloc.s  4
0x16d8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_PluginSteps()
0x16dd  call     instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_PluginSteps(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep> value)
0x16e2  ldarg.0
0x16e3  ldloc.s  4
0x16e5  callvirt instance bool Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_IsV4Assembly()
0x16ea  call     instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_IsV4Assembly(bool value)
0x16ef  leave.s  loc_1712
0x16f1  ldloc.0
0x16f2  brfalse.s loc_1711
0x16f4  ldloc.0
0x16f5  call     void [mscorlib]System.AppDomain::Unload(class [mscorlib]System.AppDomain)
0x16fa  leave.s  loc_1711
0x16fc  stloc.s  7
0x16fe  ldstr    aExceptionWhile// "Exception while unloading AppDomain: {0"...
0x1703  ldloc.s  7
0x1705  callvirt instance string [mscorlib]System.Exception::get_Message()
0x170a  call     void [mscorlib]System.Console::WriteLine(string, object)
0x170f  leave.s  loc_1711
0x1711  endfinally
0x1712  ret
```
