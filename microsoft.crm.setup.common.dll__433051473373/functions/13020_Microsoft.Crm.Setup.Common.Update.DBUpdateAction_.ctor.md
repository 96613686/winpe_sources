# Microsoft.Crm.Setup.Common.Update.DBUpdateAction::.ctor

- ea: `0x13020`
- end: `0x1304e`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateAction::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x13035`: `Installing DB update`

## pseudocode

```c

```

## disassembly

```asm
0x13020  ldarg.0
0x13021  ldarg.2
0x13022  ldarg.3
0x13023  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateActionWithErrors::.ctor(int32, int32)
0x13028  ldarg.0
0x13029  ldarg.1
0x1302a  stfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.Update.DBUpdateAction::progressEventSource
0x1302f  ldarg.0
0x13030  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x13035  ldstr    aInstallingDbUp// "Installing DB update"
0x1303a  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::set_ProgressMessage(string)
0x1303f  ldarg.0
0x13040  ldarg.2
0x13041  stfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateAction::progressStart
0x13046  ldarg.0
0x13047  ldarg.3
0x13048  stfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateAction::allocatedProgress
0x1304d  ret
```
