# Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ProcessExitCode

- ea: `0x11900`
- end: `0x119ca`
- name: `Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ProcessExitCode`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11790`
- `0x117e0`

## callees

- `0xff0`
- `0x116c0`
- `0x11860`
- `0x11900`

## string_xrefs

- `0x1193b`: `Components successfully enabled, but reboot is required for completion`
- `0x11969`: `SystemComponentManager.ServerManagerCommand.AnotherInstanceInProgress`
- `0x11991`: `Error {0} reported by serverManagerCmd.  See "{1}" and http://technet.microsoft.com/en-us/library/cc733119.aspx for more information.`

## pseudocode

```c

```

## disassembly

```asm
0x11900  ldnull
0x11901  stloc.0
0x11902  ldarg.1
0x11903  ldc.i4   0x3EB
0x11908  bgt.s    loc_11917
0x1190a  ldarg.1
0x1190b  brfalse.s loc_11989
0x1190d  ldarg.1
0x1190e  ldc.i4   0x3EB
0x11913  beq.s    loc_11929
0x11915  br.s     loc_1197C
0x11917  ldarg.1
0x11918  ldc.i4   0x3EC
0x1191d  beq.s    loc_11959
0x1191f  ldarg.1
0x11920  ldc.i4   0xBC2
0x11925  beq.s    loc_1193B
0x11927  br.s     loc_1197C
0x11929  ldstr    aUtilityReports// "Utility reports no change required."
0x1192e  ldc.i4.0
0x1192f  newarr   [mscorlib]System.Object
0x11934  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x11939  br.s     loc_11989
0x1193b  ldstr    aComponentsSucc// "Components successfully enabled, but re"...
0x11940  ldc.i4.0
0x11941  newarr   [mscorlib]System.Object
0x11946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x1194b  ldarg.0
0x1194c  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_InstallInfo()
0x11951  ldc.i4.1
0x11952  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RebootRequired(bool)
0x11957  br.s     loc_11989
0x11959  ldstr    aAnotherInstanc// "Another instance of ServerManagerCmd or"...
0x1195e  ldc.i4.0
0x1195f  newarr   [mscorlib]System.Object
0x11964  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x11969  ldstr    aSystemcomponen_1// "SystemComponentManager.ServerManagerCom"...
0x1196e  ldc.i4.0
0x1196f  newarr   [mscorlib]System.Object
0x11974  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x11979  stloc.0
0x1197a  br.s     loc_11989
0x1197c  ldarga.s 1
0x1197e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x11983  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11988  stloc.0
0x11989  ldloc.0
0x1198a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1198f  brtrue.s loc_119C9
0x11991  ldstr    aError0Reported// "Error {0} reported by serverManagerCmd."...
0x11996  ldc.i4.2
0x11997  newarr   [mscorlib]System.Object
0x1199c  dup
0x1199d  ldc.i4.0
0x1199e  ldarg.1
0x1199f  box      [mscorlib]System.Int32
0x119a4  stelem.ref
0x119a5  dup
0x119a6  ldc.i4.1
0x119a7  ldarg.0
0x119a8  call     instance string Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::get_ServerManagerCmdLogFilePath()
0x119ad  stelem.ref
0x119ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x119b3  ldarg.2
0x119b4  ldc.i4.1
0x119b5  newarr   [mscorlib]System.Object
0x119ba  dup
0x119bb  ldc.i4.0
0x119bc  ldloc.0
0x119bd  stelem.ref
0x119be  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x119c3  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x119c8  throw
0x119c9  ret
```
