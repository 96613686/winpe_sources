# Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_NextClicked

- ea: `0x84c0`
- end: `0x85a1`
- name: `Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_NextClicked`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x680`
- `0x700`
- `0xff0`
- `0x10c0`
- `0x2dc0`
- `0x35e0`
- `0x84c0`
- `0xb1d0`
- `0xb1e0`
- `0xb1f0`
- `0xfbc0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x84c0  ldarg.0
0x84c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x84c6  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x84cb  callvirt instance string [mscorlib]System.String::Trim()
0x84d0  stloc.0
0x84d1  newobj   instance void Microsoft.Crm.Setup.Common.Analyzer::.ctor()
0x84d6  dup
0x84d7  ldloc.0
0x84d8  newobj   instance void Microsoft.Crm.Setup.Common.TargetFolderValidator::.ctor(string targetFolder)
0x84dd  callvirt instance void Microsoft.Crm.Setup.Common.Analyzer::RegisterValidator(class Microsoft.Crm.Setup.Common.Validator validator)
0x84e2  newobj   instance void Microsoft.Crm.Setup.Common.ClientVersionHistory::.ctor()
0x84e7  ldc.i4.1
0x84e8  ldc.i4.2
0x84e9  ldc.i4.0
0x84ea  ldc.i4.0
0x84eb  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x84f0  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.VersionHistory::GetVersionComponentCode(class [mscorlib]System.Version)
0x84f5  stloc.1
0x84f6  dup
0x84f7  ldloc.1
0x84f8  ldloc.0
0x84f9  newobj   instance void Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::.ctor(valuetype [mscorlib]System.Guid peerVersionComponentCode, string targetFolder)
0x84fe  callvirt instance void Microsoft.Crm.Setup.Common.Analyzer::RegisterValidator(class Microsoft.Crm.Setup.Common.Validator validator)
0x8503  ldarg.0
0x8504  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8509  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x850e  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.AnalyzerBase::Analyze(class [mscorlib]System.Collections.IDictionary)
0x8513  brtrue.s loc_851D
0x8515  ldarg.2
0x8516  ldc.i4.1
0x8517  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x851c  ret
0x851d  ldarg.0
0x851e  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x8523  ldloc.0
0x8524  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path(string value)
0x8529  ldc.i4.m1
0x852a  conv.i8
0x852b  ldarg.0
0x852c  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x8531  callvirt instance int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::get_SpaceAvailable()
0x8536  bne.un.s loc_854E
0x8538  ldstr    aErrorDiskspace// "Error.DiskSpace.Exception"
0x853d  ldc.i4.0
0x853e  newarr   [mscorlib]System.Object
0x8543  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x8548  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x854d  throw
0x854e  ldarg.0
0x854f  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x8554  callvirt instance int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::get_SpaceAvailable()
0x8559  ldarg.0
0x855a  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x855f  callvirt instance int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::get_SpaceRequired()
0x8564  bge.s    loc_858A
0x8566  ldstr    aErrorDiskspace_0// "Error.DiskSpace.NotEnough"
0x856b  ldc.i4.1
0x856c  newarr   [mscorlib]System.Object
0x8571  dup
0x8572  ldc.i4.0
0x8573  ldloc.0
0x8574  stelem.ref
0x8575  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x857a  ldc.i4.s 0x30
0x857c  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::RequestInput(object, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageType)
0x8581  pop
0x8582  ldarg.2
0x8583  ldc.i4.1
0x8584  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x8589  ret
0x858a  ldarg.0
0x858b  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8590  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x8595  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x859a  ldloc.0
0x859b  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_TargetFolder(string)
0x85a0  ret
```
