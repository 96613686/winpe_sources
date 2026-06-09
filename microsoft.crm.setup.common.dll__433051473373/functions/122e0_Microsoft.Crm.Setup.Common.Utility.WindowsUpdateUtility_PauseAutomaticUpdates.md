# Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::PauseAutomaticUpdates

- ea: `0x122e0`
- end: `0x12359`
- name: `Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::PauseAutomaticUpdates`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2250`

## callees

- `0x122e0`

## string_xrefs

- `0x122fb`: `Pausing Automatic Updates`
- `0x12315`: `Not pausing automatic updates because configuration is AutomaticUpdatesNotificationLevel.`
- `0x1233a`: `Exception thrown on attempt to pause automatic updates:  `

## pseudocode

```c

```

## disassembly

```asm
0x122e0  ldc.i4.0
0x122e1  stloc.0
0x122e2  newobj   instance void [Interop.WUApiLib]WUApiLib.AutomaticUpdatesClass::.ctor()
0x122e7  stloc.1
0x122e8  ldloc.1
0x122e9  callvirt instance class [Interop.WUApiLib]WUApiLib.IAutomaticUpdatesSettings [Interop.WUApiLib]WUApiLib.IAutomaticUpdates2::get_Settings()
0x122ee  callvirt instance valuetype [Interop.WUApiLib]WUApiLib.AutomaticUpdatesNotificationLevel [Interop.WUApiLib]WUApiLib.IAutomaticUpdatesSettings::get_NotificationLevel()
0x122f3  stloc.2
0x122f4  ldloc.2
0x122f5  ldc.i4.1
0x122f6  beq.s    loc_12315
0x122f8  ldloc.2
0x122f9  brfalse.s loc_12315
0x122fb  ldstr    aPausingAutomat// "Pausing Automatic Updates"
0x12300  ldc.i4.0
0x12301  newarr   [mscorlib]System.Object
0x12306  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1230b  ldloc.1
0x1230c  callvirt instance void [Interop.WUApiLib]WUApiLib.IAutomaticUpdates2::Pause()
0x12311  ldc.i4.1
0x12312  stloc.0
0x12313  br.s     loc_12337
0x12315  ldstr    aNotPausingAuto// "Not pausing automatic updates because c"...
0x1231a  ldloca.s 2
0x1231c  constrained. [Interop.WUApiLib]WUApiLib.AutomaticUpdatesNotificationLevel
0x12322  callvirt instance string [mscorlib]System.Object::ToString()
0x12327  call     string [mscorlib]System.String::Concat(string, string)
0x1232c  ldc.i4.0
0x1232d  newarr   [mscorlib]System.Object
0x12332  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12337  leave.s  loc_12357
0x12339  stloc.3
0x1233a  ldstr    aExceptionThrow// "Exception thrown on attempt to pause au"...
0x1233f  ldloc.3
0x12340  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12345  call     string [mscorlib]System.String::Concat(string, string)
0x1234a  ldc.i4.0
0x1234b  newarr   [mscorlib]System.Object
0x12350  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12355  leave.s  loc_12357
0x12357  ldloc.0
0x12358  ret
```
