# Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::TryGetMultiTenantPdExePath

- ea: `0x18710`
- end: `0x187b0`
- name: `Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::TryGetMultiTenantPdExePath`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x183f0`

## callees

- `0x18710`

## string_xrefs

- `0x18794`: `CrmMultiTenantPackageDeploymentExecutorPath`

## pseudocode

```c

```

## disassembly

```asm
0x18710  ldstr    aFile// "file:\\"
0x18715  stloc.0
0x18716  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x1871b  callvirt instance string [mscorlib]System.Reflection.Assembly::get_CodeBase()
0x18720  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x18725  stloc.1
0x18726  ldloc.1
0x18727  ldloc.0
0x18728  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x1872d  brfalse.s loc_1873C
0x1872f  ldloc.1
0x18730  ldloc.0
0x18731  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18736  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1873b  stloc.1
0x1873c  ldloc.1
0x1873d  ldstr    aMultitenantpd// "MultiTenantPD"
0x18742  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x18747  stloc.2
0x18748  ldarg.0
0x18749  ldloc.2
0x1874a  ldstr    aMicrosoftCrmMu// "Microsoft.Crm.MultiTenantPackageDeploym"...
0x1874f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x18754  stind.ref
0x18755  ldarg.0
0x18756  ldind.ref
0x18757  call     bool [mscorlib]System.IO.File::Exists(string)
0x1875c  brtrue.s loc_187AE
0x1875e  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerInstallKeyDir()
0x18763  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x18768  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1876d  castclass [mscorlib]System.String
0x18772  stloc.3
0x18773  ldarg.0
0x18774  ldloc.3
0x18775  ldstr    aServer_0// "Server"
0x1877a  ldstr    aMultitenantpd// "MultiTenantPD"
0x1877f  ldstr    aMicrosoftCrmMu// "Microsoft.Crm.MultiTenantPackageDeploym"...
0x18784  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x18789  stind.ref
0x1878a  ldarg.0
0x1878b  ldind.ref
0x1878c  call     bool [mscorlib]System.IO.File::Exists(string)
0x18791  brtrue.s loc_187AE
0x18793  ldarg.0
0x18794  ldstr    aCrmmultitenant// "CrmMultiTenantPackageDeploymentExecutor"...
0x18799  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x1879e  stind.ref
0x1879f  ldarg.0
0x187a0  ldind.ref
0x187a1  brfalse.s loc_187AC
0x187a3  ldarg.0
0x187a4  ldind.ref
0x187a5  call     bool [mscorlib]System.IO.File::Exists(string)
0x187aa  brtrue.s loc_187AE
0x187ac  ldc.i4.0
0x187ad  ret
0x187ae  ldc.i4.1
0x187af  ret
```
