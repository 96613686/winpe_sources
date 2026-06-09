# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::Do

- ea: `0x1f10`
- end: `0x2096`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::Do`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x1f10`
- `0x20a0`
- `0x20b0`
- `0x20f0`
- `0x2100`
- `0x2130`
- `0x2140`
- `0x2160`
- `0x2170`
- `0x2210`
- `0x2230`

## string_xrefs

- `0x1f1f`: `{0} is already installed.`
- `0x1f88`: `Preparing to install package {0} with options: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldarg.1
0x1f12  call     instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::set_Parameters(class [mscorlib]System.Collections.IDictionary value)
0x1f17  ldarg.0
0x1f18  call     instance bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_IsProductInstalled()
0x1f1d  brfalse.s loc_1F47
0x1f1f  ldstr    a0IsAlreadyInst// "{0} is already installed."
0x1f24  ldc.i4.1
0x1f25  newarr   [mscorlib]System.Object
0x1f2a  dup
0x1f2b  ldc.i4.0
0x1f2c  ldarg.0
0x1f2d  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_ProductName()
0x1f32  stelem.ref
0x1f33  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1f38  ldarg.0
0x1f39  ldarg.0
0x1f3a  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_ProductName()
0x1f3f  ldc.i4.s 0x64
0x1f41  call     instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::UpdateProgress(string text, int32 value)
0x1f46  ret
0x1f47  ldnull
0x1f48  stloc.0
0x1f49  ldc.i4.0
0x1f4a  stloc.1
0x1f4b  ldarg.0
0x1f4c  callvirt instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::BeforeInstall()
0x1f51  call     class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_Instance()
0x1f56  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_ProgressEventSource()
0x1f5b  stloc.0
0x1f5c  call     class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_Instance()
0x1f61  ldarg.0
0x1f62  ldfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_progressHandler
0x1f67  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::set_ProgressEventSource(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource)
0x1f6c  call     class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_Instance()
0x1f71  ldc.i4.5
0x1f72  ldc.i4.s 0x5F
0x1f74  ldarg.0
0x1f75  callvirt instance bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_IgnoreFilesInUse()
0x1f7a  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::Hook(int32, int32, bool)
0x1f7f  ldc.i4.1
0x1f80  stloc.1
0x1f81  ldarg.0
0x1f82  call     instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::ConstructInstallCommandLine()
0x1f87  stloc.2
0x1f88  ldstr    aPreparingToIns// "Preparing to install package {0} with o"...
0x1f8d  ldc.i4.2
0x1f8e  newarr   [mscorlib]System.Object
0x1f93  dup
0x1f94  ldc.i4.0
0x1f95  ldarg.0
0x1f96  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_PackagePath()
0x1f9b  stelem.ref
0x1f9c  dup
0x1f9d  ldc.i4.1
0x1f9e  ldloc.2
0x1f9f  stelem.ref
0x1fa0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1fa5  ldarg.0
0x1fa6  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_PackagePath()
0x1fab  ldloc.2
0x1fac  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::InstallProduct(string, string)
0x1fb1  leave    loc_2095
0x1fb6  stloc.3
0x1fb7  ldc.i4   0xBC2
0x1fbc  ldloc.3
0x1fbd  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x1fc2  beq.s    loc_1FDE
0x1fc4  ldc.i4   0x2000
0x1fc9  ldloc.3
0x1fca  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x1fcf  beq.s    loc_1FDE
0x1fd1  ldc.i4   0x669
0x1fd6  ldloc.3
0x1fd7  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x1fdc  bne.un.s loc_2007
0x1fde  ldstr    aErrorsuccessre// "ErrorSuccessRebootRequired"
0x1fe3  ldc.i4.0
0x1fe4  newarr   [mscorlib]System.Object
0x1fe9  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x1fee  ldc.i4.0
0x1fef  newarr   [mscorlib]System.Object
0x1ff4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x1ff9  ldarg.0
0x1ffa  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_InstallInfo()
0x1fff  ldc.i4.1
0x2000  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RebootRequired(bool)
0x2005  br.s     loc_2072
0x2007  ldc.i4   0x642
0x200c  ldloc.3
0x200d  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x2012  bne.un.s loc_2052
0x2014  ldstr    aUsercancel// "UserCancel"
0x2019  ldc.i4.0
0x201a  newarr   [mscorlib]System.Object
0x201f  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x2024  ldc.i4.0
0x2025  newarr   [mscorlib]System.Object
0x202a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x202f  ldarg.0
0x2030  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_InstallInfo()
0x2035  ldc.i4.1
0x2036  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_UserCancel(bool)
0x203b  ldstr    aUsercancel// "UserCancel"
0x2040  ldc.i4.0
0x2041  newarr   [mscorlib]System.Object
0x2046  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x204b  ldloc.3
0x204c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string, class [mscorlib]System.Exception)
0x2051  throw
0x2052  ldstr    aWin32exception_0// "Win32Exception: {0}"
0x2057  ldc.i4.1
0x2058  newarr   [mscorlib]System.Object
0x205d  dup
0x205e  ldc.i4.0
0x205f  ldloc.3
0x2060  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x2065  box      [mscorlib]System.Int32
0x206a  stelem.ref
0x206b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x2070  rethrow
0x2072  leave.s  loc_2095
0x2074  call     class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_Instance()
0x2079  ldloc.0
0x207a  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::set_ProgressEventSource(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource)
0x207f  ldloc.1
0x2080  brfalse.s loc_208E
0x2082  call     class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::get_Instance()
0x2087  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiExternalUIHandler::Unhook()
0x208c  ldc.i4.0
0x208d  stloc.1
0x208e  ldarg.0
0x208f  callvirt instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::AfterInstall()
0x2094  endfinally
0x2095  ret
```
