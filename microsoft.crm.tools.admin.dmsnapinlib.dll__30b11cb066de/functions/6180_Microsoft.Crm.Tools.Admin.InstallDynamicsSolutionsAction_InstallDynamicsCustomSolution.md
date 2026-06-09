# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsCustomSolution

- ea: `0x6180`
- end: `0x61e6`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsCustomSolution`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5f20`

## callees

- `0x8630`
- `0x8e30`
- `0x189d0`
- `0x189f0`
- `0x19430`

## string_xrefs

- `0x61c3`: `Install solution `

## pseudocode

```c

```

## disassembly

```asm
0x6180  newobj   instance void <>c__DisplayClass32_0::.ctor()
0x6185  stloc.0
0x6186  ldloc.0
0x6187  ldarg.1
0x6188  stfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass32_0::solutionInfo
0x618d  ldloc.0
0x618e  ldarg.2
0x618f  stfld    string <>c__DisplayClass32_0::fileFullPathAndName
0x6194  ldarg.3
0x6195  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x619a  pop
0x619b  ldloc.0
0x619c  newobj   instance void Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::.ctor()
0x61a1  stfld    class Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution <>c__DisplayClass32_0::importCustomSolution
0x61a6  ldloc.0
0x61a7  ldfld    class Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution <>c__DisplayClass32_0::importCustomSolution
0x61ac  ldarg.3
0x61ad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x61b2  callvirt instance void Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x61b7  ldloc.0
0x61b8  ldftn    instance string <>c__DisplayClass32_0::<InstallDynamicsCustomSolution>b__0()
0x61be  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x61c3  ldstr    aInstallSolutio// "Install solution "
0x61c8  ldloc.0
0x61c9  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass32_0::solutionInfo
0x61ce  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x61d3  call     string [mscorlib]System.String::Concat(string, string)
0x61d8  ldarg.3
0x61d9  ldarg.0
0x61da  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x61df  call     T0x2B000008
0x61e4  pop
0x61e5  ret
```
