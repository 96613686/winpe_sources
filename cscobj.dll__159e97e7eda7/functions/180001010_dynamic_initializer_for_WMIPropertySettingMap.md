# _dynamic_initializer_for__WMIPropertySettingMap__

- ea: `0x180001010`
- end: `0x180001a1c`
- name: `_dynamic_initializer_for__WMIPropertySettingMap__`
- size: `2572`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bb7c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180001020`
- `OLEAUT32!__imp_VariantInit` at `0x180001094`
- `OLEAUT32!__imp_VariantInit` at `0x18000110b`
- `OLEAUT32!__imp_VariantInit` at `0x18000117f`
- `OLEAUT32!__imp_VariantInit` at `0x1800011f3`
- `OLEAUT32!__imp_VariantInit` at `0x180001267`
- `OLEAUT32!__imp_VariantInit` at `0x1800012db`
- `OLEAUT32!__imp_VariantInit` at `0x18000134f`
- `OLEAUT32!__imp_VariantInit` at `0x1800013bc`
- `OLEAUT32!__imp_VariantInit` at `0x180001430`
- `OLEAUT32!__imp_VariantInit` at `0x1800014a4`
- `OLEAUT32!__imp_VariantInit` at `0x18000151b`
- `OLEAUT32!__imp_VariantInit` at `0x18000158f`
- `OLEAUT32!__imp_VariantInit` at `0x180001606`
- `OLEAUT32!__imp_VariantInit` at `0x18000167d`
- `OLEAUT32!__imp_VariantInit` at `0x1800016f1`
- `OLEAUT32!__imp_VariantInit` at `0x180001765`
- `OLEAUT32!__imp_VariantInit` at `0x1800017d9`
- `OLEAUT32!__imp_VariantInit` at `0x18000184d`
- `OLEAUT32!__imp_VariantInit` at `0x1800018c1`
- `OLEAUT32!__imp_VariantInit` at `0x180001935`
- `OLEAUT32!__imp_VariantInit` at `0x1800019a9`
- `OLEAUT32!__imp_VariantInit` at `0x180001020`
- `OLEAUT32!__imp_VariantInit` at `0x180001094`
- `OLEAUT32!__imp_VariantInit` at `0x18000110b`
- `OLEAUT32!__imp_VariantInit` at `0x18000117f`
- `OLEAUT32!__imp_VariantInit` at `0x1800011f3`
- `OLEAUT32!__imp_VariantInit` at `0x180001267`
- `OLEAUT32!__imp_VariantInit` at `0x1800012db`
- `OLEAUT32!__imp_VariantInit` at `0x18000134f`
- `OLEAUT32!__imp_VariantInit` at `0x1800013bc`
- `OLEAUT32!__imp_VariantInit` at `0x180001430`
- `OLEAUT32!__imp_VariantInit` at `0x1800014a4`
- `OLEAUT32!__imp_VariantInit` at `0x18000151b`
- `OLEAUT32!__imp_VariantInit` at `0x18000158f`
- `OLEAUT32!__imp_VariantInit` at `0x180001606`
- `OLEAUT32!__imp_VariantInit` at `0x18000167d`
- `OLEAUT32!__imp_VariantInit` at `0x1800016f1`
- `OLEAUT32!__imp_VariantInit` at `0x180001765`
- `OLEAUT32!__imp_VariantInit` at `0x1800017d9`
- `OLEAUT32!__imp_VariantInit` at `0x18000184d`
- `OLEAUT32!__imp_VariantInit` at `0x1800018c1`
- `OLEAUT32!__imp_VariantInit` at `0x180001935`
- `OLEAUT32!__imp_VariantInit` at `0x1800019a9`

## string_xrefs

- `0x1800010b2`: `WorkOfflineButtonRemoved`
- `0x18000112d`: `MakeAvailableOfflineButtonRemoved`
- `0x1800011a1`: `OfflineFilesCacheEncrypted`
- `0x180001521`: `CacheQuotaEnabled`
- `0x18000120e`: `SlowLinkEnabled`
- `0x180001185`: `EncryptCache`
- `0x1800018c7`: `CacheQuotaLimit`
- `0x180001355`: `SlowLinkParams`
- `0x18000193b`: `CacheQuotaLimitUnpinned`
- `0x180001957`: `AutoCacheSizeInMB`
- `0x1800011f9`: `SlowLinkEnabled`

## pseudocode

```c
int dynamic_initializer_for__WMIPropertySettingMap__()
{
  VariantInit(&pvarg);
  qword_1800464B0 = (__int64)L"AssignedOfflineFiles";
  qword_1800464D8 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles\\AssignedOfflineFolders";
  qword_1800464C8 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache\\AssignedOfflineFolders";
  qword_180046500 = 0;
  WMIPropertySettingMap = 0;
  word_1800464A8 = 0;
  dword_1800464B8 = 0;
  dword_1800464C0 = 0;
  word_1800464BC = 8204;
  qword_1800464E0 = 0;
  qword_1800464D0 = 0;
  VariantInit(&stru_180046550);
  qword_180046568 = 0;
  qword_180046508 = (__int64)L"WorkOfflineDisabled";
  word_180046510 = 0;
  qword_180046518 = (__int64)L"WorkOfflineButtonRemoved";
  qword_180046540 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046530 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046520 = 0;
  dword_180046528 = 0;
  word_180046524 = 11;
  qword_180046548 = 0;
  qword_180046538 = 0;
  VariantInit(&stru_1800465B8);
  qword_1800465D0 = 0;
  qword_180046570 = (__int64)L"NoMakeAvailableOffline";
  word_180046578 = 0;
  qword_180046580 = (__int64)L"MakeAvailableOfflineButtonRemoved";
  qword_1800465A8 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046598 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046588 = 0;
  dword_180046590 = 0;
  word_18004658C = 11;
  qword_1800465B0 = 0;
  qword_1800465A0 = 0;
  VariantInit(&stru_180046620);
  qword_180046638 = 0;
  qword_1800465D8 = (__int64)L"EncryptCache";
  word_1800465E0 = 0;
  qword_1800465E8 = (__int64)L"OfflineFilesCacheEncrypted";
  qword_180046610 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046600 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_1800465F0 = 0;
  dword_1800465F8 = 0;
  word_1800465F4 = 11;
  qword_180046618 = 0;
  qword_180046608 = 0;
  VariantInit(&stru_180046688);
  qword_1800466A0 = 0;
  qword_180046640 = (__int64)L"SlowLinkEnabled";
  qword_180046650 = (__int64)L"SlowLinkEnabled";
  word_180046648 = 0;
  dword_180046658 = 0;
  dword_180046660 = 0;
  word_18004665C = 11;
  qword_180046678 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046668 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  qword_180046680 = 0;
  qword_180046670 = 0;
  VariantInit(&stru_1800466F0);
  qword_180046708 = 0;
  qword_1800466A8 = (__int64)L"SyncEnabledForCostedNetwork";
  word_1800466B0 = 0;
  qword_1800466B8 = (__int64)L"SyncOnCostedNetworkEnabled";
  qword_1800466E0 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_1800466D0 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_1800466C0 = 0;
  dword_1800466C8 = 0;
  word_1800466C4 = 11;
  qword_1800466E8 = 0;
  qword_1800466D8 = 0;
  VariantInit(&stru_180046758);
  qword_180046770 = 0;
  qword_180046710 = (__int64)L"Enabled";
  qword_180046720 = (__int64)L"Enabled";
  qword_180046748 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046750 = (__int64)L"Enabled";
  qword_180046740 = (__int64)L"Enabled";
  qword_180046738 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  word_180046718 = 0;
  dword_180046728 = 0;
  dword_180046730 = 0;
  word_18004672C = 11;
  VariantInit(&stru_1800467C0);
  qword_1800467D8 = 0;
  qword_180046788 = (__int64)L"SlowLinkParams";
  qword_1800467B0 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles\\SlowLinkParams";
  qword_1800467A0 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache\\SlowLinkParams";
  qword_180046778 = 0;
  word_180046780 = 0;
  dword_180046790 = 0;
  dword_180046798 = 0;
  word_180046794 = 8204;
  qword_1800467B8 = 0;
  qword_1800467A8 = 0;
  VariantInit(&stru_180046828);
  qword_180046840 = 0;
  qword_1800467E0 = (__int64)L"BackgroundSyncEnabled";
  word_1800467E8 = 0;
  qword_1800467F0 = (__int64)L"BackgroundSyncEnabled";
  qword_180046818 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046808 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_1800467F8 = 0;
  dword_180046800 = 0;
  word_1800467FC = 11;
  qword_180046820 = 0;
  qword_180046810 = 0;
  VariantInit(&stru_180046890);
  qword_1800468A8 = 0;
  qword_180046848 = (__int64)L"EconomicalAdminPinning";
  qword_180046858 = (__int64)L"EconomicalAdminPinningEnabled";
  word_180046850 = 0;
  qword_180046880 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046870 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046860 = 0;
  dword_180046868 = 0;
  word_180046864 = 11;
  qword_180046888 = 0;
  qword_180046878 = 0;
  VariantInit(&stru_1800468F8);
  qword_180046910 = 0;
  qword_1800468B0 = (__int64)L"ExcludedFileTypes";
  word_1800468B8 = 0;
  qword_1800468C0 = (__int64)L"ExcludedFileTypes";
  word_1800468CC = 8;
  qword_1800468E8 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_1800468D8 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_1800468C8 = 0;
  dword_1800468D0 = 0;
  qword_1800468F0 = 0;
  qword_1800468E0 = 0;
  VariantInit(&stru_180046960);
  qword_180046978 = 0;
  qword_180046918 = (__int64)L"CacheQuotaEnabled";
  word_180046920 = 0;
  qword_180046928 = (__int64)L"DiskSpaceLimitEnabled";
  qword_180046950 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046940 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046930 = 0;
  dword_180046938 = 0;
  word_180046934 = 11;
  qword_180046958 = 0;
  qword_180046948 = 0;
  VariantInit(&stru_1800469C8);
  qword_1800469E0 = 0;
  qword_180046980 = (__int64)L"OnlineCachingLatencyThreshold";
  word_180046988 = 0;
  qword_180046990 = (__int64)L"TransparentCachingLatencyThreshold";
  qword_1800469B8 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_1800469A8 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046998 = 0;
  dword_1800469A0 = 0;
  word_18004699C = 3;
  qword_1800469C0 = 0;
  qword_1800469B0 = 0;
  VariantInit(&stru_180046A30);
  qword_180046A48 = 0;
  qword_1800469E8 = (__int64)L"BackgroundSyncPeriodMin";
  word_1800469F0 = 0;
  qword_1800469F8 = (__int64)L"SyncInterval";
  qword_180046A20 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046A10 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046A00 = 0;
  dword_180046A08 = 0;
  word_180046A04 = 18;
  qword_180046A28 = 0;
  qword_180046A18 = 0;
  VariantInit(&stru_180046A98);
  qword_180046AB0 = 0;
  qword_180046A50 = (__int64)L"BackgroundSyncMaxStartMin";
  word_180046A58 = 0;
  qword_180046A60 = (__int64)L"SyncVariance";
  qword_180046A88 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046A78 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046A68 = 0;
  dword_180046A70 = 0;
  word_180046A6C = 18;
  qword_180046A90 = 0;
  qword_180046A80 = 0;
  VariantInit(&stru_180046B00);
  qword_180046B18 = 0;
  qword_180046AB8 = (__int64)L"BackgroundSyncIgnoreBlockOutAfterMin";
  word_180046AC0 = 0;
  qword_180046AC8 = (__int64)L"MaxTimeBetweenSyncs";
  qword_180046AF0 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046AE0 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046AD0 = 0;
  dword_180046AD8 = 0;
  word_180046AD4 = 18;
  qword_180046AF8 = 0;
  qword_180046AE8 = 0;
  VariantInit(&stru_180046B68);
  qword_180046B80 = 0;
  qword_180046B20 = (__int64)L"BackgroundSyncBlockOutStartTime";
  word_180046B28 = 0;
  qword_180046B30 = (__int64)L"BlockOutStartTimeHoursMinutes";
  qword_180046B58 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046B48 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046B38 = 0;
  dword_180046B40 = 0;
  word_180046B3C = 18;
  qword_180046B60 = 0;
  qword_180046B50 = 0;
  VariantInit(&stru_180046BD0);
  qword_180046BE8 = 0;
  qword_180046B88 = (__int64)L"BackgroundSyncBlockOutDurationMin";
  word_180046B90 = 0;
  qword_180046B98 = (__int64)L"BlockOutDurationMin";
  qword_180046BC0 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046BB0 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046BA0 = 0;
  dword_180046BA8 = 0;
  word_180046BA4 = 18;
  qword_180046BC8 = 0;
  qword_180046BB8 = 0;
  VariantInit(&stru_180046C38);
  qword_180046C50 = 0;
  qword_180046BF0 = (__int64)L"BackgroundSyncEnabledForForcedOffline";
  qword_180046C00 = (__int64)L"BackgroundSyncWorkOfflineSharesEnabled";
  qword_180046C28 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  word_180046BF8 = 0;
  dword_180046C08 = 0;
  dword_180046C10 = 0;
  word_180046C0C = 11;
  qword_180046C30 = 0;
  qword_180046C18 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  qword_180046C20 = 0;
  VariantInit(&stru_180046CA0);
  qword_180046CB8 = 0;
  qword_180046C58 = (__int64)L"CacheQuotaLimit";
  word_180046C60 = 0;
  qword_180046C68 = (__int64)L"TotalSizeInMB";
  qword_180046C90 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046C80 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046C70 = 0;
  dword_180046C78 = 0;
  word_180046C74 = 3;
  qword_180046C98 = 0;
  qword_180046C88 = 0;
  VariantInit(&stru_180046D08);
  qword_180046D20 = 0;
  qword_180046CC0 = (__int64)L"CacheQuotaLimitUnpinned";
  word_180046CC8 = 0;
  qword_180046CD0 = (__int64)L"AutoCacheSizeInMB";
  qword_180046CF8 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046CE8 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  dword_180046CD8 = 0;
  dword_180046CE0 = 0;
  word_180046CDC = 3;
  qword_180046D00 = 0;
  qword_180046CF0 = 0;
  VariantInit(&stru_180046D70);
  qword_180046D60 = (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\OfflineFiles";
  qword_180046D50 = (__int64)L"Software\\Policies\\Microsoft\\Windows\\NetCache";
  qword_180046D88 = 0;
  qword_180046D28 = 0;
  word_180046D30 = 0;
  qword_180046D38 = 0;
  dword_180046D40 = 0;
  dword_180046D48 = 0;
  word_180046D44 = 0;
  qword_180046D68 = 0;
  qword_180046D58 = 0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__WMIPropertySettingMap__);
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  sub     rsp, 28h
0x180001019  lea     rcx, pvarg; pvarg
0x180001020  call    cs:__imp_VariantInit
0x180001026  xor     ebp, ebp
0x180001028  lea     rax, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18000102f  mov     cs:qword_1800464B0, rax
0x180001036  lea     rcx, stru_180046550; pvarg
0x18000103d  mov     rax, cs:off_1800389D0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001044  mov     ebx, 200Ch
0x180001049  mov     cs:qword_1800464D8, rax
0x180001050  mov     rax, cs:off_1800389C8; "Software\\Policies\\Microsoft\\Windows"...
0x180001057  mov     cs:qword_1800464C8, rax
0x18000105e  mov     cs:qword_180046500, rbp
0x180001065  mov     cs:?WMIPropertySettingMap@@3PAUWMIPropertySettingsItem@@A, rbp; WMIPropertySettingsItem near * WMIPropertySettingMap
0x18000106c  mov     cs:word_1800464A8, bp
0x180001073  mov     cs:dword_1800464B8, ebp
0x180001079  mov     cs:dword_1800464C0, ebp
0x18000107f  mov     cs:word_1800464BC, bx
0x180001086  mov     cs:qword_1800464E0, rbp
0x18000108d  mov     cs:qword_1800464D0, rbp
0x180001094  call    cs:__imp_VariantInit
0x18000109a  lea     rax, aWorkofflinedis; "WorkOfflineDisabled"
0x1800010a1  mov     cs:qword_180046568, rbp
0x1800010a8  mov     cs:qword_180046508, rax
0x1800010af  lea     esi, [rbp+0Bh]
0x1800010b2  lea     rax, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x1800010b9  mov     cs:word_180046510, bp
0x1800010c0  mov     cs:qword_180046518, rax
0x1800010c7  lea     rcx, stru_1800465B8; pvarg
0x1800010ce  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800010d5  mov     cs:qword_180046540, rax
0x1800010dc  mov     rax, cs:lpSubKey
0x1800010e3  mov     cs:qword_180046530, rax
0x1800010ea  mov     cs:dword_180046520, ebp
0x1800010f0  mov     cs:dword_180046528, ebp
0x1800010f6  mov     cs:word_180046524, si
0x1800010fd  mov     cs:qword_180046548, rbp
0x180001104  mov     cs:qword_180046538, rbp
0x18000110b  call    cs:__imp_VariantInit
0x180001111  lea     rax, aNomakeavailabl; "NoMakeAvailableOffline"
0x180001118  mov     cs:qword_1800465D0, rbp
0x18000111f  mov     cs:qword_180046570, rax
0x180001126  lea     rcx, stru_180046620; pvarg
0x18000112d  lea     rax, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x180001134  mov     cs:word_180046578, bp
0x18000113b  mov     cs:qword_180046580, rax
0x180001142  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001149  mov     cs:qword_1800465A8, rax
0x180001150  mov     rax, cs:lpSubKey
0x180001157  mov     cs:qword_180046598, rax
0x18000115e  mov     cs:dword_180046588, ebp
0x180001164  mov     cs:dword_180046590, ebp
0x18000116a  mov     cs:word_18004658C, si
0x180001171  mov     cs:qword_1800465B0, rbp
0x180001178  mov     cs:qword_1800465A0, rbp
0x18000117f  call    cs:__imp_VariantInit
0x180001185  lea     rax, aEncryptcache; "EncryptCache"
0x18000118c  mov     cs:qword_180046638, rbp
0x180001193  mov     cs:qword_1800465D8, rax
0x18000119a  lea     rcx, stru_180046688; pvarg
0x1800011a1  lea     rax, CSCWMI_STR_PROP_OFFLINEFILESCACHEENCRYPTED; "OfflineFilesCacheEncrypted"
0x1800011a8  mov     cs:word_1800465E0, bp
0x1800011af  mov     cs:qword_1800465E8, rax
0x1800011b6  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800011bd  mov     cs:qword_180046610, rax
0x1800011c4  mov     rax, cs:lpSubKey
0x1800011cb  mov     cs:qword_180046600, rax
0x1800011d2  mov     cs:dword_1800465F0, ebp
0x1800011d8  mov     cs:dword_1800465F8, ebp
0x1800011de  mov     cs:word_1800465F4, si
0x1800011e5  mov     cs:qword_180046618, rbp
0x1800011ec  mov     cs:qword_180046608, rbp
0x1800011f3  call    cs:__imp_VariantInit
0x1800011f9  lea     rax, aSlowlinkenable; "SlowLinkEnabled"
0x180001200  mov     cs:qword_1800466A0, rbp
0x180001207  mov     cs:qword_180046640, rax
0x18000120e  lea     rax, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x180001215  mov     cs:qword_180046650, rax
0x18000121c  mov     cs:word_180046648, bp
0x180001223  mov     cs:dword_180046658, ebp
0x180001229  mov     cs:dword_180046660, ebp
0x18000122f  mov     cs:word_18004665C, si
0x180001236  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000123d  lea     rcx, stru_1800466F0; pvarg
0x180001244  mov     cs:qword_180046678, rax
0x18000124b  mov     rax, cs:lpSubKey
0x180001252  mov     cs:qword_180046668, rax
0x180001259  mov     cs:qword_180046680, rbp
0x180001260  mov     cs:qword_180046670, rbp
0x180001267  call    cs:__imp_VariantInit
0x18000126d  lea     rax, aSyncenabledfor; "SyncEnabledForCostedNetwork"
0x180001274  mov     cs:qword_180046708, rbp
0x18000127b  mov     cs:qword_1800466A8, rax
0x180001282  lea     rcx, stru_180046758; pvarg
0x180001289  lea     rax, CSCWMI_STR_PROP_SYNCONCOSTEDNETWORKENABLED; "SyncOnCostedNetworkEnabled"
0x180001290  mov     cs:word_1800466B0, bp
0x180001297  mov     cs:qword_1800466B8, rax
0x18000129e  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800012a5  mov     cs:qword_1800466E0, rax
0x1800012ac  mov     rax, cs:lpSubKey
0x1800012b3  mov     cs:qword_1800466D0, rax
0x1800012ba  mov     cs:dword_1800466C0, ebp
0x1800012c0  mov     cs:dword_1800466C8, ebp
0x1800012c6  mov     cs:word_1800466C4, si
0x1800012cd  mov     cs:qword_1800466E8, rbp
0x1800012d4  mov     cs:qword_1800466D8, rbp
0x1800012db  call    cs:__imp_VariantInit
0x1800012e1  lea     rcx, aEnabled; "Enabled"
0x1800012e8  mov     cs:qword_180046770, rbp
0x1800012ef  lea     rax, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x1800012f6  mov     cs:qword_180046710, rcx
0x1800012fd  mov     cs:qword_180046720, rax
0x180001304  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000130b  mov     cs:qword_180046748, rax
0x180001312  mov     rax, cs:lpSubKey
0x180001319  mov     cs:qword_180046750, rcx
0x180001320  mov     cs:qword_180046740, rcx
0x180001327  lea     rcx, stru_1800467C0; pvarg
0x18000132e  mov     cs:qword_180046738, rax
0x180001335  mov     cs:word_180046718, bp
0x18000133c  mov     cs:dword_180046728, ebp
0x180001342  mov     cs:dword_180046730, ebp
0x180001348  mov     cs:word_18004672C, si
0x18000134f  call    cs:__imp_VariantInit
0x180001355  lea     rax, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18000135c  mov     cs:qword_1800467D8, rbp
0x180001363  mov     cs:qword_180046788, rax
0x18000136a  lea     rcx, stru_180046828; pvarg
0x180001371  mov     rax, cs:off_1800389C0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001378  mov     cs:qword_1800467B0, rax
0x18000137f  mov     rax, cs:off_1800389B8; "Software\\Policies\\Microsoft\\Windows"...
0x180001386  mov     cs:qword_1800467A0, rax
0x18000138d  mov     cs:qword_180046778, rbp
0x180001394  mov     cs:word_180046780, bp
0x18000139b  mov     cs:dword_180046790, ebp
0x1800013a1  mov     cs:dword_180046798, ebp
0x1800013a7  mov     cs:word_180046794, bx
0x1800013ae  mov     cs:qword_1800467B8, rbp
0x1800013b5  mov     cs:qword_1800467A8, rbp
0x1800013bc  call    cs:__imp_VariantInit
0x1800013c2  lea     rax, aBackgroundsync_5; "BackgroundSyncEnabled"
0x1800013c9  mov     cs:qword_180046840, rbp
0x1800013d0  mov     cs:qword_1800467E0, rax
0x1800013d7  lea     rcx, stru_180046890; pvarg
0x1800013de  lea     rax, CSCWMI_STR_PROP_BACKGROUNDSYNCENABLED; "BackgroundSyncEnabled"
0x1800013e5  mov     cs:word_1800467E8, bp
0x1800013ec  mov     cs:qword_1800467F0, rax
0x1800013f3  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800013fa  mov     cs:qword_180046818, rax
0x180001401  mov     rax, cs:lpSubKey
0x180001408  mov     cs:qword_180046808, rax
0x18000140f  mov     cs:dword_1800467F8, ebp
0x180001415  mov     cs:dword_180046800, ebp
0x18000141b  mov     cs:word_1800467FC, si
0x180001422  mov     cs:qword_180046820, rbp
0x180001429  mov     cs:qword_180046810, rbp
0x180001430  call    cs:__imp_VariantInit
0x180001436  lea     rax, aEconomicaladmi; "EconomicalAdminPinning"
0x18000143d  mov     cs:qword_1800468A8, rbp
0x180001444  mov     cs:qword_180046848, rax
0x18000144b  lea     rax, CSCWMI_STR_PROP_ECONOMICALADMINPINNINGENABLED; "EconomicalAdminPinningEnabled"
0x180001452  mov     cs:qword_180046858, rax
0x180001459  mov     cs:word_180046850, bp
0x180001460  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001467  lea     rcx, stru_1800468F8; pvarg
0x18000146e  mov     cs:qword_180046880, rax
0x180001475  mov     rax, cs:lpSubKey
0x18000147c  mov     cs:qword_180046870, rax
0x180001483  mov     cs:dword_180046860, ebp
0x180001489  mov     cs:dword_180046868, ebp
0x18000148f  mov     cs:word_180046864, si
0x180001496  mov     cs:qword_180046888, rbp
0x18000149d  mov     cs:qword_180046878, rbp
0x1800014a4  call    cs:__imp_VariantInit
0x1800014aa  lea     rax, aExcludedfilety; "ExcludedFileTypes"
0x1800014b1  mov     cs:qword_180046910, rbp
0x1800014b8  mov     cs:qword_1800468B0, rax
0x1800014bf  lea     rcx, stru_180046960; pvarg
0x1800014c6  lea     rax, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x1800014cd  mov     cs:word_1800468B8, bp
0x1800014d4  mov     cs:qword_1800468C0, rax
0x1800014db  lea     eax, [rbp+8]
0x1800014de  mov     cs:word_1800468CC, ax
0x1800014e5  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800014ec  mov     cs:qword_1800468E8, rax
0x1800014f3  mov     rax, cs:lpSubKey
0x1800014fa  mov     cs:qword_1800468D8, rax
0x180001501  mov     cs:dword_1800468C8, ebp
0x180001507  mov     cs:dword_1800468D0, ebp
0x18000150d  mov     cs:qword_1800468F0, rbp
0x180001514  mov     cs:qword_1800468E0, rbp
0x18000151b  call    cs:__imp_VariantInit
0x180001521  lea     rax, aCachequotaenab; "CacheQuotaEnabled"
0x180001528  mov     cs:qword_180046978, rbp
0x18000152f  mov     cs:qword_180046918, rax
0x180001536  lea     rcx, stru_1800469C8; pvarg
0x18000153d  lea     rax, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x180001544  mov     cs:word_180046920, bp
0x18000154b  mov     cs:qword_180046928, rax
0x180001552  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001559  mov     cs:qword_180046950, rax
0x180001560  mov     rax, cs:lpSubKey
0x180001567  mov     cs:qword_180046940, rax
0x18000156e  mov     cs:dword_180046930, ebp
0x180001574  mov     cs:dword_180046938, ebp
0x18000157a  mov     cs:word_180046934, si
0x180001581  mov     cs:qword_180046958, rbp
0x180001588  mov     cs:qword_180046948, rbp
0x18000158f  call    cs:__imp_VariantInit
0x180001595  lea     rax, aOnlinecachingl; "OnlineCachingLatencyThreshold"
0x18000159c  mov     cs:qword_1800469E0, rbp
0x1800015a3  mov     cs:qword_180046980, rax
0x1800015aa  lea     edi, [rbp+3]
0x1800015ad  lea     rax, CSCWMI_STR_PROP_TRANSPARENTCACHINGLATENCYTHRESHOLD; "TransparentCachingLatencyThreshold"
0x1800015b4  mov     cs:word_180046988, bp
0x1800015bb  mov     cs:qword_180046990, rax
0x1800015c2  lea     rcx, stru_180046A30; pvarg
0x1800015c9  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800015d0  mov     cs:qword_1800469B8, rax
0x1800015d7  mov     rax, cs:lpSubKey
0x1800015de  mov     cs:qword_1800469A8, rax
0x1800015e5  mov     cs:dword_180046998, ebp
0x1800015eb  mov     cs:dword_1800469A0, ebp
0x1800015f1  mov     cs:word_18004699C, di
0x1800015f8  mov     cs:qword_1800469C0, rbp
0x1800015ff  mov     cs:qword_1800469B0, rbp
0x180001606  call    cs:__imp_VariantInit
0x18000160c  lea     rax, aBackgroundsync_0; "BackgroundSyncPeriodMin"
0x180001613  mov     cs:qword_180046A48, rbp
0x18000161a  mov     cs:qword_1800469E8, rax
0x180001621  lea     ebx, [rbp+12h]
0x180001624  lea     rax, CSCWMI_STR_PROP_SYNCINTERVAL; "SyncInterval"
0x18000162b  mov     cs:word_1800469F0, bp
0x180001632  mov     cs:qword_1800469F8, rax
0x180001639  lea     rcx, stru_180046A98; pvarg
0x180001640  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001647  mov     cs:qword_180046A20, rax
0x18000164e  mov     rax, cs:lpSubKey
0x180001655  mov     cs:qword_180046A10, rax
0x18000165c  mov     cs:dword_180046A00, ebp
0x180001662  mov     cs:dword_180046A08, ebp
0x180001668  mov     cs:word_180046A04, bx
0x18000166f  mov     cs:qword_180046A28, rbp
0x180001676  mov     cs:qword_180046A18, rbp
0x18000167d  call    cs:__imp_VariantInit
0x180001683  lea     rax, aBackgroundsync_3; "BackgroundSyncMaxStartMin"
0x18000168a  mov     cs:qword_180046AB0, rbp
0x180001691  mov     cs:qword_180046A50, rax
0x180001698  lea     rcx, stru_180046B00; pvarg
0x18000169f  lea     rax, CSCWMI_STR_PROP_SYNCVARIANCE; "SyncVariance"
0x1800016a6  mov     cs:word_180046A58, bp
0x1800016ad  mov     cs:qword_180046A60, rax
0x1800016b4  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800016bb  mov     cs:qword_180046A88, rax
0x1800016c2  mov     rax, cs:lpSubKey
0x1800016c9  mov     cs:qword_180046A78, rax
0x1800016d0  mov     cs:dword_180046A68, ebp
0x1800016d6  mov     cs:dword_180046A70, ebp
0x1800016dc  mov     cs:word_180046A6C, bx
0x1800016e3  mov     cs:qword_180046A90, rbp
0x1800016ea  mov     cs:qword_180046A80, rbp
0x1800016f1  call    cs:__imp_VariantInit
0x1800016f7  lea     rax, aBackgroundsync; "BackgroundSyncIgnoreBlockOutAfterMin"
0x1800016fe  mov     cs:qword_180046B18, rbp
0x180001705  mov     cs:qword_180046AB8, rax
0x18000170c  lea     rcx, stru_180046B68; pvarg
0x180001713  lea     rax, CSCWMI_STR_PROP_MAXTIMEBETWEENSYNCS; "MaxTimeBetweenSyncs"
0x18000171a  mov     cs:word_180046AC0, bp
0x180001721  mov     cs:qword_180046AC8, rax
0x180001728  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000172f  mov     cs:qword_180046AF0, rax
0x180001736  mov     rax, cs:lpSubKey
0x18000173d  mov     cs:qword_180046AE0, rax
0x180001744  mov     cs:dword_180046AD0, ebp
0x18000174a  mov     cs:dword_180046AD8, ebp
0x180001750  mov     cs:word_180046AD4, bx
0x180001757  mov     cs:qword_180046AF8, rbp
0x18000175e  mov     cs:qword_180046AE8, rbp
0x180001765  call    cs:__imp_VariantInit
0x18000176b  lea     rax, aBackgroundsync_2; "BackgroundSyncBlockOutStartTime"
0x180001772  mov     cs:qword_180046B80, rbp
0x180001779  mov     cs:qword_180046B20, rax
0x180001780  lea     rcx, stru_180046BD0; pvarg
0x180001787  lea     rax, CSCWMI_STR_PROP_BLOCKOUTSTARTTIMEHOURSMINUTES; "BlockOutStartTimeHoursMinutes"
0x18000178e  mov     cs:word_180046B28, bp
0x180001795  mov     cs:qword_180046B30, rax
0x18000179c  mov     rax, cs:off_1800389B0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800017a3  mov     cs:qword_180046B58, rax
0x1800017aa  mov     rax, cs:lpSubKey
0x1800017b1  mov     cs:qword_180046B48, rax
0x1800017b8  mov     cs:dword_180046B38, ebp
0x1800017be  mov     cs:dword_180046B40, ebp
0x1800017c4  mov     cs:word_180046B3C, bx
0x1800017cb  mov     cs:qword_180046B60, rbp
0x1800017d2  mov     cs:qword_180046B50, rbp
0x1800017d9  call    cs:__imp_VariantInit
  ... truncated ...
```
