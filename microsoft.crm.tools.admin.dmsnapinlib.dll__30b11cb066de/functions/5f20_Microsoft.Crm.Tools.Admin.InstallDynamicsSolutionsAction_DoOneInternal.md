# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::DoOneInternal

- ea: `0x5f20`
- end: `0x617e`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::DoOneInternal`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x193c0`

## callees

- `0x2b40`
- `0x5dc0`
- `0x5f20`
- `0x6180`
- `0x61f0`
- `0x6980`
- `0x8630`
- `0x8e30`
- `0x16d30`
- `0x193f0`

## string_xrefs

- `0x5f34`: `Installing {0} from {1}.`
- `0x6095`: `Failed to install {0}`
- `0x60f0`: `InstallDynamicsSolutionsAction: `
- `0x6129`: `fileFullPathAndName`

## pseudocode

```c

```

## disassembly

```asm
0x5f20  newobj   instance void <>c__DisplayClass31_0::.ctor()
0x5f25  stloc.0
0x5f26  ldloc.0
0x5f27  ldarg.1
0x5f28  stfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x5f2d  ldloc.0
0x5f2e  ldarg.3
0x5f2f  stfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x5f34  ldstr    aInstalling0Fro// "Installing {0} from {1}."
0x5f39  ldloc.0
0x5f3a  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x5f3f  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x5f44  ldarg.2
0x5f45  call     string [mscorlib]System.String::Format(string, object, object)
0x5f4a  ldc.i4.0
0x5f4b  newarr   [mscorlib]System.Object
0x5f50  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x5f55  ldloc.0
0x5f56  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x5f5b  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x5f60  pop
0x5f61  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x5f66  stloc.1
0x5f67  ldloc.1
0x5f68  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x5f6d  ldc.i4.0
0x5f6e  conv.i8
0x5f6f  stloc.2
0x5f70  ldsfld   string [mscorlib]System.String::Empty
0x5f75  stloc.3
0x5f76  ldsfld   string [mscorlib]System.String::Empty
0x5f7b  stloc.s  4
0x5f7d  ldsfld   string [mscorlib]System.String::Empty
0x5f82  stloc.s  5
0x5f84  ldsfld   string [mscorlib]System.String::Empty
0x5f89  stloc.s  6
0x5f8b  ldsfld   string [mscorlib]System.String::Empty
0x5f90  stloc.s  7
0x5f92  ldsfld   string [mscorlib]System.String::Empty
0x5f97  stloc.s  8
0x5f99  ldnull
0x5f9a  stloc.s  9
0x5f9c  ldc.i4.0
0x5f9d  stloc.s  0xA
0x5f9f  ldloc.0
0x5fa0  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x5fa5  callvirt instance bool [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UsePackage()
0x5faa  brtrue.s loc_5FF8
0x5fac  ldstr    aUsepackageNo// "UsePackage :No"
0x5fb1  stloc.3
0x5fb2  ldarg.0
0x5fb3  call     instance bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::get_IsSystemConverted()
0x5fb8  brfalse.s loc_5FDC
0x5fba  ldstr    aSystemconverte// "SystemConverted :Yes"
0x5fbf  stloc.s  4
0x5fc1  ldstr    aAllSystemConve// "All system converted solutions must be "...
0x5fc6  ldloc.0
0x5fc7  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x5fcc  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x5fd1  call     string [mscorlib]System.String::Format(string, object)
0x5fd6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x5fdb  throw
0x5fdc  ldstr    aSystemconverte_0// "SystemConverted :No"
0x5fe1  stloc.s  4
0x5fe3  ldarg.0
0x5fe4  ldloc.0
0x5fe5  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x5fea  ldarg.2
0x5feb  ldloc.0
0x5fec  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x5ff1  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsCustomSolution(class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo solutionInfo, string fileFullPathAndName, class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x5ff6  br.s     loc_601B
0x5ff8  ldstr    aUsepackageYes// "UsePackage :Yes"
0x5ffd  stloc.3
0x5ffe  ldarg.0
0x5fff  ldloc.0
0x6000  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x6005  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x600a  ldarg.2
0x600b  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x6010  ldloc.0
0x6011  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x6016  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsPackage(string solutionUniqueName, class [mscorlib]System.IO.FileInfo packageFile, class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x601b  ldloc.1
0x601c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x6021  ldloc.1
0x6022  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x6027  stloc.2
0x6028  ldloc.0
0x6029  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x602e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x6033  ldarg.0
0x6034  call     instance string Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetDatabaseVersionString()
0x6039  ldloc.0
0x603a  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x603f  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x6044  ldloc.3
0x6045  ldloc.s  4
0x6047  ldloc.0
0x6048  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x604d  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_FullFileName()
0x6052  ldloc.0
0x6053  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x6058  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x605d  stloc.s  0xB
0x605f  ldloca.s 0xB
0x6061  constrained. [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType
0x6067  callvirt instance string [mscorlib]System.Object::ToString()
0x606c  ldloc.2
0x606d  call     void Microsoft.Crm.Tools.Admin.SetupTelemetry::SetupSolutionInstalled(valuetype [mscorlib]System.Guid organizationId, string dbVersion, string solutionName, string type, string isSystemConverted, string fileLocation, string orgState, int64 timeTaken)
0x6072  leave    loc_6129
0x6077  ldc.i4.1
0x6078  stloc.s  0xA
0x607a  dup
0x607b  stloc.s  9
0x607d  dup
0x607e  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x6083  stloc.s  6
0x6085  dup
0x6086  callvirt instance string [mscorlib]System.Exception::get_Message()
0x608b  stloc.s  5
0x608d  dup
0x608e  callvirt instance string [mscorlib]System.Object::ToString()
0x6093  stloc.s  8
0x6095  ldstr    aFailedToInstal_0// "Failed to install {0}"
0x609a  ldloc.0
0x609b  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x60a0  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x60a5  call     string [mscorlib]System.String::Format(string, object)
0x60aa  stloc.s  7
0x60ac  isinst   [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerException
0x60b1  stloc.s  0xC
0x60b3  ldloc.s  0xC
0x60b5  brfalse.s loc_60C9
0x60b7  ldloc.s  0xC
0x60b9  call     instance string [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerException::get_Error()
0x60be  brfalse.s loc_60C9
0x60c0  ldloc.s  0xC
0x60c2  callvirt instance string [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerException::get_Error()
0x60c7  stloc.s  5
0x60c9  leave.s  loc_6129
0x60cb  ldloc.0
0x60cc  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x60d1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x60d6  ldloc.0
0x60d7  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x60dc  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x60e1  stloc.s  0xB
0x60e3  ldloca.s 0xB
0x60e5  constrained. [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType
0x60eb  callvirt instance string [mscorlib]System.Object::ToString()
0x60f0  ldstr    aInstalldynamic_1// "InstallDynamicsSolutionsAction: "
0x60f5  ldloc.0
0x60f6  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x60fb  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x6100  call     string [mscorlib]System.String::Concat(string, string)
0x6105  ldsfld   string [mscorlib]System.String::Empty
0x610a  ldloc.s  0xA
0x610c  ldloc.s  7
0x610e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x6113  ldloc.2
0x6114  ldloc.s  6
0x6116  ldloc.s  5
0x6118  ldloc.s  8
0x611a  ldarg.0
0x611b  call     instance string Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetDatabaseVersionString()
0x6120  ldloc.s  0xA
0x6122  ldc.i4.0
0x6123  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmActionTelemetryHelper::OrganizationActionCompleted(valuetype [mscorlib]System.Guid, string, string, string, bool, string, string, int64, string, string, string, string, bool, bool)
0x6128  endfinally
0x6129  ldstr    aFilefullpathan// "fileFullPathAndName"
0x612e  ldarg.2
0x612f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6134  ldloc.s  0xA
0x6136  brfalse.s loc_614A
0x6138  ldloc.0
0x6139  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x613e  ldloc.s  7
0x6140  ldloc.s  9
0x6142  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x6147  ldloc.s  9
0x6149  throw
0x614a  ldloc.0
0x614b  ldftn    instance string <>c__DisplayClass31_0::<DoOneInternal>b__0()
0x6151  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x6156  ldstr    aSetsolutionvis// "SetSolutionVisibility for "
0x615b  ldloc.0
0x615c  ldfld    class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo <>c__DisplayClass31_0::solutionInfo
0x6161  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x6166  call     string [mscorlib]System.String::Concat(string, string)
0x616b  ldloc.0
0x616c  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass31_0::organizationInfo
0x6171  ldarg.0
0x6172  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x6177  call     T0x2B000008
0x617c  pop
0x617d  ret
```
