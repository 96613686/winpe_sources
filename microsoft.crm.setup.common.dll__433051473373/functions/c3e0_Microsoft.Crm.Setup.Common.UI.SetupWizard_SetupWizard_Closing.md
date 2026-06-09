# Microsoft.Crm.Setup.Common.UI.SetupWizard::SetupWizard_Closing

- ea: `0xc3e0`
- end: `0xc4b4`
- name: `Microsoft.Crm.Setup.Common.UI.SetupWizard::SetupWizard_Closing`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xff0`
- `0xc3e0`
- `0xfba0`
- `0xfbb0`
- `0xfbc0`
- `0xfd30`

## string_xrefs

- `0xc408`: `ClientConfigWizard`
- `0xc414`: `ClientConfigurationCancelConfirmationMessage`

## pseudocode

```c

```

## disassembly

```asm
0xc3e0  ldarg.0
0xc3e1  call     instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0xc3e6  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xc3eb  stloc.0
0xc3ec  ldarg.0
0xc3ed  call     instance bool Microsoft.Crm.Setup.Common.UI.Wizard::get_RequiresClosingConfirmation()
0xc3f2  brfalse  loc_C483
0xc3f7  ldsfld   string [mscorlib]System.String::Empty
0xc3fc  stloc.1
0xc3fd  ldarg.1
0xc3fe  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc403  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xc408  ldstr    aClientconfigwi// "ClientConfigWizard"
0xc40d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc412  brfalse.s loc_C427
0xc414  ldstr    aClientconfigur// "ClientConfigurationCancelConfirmationMe"...
0xc419  ldc.i4.0
0xc41a  newarr   [mscorlib]System.Object
0xc41f  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xc424  stloc.1
0xc425  br.s     loc_C438
0xc427  ldstr    aSetupcancelcon// "SetupCancelConfirmationMessage"
0xc42c  ldc.i4.0
0xc42d  newarr   [mscorlib]System.Object
0xc432  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xc437  stloc.1
0xc438  ldloc.1
0xc439  ldc.i4.s 0x20
0xc43b  ldc.i4.4
0xc43c  ldc.i4   0x100
0xc441  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::RequestInput(object, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageType, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputOptions, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputDefaultOption)
0xc446  stloc.2
0xc447  ldarg.2
0xc448  ldc.i4.6
0xc449  ldloc.2
0xc44a  ceq
0xc44c  ldc.i4.0
0xc44d  ceq
0xc44f  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0xc454  ldarg.2
0xc455  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xc45a  brfalse.s loc_C463
0xc45c  ldarg.0
0xc45d  ldc.i4.1
0xc45e  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_WizardClose(valuetype WizardCloseType value)
0xc463  ldarg.2
0xc464  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xc469  brtrue.s loc_C483
0xc46b  ldloc.0
0xc46c  ldc.i4.0
0xc46d  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RebootRequired(bool)
0xc472  ldarg.0
0xc473  call     instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0xc478  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IpcInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xc47d  ldc.i4.m1
0xc47e  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IpcInfo::set_ExitType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExitType)
0xc483  ldarg.2
0xc484  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xc489  brtrue.s loc_C4B3
0xc48b  ldarg.0
0xc48c  call     instance valuetype WizardCloseType Microsoft.Crm.Setup.Common.UI.Wizard::get_WizardClose()
0xc491  brtrue.s loc_C4B3
0xc493  ldloc.0
0xc494  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_Setup()
0xc499  ldstr    aUsercancel// "UserCancel"
0xc49e  ldc.i4.0
0xc49f  newarr   [mscorlib]System.Object
0xc4a4  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xc4a9  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0xc4ae  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::set_RunException(class [mscorlib]System.Exception)
0xc4b3  ret
```
