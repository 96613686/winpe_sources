# Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::LoadData

- ea: `0x1f90`
- end: `0x201b`
- name: `Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::LoadData`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e40`

## string_xrefs

- `0x1fac`: `ProfUserLicenseStorageAmountMB`
- `0x200a`: `D365UserLicenseStorageAmountMB`

## pseudocode

```c

```

## disassembly

```asm
0x1f90  ldarg.0
0x1f91  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1f96  ldstr    aProfuserlicens// "ProfUserLicenseStorageStep"
0x1f9b  ldc.i4.0
0x1f9c  callvirt T0x2B000013
0x1fa1  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageStep
0x1fa6  ldarg.0
0x1fa7  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1fac  ldstr    aProfuserlicens_0// "ProfUserLicenseStorageAmountMB"
0x1fb1  ldc.i4.0
0x1fb2  callvirt T0x2B000013
0x1fb7  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseStorageAmountInMb
0x1fbc  ldarg.0
0x1fbd  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1fc2  ldstr    aProfuserlicens_1// "ProfUserLicenseTestInstanceStep"
0x1fc7  ldc.i4.0
0x1fc8  callvirt T0x2B000013
0x1fcd  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_professionalUserLicenseTestInstanceStep
0x1fd2  ldarg.0
0x1fd3  ldc.i4.0
0x1fd4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1fd9  ldstr    aUserlicensemax// "UserLicenseMaxStorageToProvisionMB"
0x1fde  ldc.i4.0
0x1fdf  callvirt T0x2B000013
0x1fe4  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x1fe9  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_userLicenseMaxStorageToProvisionMB
0x1fee  ldarg.0
0x1fef  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x1ff4  ldstr    aD365userlicens// "D365UserLicenseStorageStep"
0x1ff9  ldc.i4.1
0x1ffa  callvirt T0x2B000013
0x1fff  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_d365UserLicenseStorageStep
0x2004  ldarg.0
0x2005  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x200a  ldstr    aD365userlicens_0// "D365UserLicenseStorageAmountMB"
0x200f  ldc.i4.1
0x2010  callvirt T0x2B000013
0x2015  stfld    int32 Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.UserLicenseToResourceMapper::_d365UserLicenseStorageAmountInMb
0x201a  ret
```
