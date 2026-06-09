# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::.ctor

- ea: `0x120`
- end: `0x2dd`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::.ctor`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3a0`
- `0x650`

## callees

- `0x30`
- `0x50`
- `0x70`
- `0x90`
- `0xb0`
- `0xd0`
- `0xf0`
- `0x100`
- `0x110`
- `0x120`
- `0x2e0`
- `0x1be0`

## string_xrefs

- `0x2a6`: `isinternalcrmappsinstall`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  call     instance void [mscorlib]System.Object::.ctor()
0x126  ldarg.0
0x127  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::.ctor()
0x12c  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_PDArgs(class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments value)
0x131  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x136  stloc.0
0x137  ldarg.1
0x138  stloc.2
0x139  ldc.i4.0
0x13a  stloc.3
0x13b  br.s     loc_199
0x13d  ldloc.2
0x13e  ldloc.3
0x13f  ldelem.ref
0x140  stloc.s  4
0x142  ldloc.s  4
0x144  ldstr    aPayload// "payload"
0x149  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x14e  brfalse.s loc_16E
0x150  ldloc.0
0x151  ldstr    aPayload// "payload"
0x156  ldloc.s  4
0x158  ldstr    aPayload_0// "payload="
0x15d  ldstr    asc_3022// ""
0x162  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x167  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c  br.s     loc_195
0x16e  ldloc.s  4
0x170  ldc.i4.1
0x171  newarr   [mscorlib]System.Char
0x176  dup
0x177  ldc.i4.0
0x178  ldc.i4.s 0x3D
0x17a  stelem.i2
0x17b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x180  stloc.s  5
0x182  ldloc.0
0x183  ldloc.s  5
0x185  ldc.i4.0
0x186  ldelem.ref
0x187  ldloc.s  5
0x189  ldc.i4.1
0x18a  ldelem.ref
0x18b  call     string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::StripQuote(string str)
0x190  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x195  ldloc.3
0x196  ldc.i4.1
0x197  add
0x198  stloc.3
0x199  ldloc.3
0x19a  ldloc.2
0x19b  ldlen
0x19c  conv.i4
0x19d  blt.s    loc_13D
0x19f  ldloc.0
0x1a0  ldstr    aApiport// "apiport"
0x1a5  ldloca.s 1
0x1a7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x1ac  brfalse.s loc_1BB
0x1ae  ldarg.0
0x1af  ldloc.1
0x1b0  call     int32 [mscorlib]System.Int32::Parse(string)
0x1b5  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_ApiPort(int32 value)
0x1ba  ret
0x1bb  ldarg.0
0x1bc  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x1c1  ldloc.0
0x1c2  ldstr    aOrganizationid// "organizationid"
0x1c7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1cc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x1d1  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0x1d6  ldarg.0
0x1d7  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x1dc  ldloc.0
0x1dd  ldstr    aUserid// "userid"
0x1e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1e7  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x1ec  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::UserId
0x1f1  ldarg.0
0x1f2  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x1f7  ldloc.0
0x1f8  ldstr    aPackagelocatio// "packagelocation"
0x1fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x202  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0x207  ldarg.0
0x208  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x20d  ldloc.0
0x20e  ldstr    aPackagename// "packagename"
0x213  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x218  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0x21d  ldarg.0
0x21e  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x223  ldloc.0
0x224  ldstr    aAllowpackageco// "allowpackagecodeexecution"
0x229  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x22e  call     bool [mscorlib]System.Boolean::Parse(string)
0x233  stfld    bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::AllowPackageCodeExecution
0x238  ldarg.0
0x239  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::get_PDArgs()
0x23e  ldloc.0
0x23f  ldstr    aPayload// "payload"
0x244  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x249  brtrue.s loc_252
0x24b  ldstr    asc_3022// ""
0x250  br.s     loc_25D
0x252  ldloc.0
0x253  ldstr    aPayload// "payload"
0x258  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x25d  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x262  ldarg.0
0x263  ldloc.0
0x264  ldstr    aIslive// "islive"
0x269  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x26e  call     bool [mscorlib]System.Boolean::Parse(string)
0x273  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_IsLive(bool value)
0x278  ldarg.0
0x279  ldloc.0
0x27a  ldstr    aIssystemconver// "issystemconvertedsolutionupgrade"
0x27f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x284  call     bool [mscorlib]System.Boolean::Parse(string)
0x289  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_IsSystemConvertedSolutionUpgrade(bool value)
0x28e  ldarg.0
0x28f  ldloc.0
0x290  ldstr    aUsessl// "usessl"
0x295  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x29a  call     bool [mscorlib]System.Boolean::Parse(string)
0x29f  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_UseSSL(bool value)
0x2a4  ldarg.0
0x2a5  ldloc.0
0x2a6  ldstr    aIsinternalcrma// "isinternalcrmappsinstall"
0x2ab  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2b0  call     bool [mscorlib]System.Boolean::Parse(string)
0x2b5  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_IsInternalCRMAppsInstall(bool value)
0x2ba  ldarg.0
0x2bb  ldloc.0
0x2bc  ldstr    aOrganizationun// "organizationuniquename"
0x2c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2c6  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_OrganizationUniqueName(string value)
0x2cb  ldarg.0
0x2cc  ldloc.0
0x2cd  ldstr    aHostname// "hostname"
0x2d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2d7  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::set_Hostname(string value)
0x2dc  ret
```
