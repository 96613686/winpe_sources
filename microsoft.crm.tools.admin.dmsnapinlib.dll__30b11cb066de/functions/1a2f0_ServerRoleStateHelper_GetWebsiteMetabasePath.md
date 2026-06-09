# ServerRoleStateHelper::GetWebsiteMetabasePath

- ea: `0x1a2f0`
- end: `0x1a3b2`
- name: `ServerRoleStateHelper::GetWebsiteMetabasePath`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a250`
- `0x1a2a0`

## callees

- `0x1a2f0`

## string_xrefs

- `0x1a320`: `Error during the access of the Registry on the remote machine ({0})`
- `0x1a367`: `Error during the access of the Registry on the remote machine ({0}). Exception: {1}`
- `0x1a389`: `Cannot open the key ({0}) in the Registry at this location ({1}) on this remote machine ({2})`

## pseudocode

```c

```

## disassembly

```asm
0x1a2f0  ldnull
0x1a2f1  stloc.0
0x1a2f2  ldc.i4   0x80000002
0x1a2f7  ldarg.0
0x1a2f8  call     class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenRemoteBaseKey(valuetype [mscorlib]Microsoft.Win32.RegistryHive, string)
0x1a2fd  stloc.1
0x1a2fe  ldloc.1
0x1a2ff  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MSCRM"
0x1a304  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1a309  stloc.2
0x1a30a  ldloc.2
0x1a30b  brfalse.s loc_1A320
0x1a30d  ldloc.2
0x1a30e  ldstr    aWebsite// "website"
0x1a313  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1a318  castclass [mscorlib]System.String
0x1a31d  stloc.0
0x1a31e  br.s     loc_1A334
0x1a320  ldstr    aErrorDuringThe_1// "Error during the access of the Registry"...
0x1a325  ldc.i4.1
0x1a326  newarr   [mscorlib]System.Object
0x1a32b  dup
0x1a32c  ldc.i4.0
0x1a32d  ldarg.0
0x1a32e  stelem.ref
0x1a32f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1a334  leave.s  loc_1A340
0x1a336  ldloc.2
0x1a337  brfalse.s loc_1A33F
0x1a339  ldloc.2
0x1a33a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a33f  endfinally
0x1a340  leave.s  loc_1A34C
0x1a342  ldloc.1
0x1a343  brfalse.s loc_1A34B
0x1a345  ldloc.1
0x1a346  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a34b  endfinally
0x1a34c  leave.s  loc_1A386
0x1a34e  stloc.3
0x1a34f  ldloc.3
0x1a350  isinst   [mscorlib]System.UnauthorizedAccessException
0x1a355  brtrue.s loc_1A367
0x1a357  ldloc.3
0x1a358  isinst   [mscorlib]System.Security.SecurityException
0x1a35d  brtrue.s loc_1A367
0x1a35f  ldloc.3
0x1a360  isinst   [mscorlib]System.IO.IOException
0x1a365  brfalse.s loc_1A384
0x1a367  ldstr    aErrorDuringThe_2// "Error during the access of the Registry"...
0x1a36c  ldc.i4.2
0x1a36d  newarr   [mscorlib]System.Object
0x1a372  dup
0x1a373  ldc.i4.0
0x1a374  ldarg.0
0x1a375  stelem.ref
0x1a376  dup
0x1a377  ldc.i4.1
0x1a378  ldloc.3
0x1a379  stelem.ref
0x1a37a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1a37f  ldnull
0x1a380  stloc.s  4
0x1a382  leave.s  loc_1A3AF
0x1a384  rethrow
0x1a386  ldloc.0
0x1a387  brtrue.s loc_1A3AD
0x1a389  ldstr    aCannotOpenTheK// "Cannot open the key ({0}) in the Regist"...
0x1a38e  ldc.i4.3
0x1a38f  newarr   [mscorlib]System.Object
0x1a394  dup
0x1a395  ldc.i4.0
0x1a396  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MSCRM"
0x1a39b  stelem.ref
0x1a39c  dup
0x1a39d  ldc.i4.1
0x1a39e  ldstr    aWebsite// "website"
0x1a3a3  stelem.ref
0x1a3a4  dup
0x1a3a5  ldc.i4.2
0x1a3a6  ldarg.0
0x1a3a7  stelem.ref
0x1a3a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1a3ad  ldloc.0
0x1a3ae  ret
0x1a3af  ldloc.s  4
0x1a3b1  ret
```
