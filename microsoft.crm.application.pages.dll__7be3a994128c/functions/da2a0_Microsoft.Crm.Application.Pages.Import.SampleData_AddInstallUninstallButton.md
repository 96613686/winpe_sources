# Microsoft.Crm.Application.Pages.Import.SampleData::AddInstallUninstallButton

- ea: `0xda2a0`
- end: `0xda31c`
- name: `Microsoft.Crm.Application.Pages.Import.SampleData::AddInstallUninstallButton`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xda010`

## callees

- `0xda2a0`
- `0xda320`
- `0xda390`

## string_xrefs

- `0xda2ba`: `butUninstall`
- `0xda2bf`: `SampleData.SampleDataDialog.Button.Uninstall.Label`
- `0xda2c4`: `uninstall();`
- `0xda2da`: `butInstall`
- `0xda2df`: `SampleData.SampleDataDialog.Button.Install.Label`
- `0xda2e4`: `install();`

## pseudocode

```c

```

## disassembly

```asm
0xda2a0  ldarg.0
0xda2a1  ldfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_hideInstallOrUninstallButton
0xda2a6  brfalse.s loc_DA2A9
0xda2a8  ret
0xda2a9  ldarg.0
0xda2aa  ldfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataInstalled
0xda2af  brtrue.s loc_DA2BA
0xda2b1  ldarg.0
0xda2b2  ldfld    int32 Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataImportStatus
0xda2b7  ldc.i4.5
0xda2b8  bne.un.s loc_DA2DA
0xda2ba  ldstr    aButuninstall// "butUninstall"
0xda2bf  ldstr    aSampledataSamp_5// "SampleData.SampleDataDialog.Button.Unin"...
0xda2c4  ldstr    aUninstall// "uninstall();"
0xda2c9  ldarg.0
0xda2ca  call     instance bool Microsoft.Crm.Application.Pages.Import.SampleData::CanUninstall()
0xda2cf  ldc.i4.0
0xda2d0  ceq
0xda2d2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xda2d7  stloc.0
0xda2d8  br.s     loc_DA30E
0xda2da  ldstr    aButinstall// "butInstall"
0xda2df  ldstr    aSampledataSamp_6// "SampleData.SampleDataDialog.Button.Inst"...
0xda2e4  ldstr    aInstall// "install();"
0xda2e9  ldarg.0
0xda2ea  call     instance bool Microsoft.Crm.Application.Pages.Import.SampleData::CanInstall()
0xda2ef  brfalse.s loc_DA307
0xda2f1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xda2f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SampleDataImportId()
0xda2fb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda300  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda305  br.s     loc_DA308
0xda307  ldc.i4.1
0xda308  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xda30d  stloc.0
0xda30e  ldarg.0
0xda30f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xda314  ldloc.0
0xda315  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0xda31a  pop
0xda31b  ret
```
