# Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::EnableComponentsInternal

- ea: `0x117e0`
- end: `0x11858`
- name: `Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::EnableComponentsInternal`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x117e0`
- `0x11860`
- `0x11870`
- `0x11900`

## string_xrefs

- `0x117e6`: `EnableComponentsInternal`
- `0x11847`: `EnableComponentsInternal`
- `0x1180f`: `-install {0} -logPath "{1}"`
- `0x11837`: `SystemComponentManager.ServerManagerCommand.ErrorEnablingSystemComponents`

## pseudocode

```c

```

## disassembly

```asm
0x117e0  ldarg.0
0x117e1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x117e6  ldstr    aEnablecomponen_0// "EnableComponentsInternal"
0x117eb  ldc.i4.0
0x117ec  newarr   [mscorlib]System.Object
0x117f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodEntry(class [mscorlib]System.Type, string, object[])
0x117f6  ldarg.1
0x117f7  call     T0x2B000009
0x117fc  brfalse.s loc_11841
0x117fe  ldstr    asc_265CA// " "
0x11803  ldarg.1
0x11804  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x11809  stloc.0
0x1180a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1180f  ldstr    aInstall0Logpat// "-install {0} -logPath \"{1}\""
0x11814  ldc.i4.2
0x11815  newarr   [mscorlib]System.Object
0x1181a  dup
0x1181b  ldc.i4.0
0x1181c  ldloc.0
0x1181d  stelem.ref
0x1181e  dup
0x1181f  ldc.i4.1
0x11820  ldarg.0
0x11821  call     instance string Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::get_ServerManagerCmdLogFilePath()
0x11826  stelem.ref
0x11827  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1182c  stloc.1
0x1182d  ldarg.0
0x1182e  ldloc.1
0x1182f  call     instance int32 Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::InvokeServerManager(string commandLineOptions)
0x11834  stloc.2
0x11835  ldarg.0
0x11836  ldloc.2
0x11837  ldstr    aSystemcomponen_0// "SystemComponentManager.ServerManagerCom"...
0x1183c  call     instance void Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ProcessExitCode(int32 exitCode, string errorContextResourceName)
0x11841  ldarg.0
0x11842  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11847  ldstr    aEnablecomponen_0// "EnableComponentsInternal"
0x1184c  ldc.i4.0
0x1184d  newarr   [mscorlib]System.Object
0x11852  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodExit(class [mscorlib]System.Type, string, object[])
0x11857  ret
```
