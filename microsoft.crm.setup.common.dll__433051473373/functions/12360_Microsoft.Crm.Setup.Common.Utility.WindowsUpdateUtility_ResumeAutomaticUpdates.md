# Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::ResumeAutomaticUpdates

- ea: `0x12360`
- end: `0x123d4`
- name: `Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::ResumeAutomaticUpdates`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x22c0`

## callees

- `0x12360`

## string_xrefs

- `0x12379`: `Resuming Automatic Updates`
- `0x12391`: `Not resuming automatic updates because configuration is AutomaticUpdatesNotificationLevel.`
- `0x123b6`: `Exception thrown on attempt to resume automatic updates:  `

## pseudocode

```c

```

## disassembly

```asm
0x12360  newobj   instance void [Interop.WUApiLib]WUApiLib.AutomaticUpdatesClass::.ctor()
0x12365  stloc.0
0x12366  ldloc.0
0x12367  callvirt instance class [Interop.WUApiLib]WUApiLib.IAutomaticUpdatesSettings [Interop.WUApiLib]WUApiLib.IAutomaticUpdates2::get_Settings()
0x1236c  callvirt instance valuetype [Interop.WUApiLib]WUApiLib.AutomaticUpdatesNotificationLevel [Interop.WUApiLib]WUApiLib.IAutomaticUpdatesSettings::get_NotificationLevel()
0x12371  stloc.1
0x12372  ldloc.1
0x12373  ldc.i4.1
0x12374  beq.s    loc_12391
0x12376  ldloc.1
0x12377  brfalse.s loc_12391
0x12379  ldstr    aResumingAutoma// "Resuming Automatic Updates"
0x1237e  ldc.i4.0
0x1237f  newarr   [mscorlib]System.Object
0x12384  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12389  ldloc.0
0x1238a  callvirt instance void [Interop.WUApiLib]WUApiLib.IAutomaticUpdates2::Resume()
0x1238f  br.s     loc_123B3
0x12391  ldstr    aNotResumingAut// "Not resuming automatic updates because "...
0x12396  ldloca.s 1
0x12398  constrained. [Interop.WUApiLib]WUApiLib.AutomaticUpdatesNotificationLevel
0x1239e  callvirt instance string [mscorlib]System.Object::ToString()
0x123a3  call     string [mscorlib]System.String::Concat(string, string)
0x123a8  ldc.i4.0
0x123a9  newarr   [mscorlib]System.Object
0x123ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x123b3  leave.s  loc_123D3
0x123b5  stloc.2
0x123b6  ldstr    aExceptionThrow_0// "Exception thrown on attempt to resume a"...
0x123bb  ldloc.2
0x123bc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x123c1  call     string [mscorlib]System.String::Concat(string, string)
0x123c6  ldc.i4.0
0x123c7  newarr   [mscorlib]System.Object
0x123cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x123d1  leave.s  loc_123D3
0x123d3  ret
```
