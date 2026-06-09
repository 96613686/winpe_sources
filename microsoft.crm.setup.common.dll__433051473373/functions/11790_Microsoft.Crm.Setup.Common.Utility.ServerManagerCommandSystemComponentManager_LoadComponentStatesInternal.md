# Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::LoadComponentStatesInternal

- ea: `0x11790`
- end: `0x117db`
- name: `Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::LoadComponentStatesInternal`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x11750`
- `0x11860`
- `0x11870`
- `0x11900`
- `0x119d0`

## string_xrefs

- `0x11791`: `ServerManagerQuery.xml`
- `0x117a1`: `-query "{0}" -logPath "{1}"`
- `0x117c9`: `SystemComponentManager.ServerManagerCommand.ErrorQueryingComponentStates`

## pseudocode

```c

```

## disassembly

```asm
0x11790  ldarg.0
0x11791  ldstr    aServermanagerq// "ServerManagerQuery.xml"
0x11796  call     instance string Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::ConstructSupportFilePath(string fileName)
0x1179b  stloc.0
0x1179c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x117a1  ldstr    aQuery0Logpath1// "-query \"{0}\" -logPath \"{1}\""
0x117a6  ldc.i4.2
0x117a7  newarr   [mscorlib]System.Object
0x117ac  dup
0x117ad  ldc.i4.0
0x117ae  ldloc.0
0x117af  stelem.ref
0x117b0  dup
0x117b1  ldc.i4.1
0x117b2  ldarg.0
0x117b3  call     instance string Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::get_ServerManagerCmdLogFilePath()
0x117b8  stelem.ref
0x117b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x117be  stloc.1
0x117bf  ldarg.0
0x117c0  ldloc.1
0x117c1  call     instance int32 Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::InvokeServerManager(string commandLineOptions)
0x117c6  stloc.2
0x117c7  ldarg.0
0x117c8  ldloc.2
0x117c9  ldstr    aSystemcomponen// "SystemComponentManager.ServerManagerCom"...
0x117ce  call     instance void Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ProcessExitCode(int32 exitCode, string errorContextResourceName)
0x117d3  ldarg.0
0x117d4  ldloc.0
0x117d5  call     instance void Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ParseQueryFile(string queryResultFilePath)
0x117da  ret
```
