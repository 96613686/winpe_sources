# Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::CreatePackageDeploymentExecutorArgs

- ea: `0x6fd0`
- end: `0x70a6`
- name: `Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::CreatePackageDeploymentExecutorArgs`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19480`

## callees

- `0x70b0`

## string_xrefs

- `0x7061`: `isinternalcrmappsinstall`

## pseudocode

```c

```

## disassembly

```asm
0x6fd0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6fd5  stloc.0
0x6fd6  ldstr    aOrganizationid_1// "organizationid"
0x6fdb  ldarga.s 0
0x6fdd  constrained. [mscorlib]System.Guid
0x6fe3  callvirt instance string [mscorlib]System.Object::ToString()
0x6fe8  ldloc.0
0x6fe9  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x6fee  ldstr    aUserid// "userid"
0x6ff3  ldarga.s 1
0x6ff5  constrained. [mscorlib]System.Guid
0x6ffb  callvirt instance string [mscorlib]System.Object::ToString()
0x7000  ldloc.0
0x7001  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7006  ldstr    aPackagelocatio// "packagelocation"
0x700b  ldarg.2
0x700c  ldloc.0
0x700d  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7012  ldstr    aPackagename// "packagename"
0x7017  ldarg.3
0x7018  ldloc.0
0x7019  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x701e  ldstr    aAllowpackageco// "allowpackagecodeexecution"
0x7023  ldarga.s 4
0x7025  call     instance string [mscorlib]System.Boolean::ToString()
0x702a  ldloc.0
0x702b  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7030  ldstr    aPayload// "payload"
0x7035  ldarg.s  0xB
0x7037  ldloc.0
0x7038  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x703d  ldstr    aIslive// "islive"
0x7042  ldarga.s 5
0x7044  call     instance string [mscorlib]System.Boolean::ToString()
0x7049  ldloc.0
0x704a  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x704f  ldstr    aIssystemconver// "issystemconvertedsolutionupgrade"
0x7054  ldarga.s 6
0x7056  call     instance string [mscorlib]System.Boolean::ToString()
0x705b  ldloc.0
0x705c  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7061  ldstr    aIsinternalcrma// "isinternalcrmappsinstall"
0x7066  ldarga.s 7
0x7068  call     instance string [mscorlib]System.Boolean::ToString()
0x706d  ldloc.0
0x706e  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7073  ldstr    aUsessl// "usessl"
0x7078  ldarga.s 9
0x707a  call     instance string [mscorlib]System.Boolean::ToString()
0x707f  ldloc.0
0x7080  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7085  ldstr    aOrganizationun_0// "organizationuniquename"
0x708a  ldarg.s  8
0x708c  ldloc.0
0x708d  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x7092  ldstr    aHostname// "hostname"
0x7097  ldarg.s  0xA
0x7099  ldloc.0
0x709a  call     void Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::AddArgumentToString(string arg, string val, class [mscorlib]System.Collections.Generic.List`1<string> sb)
0x709f  ldloc.0
0x70a0  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x70a5  ret
```
