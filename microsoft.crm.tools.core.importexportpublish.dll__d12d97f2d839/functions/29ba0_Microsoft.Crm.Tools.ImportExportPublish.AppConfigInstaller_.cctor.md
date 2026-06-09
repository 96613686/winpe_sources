# Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::.cctor

- ea: `0x29ba0`
- end: `0x29c4b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::.cctor`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x29bd2`: `appconfigidunique`
- `0x29bdc`: `appconfigid`
- `0x29bbe`: `appconfiginstanceid`
- `0x29bc8`: `appconfigmasterid`

## pseudocode

```c

```

## disassembly

```asm
0x29ba0  ldstr    aBcb82bb91ae942// "BCB82BB9-1AE9-424A-9207-BDCB35EC0A25"
0x29ba5  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::PARKING_SOLUTION_ID_KEY
0x29baa  ldstr    aF84308e554484b// "F84308E5-5448-4B4E-A67E-C38DA71F20E3"
0x29baf  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::CREATE_PARKING_SOLUTION_KEY
0x29bb4  ldstr    aValue// "value"
0x29bb9  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_VALUE
0x29bbe  ldstr    aAppconfiginsta_2// "appconfiginstanceid"
0x29bc3  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_APP_CONFIG_INSTANCE_ID
0x29bc8  ldstr    aAppconfigmaste// "appconfigmasterid"
0x29bcd  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_APP_CONFIG_MASTER_ID
0x29bd2  ldstr    aAppconfigiduni// "appconfigidunique"
0x29bd7  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_APP_CONFIG_ID_UNIQUE
0x29bdc  ldstr    aAppconfigid// "appconfigid"
0x29be1  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_APP_CONFIG_ID
0x29be6  ldstr    aAppmoduleid// "appmoduleid"
0x29beb  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_APP_MODULE_ID
0x29bf0  ldstr    aUniquename// "uniquename"
0x29bf5  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_UNIQUE_NAME
0x29bfa  ldstr    aName// "name"
0x29bff  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_NAME
0x29c04  ldstr    aDescription// "description"
0x29c09  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_DESCRIPTION
0x29c0e  ldstr    aFriendlyname_0// "friendlyname"
0x29c13  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_FRIENDLY_NAME
0x29c18  ldstr    aPublisherid_0// "publisherid"
0x29c1d  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_PUBLISHER_ID
0x29c22  ldstr    aIsmanaged// "ismanaged"
0x29c27  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::AT_IS_MANAGED
0x29c2c  ldstr    aBackingSolutio// "Backing_Solution_Display_Name_Suffix"
0x29c31  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::PARKING_SOLUTION_NAME_SUFFIX_KEY
0x29c36  ldstr    aBackingSolutio_0// "Backing_Solution_Schema_Name_Suffix"
0x29c3b  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::PARKING_SOLUTION_UNIQUE_NAME_SUFFIX_KEY
0x29c40  ldstr    aBackingSolutio_1// "Backing_Solution_Description"
0x29c45  stsfld   string Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::PARKING_SOLUTION_DESCRIPTION_KEY
0x29c4a  ret
```
