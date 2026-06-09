# Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::ConfigurePage

- ea: `0x71720`
- end: `0x7181c`
- name: `Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::ConfigurePage`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x71720`

## string_xrefs

- `0x7177c`: `Microsoft.Crm.Tools.EmailAgent.SystemState.xml`
- `0x71792`: `EncryptionKey.xml`
- `0x71766`: `Microsoft.Crm.Tools.EmailAgent.xml`
- `0x71761`: `LOCID_ROUTER_EMAILAGENT_XML`
- `0x71777`: `LOCID_ROUTER_SYSTEMSTATE_XML`
- `0x7178d`: `LOCID_ROUTER_ENCRYPTION_XML`
- `0x717dc`: `LOCID_MIGRATE_START_ACCESS_KEY`
- `0x7180a`: `LOCID_MIGRATE_FINISH_ACCESS_KEY`

## pseudocode

```c

```

## disassembly

```asm
0x71720  ldc.i4.0
0x71721  stloc.2
0x71722  br.s     loc_71751
0x71724  ldarg.0
0x71725  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7172a  ldsfld   string[][] Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::resourceStrings
0x7172f  ldloc.2
0x71730  ldelem.ref
0x71731  ldc.i4.0
0x71732  ldelem.ref
0x71733  ldarg.0
0x71734  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x71739  ldsfld   string[][] Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::resourceStrings
0x7173e  ldloc.2
0x7173f  ldelem.ref
0x71740  ldc.i4.1
0x71741  ldelem.ref
0x71742  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x71747  ldc.i4.0
0x71748  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7174d  ldloc.2
0x7174e  ldc.i4.1
0x7174f  add
0x71750  stloc.2
0x71751  ldloc.2
0x71752  ldsfld   string[][] Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::resourceStrings
0x71757  ldlen
0x71758  conv.i4
0x71759  blt.s    loc_71724
0x7175b  ldarg.0
0x7175c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x71761  ldstr    aLocidRouterEma// "LOCID_ROUTER_EMAILAGENT_XML"
0x71766  ldstr    aMicrosoftCrmTo_0// "Microsoft.Crm.Tools.EmailAgent.xml"
0x7176b  ldc.i4.0
0x7176c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x71771  ldarg.0
0x71772  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x71777  ldstr    aLocidRouterSys// "LOCID_ROUTER_SYSTEMSTATE_XML"
0x7177c  ldstr    aMicrosoftCrmTo// "Microsoft.Crm.Tools.EmailAgent.SystemSt"...
0x71781  ldc.i4.0
0x71782  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x71787  ldarg.0
0x71788  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7178d  ldstr    aLocidRouterEnc// "LOCID_ROUTER_ENCRYPTION_XML"
0x71792  ldstr    aEncryptionkeyX// "EncryptionKey.xml"
0x71797  ldc.i4.0
0x71798  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7179d  ldarg.0
0x7179e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x717a3  ldstr    aMigrationwizar// "MigrationWizard.StartButton.Text"
0x717a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x717ad  stloc.0
0x717ae  ldarg.0
0x717af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x717b4  ldstr    aMigrationwizar_0// "MigrationWizard.FinishButton.Text"
0x717b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x717be  stloc.1
0x717bf  ldarg.0
0x717c0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x717c5  ldstr    aLocidMigrateSt// "LOCID_MIGRATE_START_BTN"
0x717ca  ldloc.0
0x717cb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x717d0  ldc.i4.0
0x717d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x717d6  ldarg.0
0x717d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x717dc  ldstr    aLocidMigrateSt_0// "LOCID_MIGRATE_START_ACCESS_KEY"
0x717e1  ldloc.0
0x717e2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x717e7  ldc.i4.0
0x717e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x717ed  ldarg.0
0x717ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x717f3  ldstr    aLocidMigrateFi// "LOCID_MIGRATE_FINISH_BTN"
0x717f8  ldloc.1
0x717f9  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x717fe  ldc.i4.0
0x717ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x71804  ldarg.0
0x71805  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7180a  ldstr    aLocidMigrateFi_0// "LOCID_MIGRATE_FINISH_ACCESS_KEY"
0x7180f  ldloc.1
0x71810  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x71815  ldc.i4.0
0x71816  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7181b  ret
```
