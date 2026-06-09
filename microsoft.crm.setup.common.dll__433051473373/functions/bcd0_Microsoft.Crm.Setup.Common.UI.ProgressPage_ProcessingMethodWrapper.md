# Microsoft.Crm.Setup.Common.UI.ProgressPage::ProcessingMethodWrapper

- ea: `0xbcd0`
- end: `0xbd38`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::ProcessingMethodWrapper`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb7e0`
- `0xb840`
- `0xbcd0`
- `0x10d00`

## string_xrefs

- `0xbce5`: `Exception caught in progress page execution thread: `

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  ldarg.0
0xbcd1  ldc.i4.0
0xbcd2  call     instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::set_WorkerThreadIsComplete(bool value)
0xbcd7  ldarg.0
0xbcd8  call     instance class [mscorlib]System.Threading.ThreadStart Microsoft.Crm.Setup.Common.UI.ProgressPage::get_ProcessingMethod()
0xbcdd  callvirt instance void [mscorlib]System.Threading.ThreadStart::Invoke()
0xbce2  leave.s  loc_BD37
0xbce4  stloc.0
0xbce5  ldstr    aExceptionCaugh// "Exception caught in progress page execu"...
0xbcea  ldloc.0
0xbceb  callvirt instance string [mscorlib]System.Object::ToString()
0xbcf0  call     string [mscorlib]System.String::Concat(string, string)
0xbcf5  ldc.i4.0
0xbcf6  newarr   [mscorlib]System.Object
0xbcfb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0xbd00  ldarg.0
0xbd01  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase Microsoft.Crm.Setup.Common.UI.WizardPage::get_Setup()
0xbd06  callvirt instance class [mscorlib]System.Exception [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::get_RunException()
0xbd0b  brtrue.s loc_BD19
0xbd0d  ldarg.0
0xbd0e  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase Microsoft.Crm.Setup.Common.UI.WizardPage::get_Setup()
0xbd13  ldloc.0
0xbd14  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::set_RunException(class [mscorlib]System.Exception)
0xbd19  leave.s  loc_BD37
0xbd1b  ldarg.0
0xbd1c  ldc.i4.1
0xbd1d  call     instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::set_WorkerThreadIsComplete(bool value)
0xbd22  ldc.i4.1
0xbd23  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0xbd28  stloc.1
0xbd29  ldarg.0
0xbd2a  ldfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgress
0xbd2f  ldarg.0
0xbd30  ldloc.1
0xbd31  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0xbd36  endfinally
0xbd37  ret
```
