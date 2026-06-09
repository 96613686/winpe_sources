# Microsoft.Crm.Setup.Common.MUOptInaction::Do

- ea: `0x5d0`
- end: `0x65d`
- name: `Microsoft.Crm.Setup.Common.MUOptInaction::Do`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5d0`
- `0x120f0`
- `0x12160`

## string_xrefs

- `0x5d8`: `System is not currently opted in to Microsoft Update.`
- `0x5f0`: `InstallInfo.MUOptIn`
- `0x64c`: `System is already opted in to Microsoft Update.  Taking no action.`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.1
0x5d1  call     bool Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::IsSystemOptedIntoMicrosoftUpdate(class [mscorlib]System.Collections.IDictionary data)
0x5d6  brtrue.s loc_64C
0x5d8  ldstr    aSystemIsNotCur// "System is not currently opted in to Mic"...
0x5dd  ldc.i4.0
0x5de  newarr   [mscorlib]System.Object
0x5e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x5e8  ldarg.1
0x5e9  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x5ee  stloc.0
0x5ef  ldarg.1
0x5f0  ldstr    aInstallinfoMuo// "InstallInfo.MUOptIn"
0x5f5  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5fa  brfalse.s loc_63B
0x5fc  ldloc.0
0x5fd  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_MUOptIn()
0x602  brfalse.s loc_63B
0x604  ldarg.1
0x605  call     int64 Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::OptSystemIntoMicrosoftUpdate(class [mscorlib]System.Collections.IDictionary data)
0x60a  stloc.1
0x60b  ldloc.1
0x60c  brfalse.s loc_62A
0x60e  ldstr    aMuoptinactionD// "MUOptInAction did not succeed.  Error c"...
0x613  ldloc.1
0x614  box      [mscorlib]System.Int64
0x619  call     string [mscorlib]System.String::Concat(object, object)
0x61e  ldc.i4.0
0x61f  newarr   [mscorlib]System.Object
0x624  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x629  ret
0x62a  ldstr    aMuoptinactionS// "MUOptInAction succeeded"
0x62f  ldc.i4.0
0x630  newarr   [mscorlib]System.Object
0x635  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x63a  ret
0x63b  ldstr    aMuoptinWasNotS// "MUOptIn was not specified"
0x640  ldc.i4.0
0x641  newarr   [mscorlib]System.Object
0x646  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x64b  ret
0x64c  ldstr    aSystemIsAlread// "System is already opted in to Microsoft"...
0x651  ldc.i4.0
0x652  newarr   [mscorlib]System.Object
0x657  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x65c  ret
```
