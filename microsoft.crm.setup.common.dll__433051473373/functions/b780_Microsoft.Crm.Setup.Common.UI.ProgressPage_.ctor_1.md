# Microsoft.Crm.Setup.Common.UI.ProgressPage::.ctor_1

- ea: `0xb780`
- end: `0xb7dc`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::.ctor_1`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb740`
- `0xb750`

## callees

- `0xb780`
- `0xb7f0`
- `0xb8f0`
- `0xc530`

## string_xrefs

- `0xb7a4`: `Setup thread-routine provided to progress wizard`

## pseudocode

```c

```

## disassembly

```asm
0xb780  ldarg.0
0xb781  call     instance void Microsoft.Crm.Setup.Common.UI.SetupWizardPage::.ctor()
0xb786  ldarg.0
0xb787  call     instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::InitializeComponent()
0xb78c  ldarg.0
0xb78d  ldarg.1
0xb78e  stfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgress
0xb793  ldarg.0
0xb794  ldarg.2
0xb795  stfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgress
0xb79a  ldarg.3
0xb79b  brfalse.s loc_B7DB
0xb79d  ldarg.0
0xb79e  ldarg.3
0xb79f  call     instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::set_ProcessingMethod(class [mscorlib]System.Threading.ThreadStart value)
0xb7a4  ldstr    aSetupThreadRou// "Setup thread-routine provided to progre"...
0xb7a9  ldc.i4.0
0xb7aa  newarr   [mscorlib]System.Object
0xb7af  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xb7b4  ldarg.0
0xb7b5  ldarg.0
0xb7b6  ldftn    instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::ProcessingMethodWrapper()
0xb7bc  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xb7c1  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0xb7c6  stfld    class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.ProgressPage::_workerThread
0xb7cb  ldarg.0
0xb7cc  ldfld    class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.ProgressPage::_workerThread
0xb7d1  ldstr    aProgresspagePr// "ProgressPage ProcessingMethod"
0xb7d6  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xb7db  ret
```
