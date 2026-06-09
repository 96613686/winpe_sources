# UpdateAutoTriggerRegKeys

- ea: `0x180030670`
- end: `0x1800317e6`
- name: `UpdateAutoTriggerRegKeys`
- size: `4470`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180057f70`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x18000ec50`
- `0x180012c24`
- `0x180017ec8`
- `0x18001a588`
- `0x180030670`
- `0x180033780`
- `0x180033ad8`
- `0x180034434`
- `0x180048180`
- `0x18005f6f4`
- `0x180069848`
- `0x180083b18`
- `0x1800df660`
- `0x1800e8ef0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800307d6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800307d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031453`
- `RPCRT4!RpcImpersonateClient` at `0x1800313b4`
- `RPCRT4!RpcImpersonateClient` at `0x1800313b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031443`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031443`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030d5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030fc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800311a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031237`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031555`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030d5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030fc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800311a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031237`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031555`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031732`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030b6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030bc4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030c1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030c7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031129`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030b6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030bc4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030c1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030c7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031129`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030822`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030822`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030988`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800308f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030988`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030955`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031356`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030955`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031356`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800316ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003171d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800316ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003171d`

## string_xrefs

- `0x1800307e7`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800307f0`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180030c13`: `UserSID`
- `0x180030c4d`: `UserSID`
- `0x180031540`: `UserSID`
- `0x180030b67`: `AutoTriggerProfilePhonebookPath`
- `0x180030b9a`: `AutoTriggerProfilePhonebookPath`
- `0x180031191`: `AutoTriggerProfilePhonebookPath`
- `0x1800311e3`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall UpdateAutoTriggerRegKeys(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rdi
  __int128 v5; // xmm0
  int v6; // r14d
  __int64 v7; // rsi
  int v8; // r13d
  int v9; // r15d
  BYTE *v10; // r12
  const char *v11; // rcx
  const char *v12; // r11
  const char *v13; // r10
  const char *v14; // r9
  char IsStateSeparationEnabled; // al
  const WCHAR *v16; // rdx
  unsigned int v17; // eax
  unsigned int UserSid; // ebx
  struct _LIST_ENTRY *v19; // rcx
  __int64 v20; // rdx
  int v21; // edi
  unsigned int v22; // eax
  __int64 v23; // r9
  BYTE *v24; // rbx
  LSTATUS v25; // eax
  struct _LIST_ENTRY *v26; // rcx
  __int64 v27; // rdx
  unsigned int active; // eax
  LSTATUS v29; // eax
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  struct _LIST_ENTRY *v33; // rcx
  unsigned int v34; // eax
  LSTATUS v35; // eax
  BYTE *v36; // r14
  unsigned int v37; // eax
  LSTATUS v38; // eax
  __int64 v39; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  LSTATUS v41; // eax
  __int64 v42; // rdi
  __int64 v43; // rax
  DWORD LastError; // eax
  struct _LIST_ENTRY *v45; // rcx
  int v46; // edx
  const WCHAR *v47; // r9
  __int64 v48; // rax
  BYTE *v49; // r15
  __int64 v50; // rax
  struct _LIST_ENTRY *v51; // rcx
  const char *v52; // r13
  struct _LIST_ENTRY *v53; // rcx
  const char *v54; // r9
  LSTATUS v55; // eax
  const char *v56; // r9
  unsigned int v57; // eax
  struct _LIST_ENTRY *v58; // rcx
  struct _LIST_ENTRY *v59; // rcx
  __int64 result; // rax
  int dwOptions; // [rsp+20h] [rbp-79h]
  int samDesired; // [rsp+28h] [rbp-71h]
  DWORD cbData; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  DWORD Type; // [rsp+60h] [rbp-39h] BYREF
  BYTE *v66; // [rsp+68h] [rbp-31h]
  BYTE *lpData; // [rsp+70h] [rbp-29h] BYREF
  int v68; // [rsp+78h] [rbp-21h]
  HLOCAL hMem; // [rsp+80h] [rbp-19h]
  BYTE Data[8]; // [rsp+88h] [rbp-11h] BYREF
  unsigned int *v71; // [rsp+90h] [rbp-9h]
  BYTE v72[16]; // [rsp+98h] [rbp-1h] BYREF

  v71 = (unsigned int *)a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1324, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_OWORD *)(a3 + 1040);
  v6 = *(_DWORD *)(a3 + 1056);
  v7 = a3 + 4;
  v8 = *(_DWORD *)(a3 + 1060);
  v9 = *(_DWORD *)(a3 + 1580);
  v10 = (BYTE *)(a3 + 518);
  v66 = (BYTE *)(a3 + 4);
  *(_OWORD *)v72 = v5;
  hMem = (HLOCAL)(a3 + 1064);
  v68 = 0;
  lpData = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  *(_DWORD *)Data = 1;
  v11 = L"<NULL>";
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 5u )
  {
    v12 = L"<NULL>";
    v13 = L"<NULL>";
    v14 = L"<NULL>";
    if ( a3 != -1064 )
      v12 = (const char *)(a3 + 1064);
    if ( a3 != -4 )
      v13 = (const char *)(a3 + 4);
    if ( a3 != -518 )
      LODWORD(v14) = a3 + 518;
    WPP_SF_SSS_guid_ccc(
      v4[1].Flink,
      1325,
      (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
      (_DWORD)v14,
      (__int64)v13,
      (__int64)v12,
      (__int64)v72,
      v6 != 0,
      v8 != 0,
      v9 != 0);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a3 == -518 || a3 == -4 )
  {
    UserSid = 87;
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v4[1].Blink) & 0x2000) == 0
      || BYTE1(v4[1].Blink) < 2u )
    {
      goto LABEL_269;
    }
    Flink = v4[1].Flink;
    v39 = 1326;
    goto LABEL_162;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v11);
  v16 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !IsStateSeparationEnabled )
    v16 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v17 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0, 0, 0x20007u, 0, &hKey, 0);
  UserSid = v17;
  if ( v17 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v20 = 1327;
LABEL_24:
      WPP_SF_d(v19[1].Flink, v20, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v17);
      goto LABEL_269;
    }
    goto LABEL_269;
  }
  v17 = ProfileSatisifesLockDownPolicy(v7, v10);
  UserSid = v17;
  if ( !v17 )
  {
    v21 = 0;
    v22 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, 0, &cbData);
    if ( v22 || Type != 7 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
      {
LABEL_54:
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v26[1].Blink) & 0x2000) != 0
          && BYTE1(v26[1].Blink) >= 5u )
        {
          LOBYTE(samDesired) = v21;
          LOBYTE(dwOptions) = v9 != 0;
          LOBYTE(v23) = v6 != 0;
          WPP_SF_ccc(v26[1].Flink, 1333, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v23, dwOptions, samDesired);
          v26 = WPP_GLOBAL_Control;
        }
LABEL_58:
        if ( v6 )
        {
          if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v26[1].Blink) & 0x2000) != 0
            && BYTE1(v26[1].Blink) >= 5u )
          {
            WPP_SF_(v26[1].Flink, 1334, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          active = VpnProfileActiveSet(0, 0, 0, 1);
          if ( active
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1335, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, active);
          }
          v29 = RegDeleteValueW(hKey, L"AutoTriggerProfilePhonebookPath");
          if ( v29
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control[1].Flink,
              1336,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (unsigned int)L"AutoTriggerProfilePhonebookPath",
              v29);
          }
          v30 = RegDeleteValueW(hKey, L"AutoTriggerProfileEntryName");
          if ( v30
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control[1].Flink,
              1337,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (unsigned int)L"AutoTriggerProfileEntryName",
              v30);
          }
          v31 = RegDeleteValueW(hKey, L"UserSID");
          if ( v31
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control[1].Flink,
              1338,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (unsigned int)L"UserSID",
              v31);
          }
          v32 = RegDeleteValueW(hKey, L"AutoTriggerProfileGUID");
          UserSid = v32;
          if ( v32 )
          {
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1339,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)L"AutoTriggerProfileGUID",
                v32);
              v33 = WPP_GLOBAL_Control;
            }
            UserSid = 0;
          }
          else
          {
            v33 = WPP_GLOBAL_Control;
          }
          if ( !v9 )
            goto LABEL_112;
          if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v33[1].Blink) & 0x2000) != 0
            && BYTE1(v33[1].Blink) >= 4u )
          {
            WPP_SF_(v33[1].Flink, 1340, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            v33 = WPP_GLOBAL_Control;
          }
          if ( v21 )
            goto LABEL_112;
          v34 = AddWStringToWMultiStringStart(&lpData, &cbData, v66);
          UserSid = 0;
          if ( v34 )
          {
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_112;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1343, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v34);
          }
          else
          {
            v35 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
            UserSid = v35;
            if ( v35 )
            {
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1341,
                  (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  (unsigned int)L"AutoTriggerDisabledProfilesList",
                  v35);
                v33 = WPP_GLOBAL_Control;
              }
              UserSid = 0;
              goto LABEL_112;
            }
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
            {
LABEL_112:
              if ( v8 )
              {
                UserSid = RegSetValueExW(hKey, L"AutoTriggeringDisabled", 0, 4u, Data, 4u);
                if ( UserSid )
                {
                  v33 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
                  {
                    WPP_SF_S(
                      WPP_GLOBAL_Control[1].Flink,
                      1344,
                      WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                      L"AutoTriggeringDisabled");
                    v33 = WPP_GLOBAL_Control;
                  }
                  UserSid = 0;
                }
                else
                {
                  v33 = WPP_GLOBAL_Control;
                }
              }
              if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v33[1].Blink) & 0x2000) != 0
                && BYTE1(v33[1].Blink) >= 4u )
              {
                WPP_SF_(v33[1].Flink, 1345, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              }
              goto LABEL_267;
            }
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1342, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          v33 = WPP_GLOBAL_Control;
          goto LABEL_112;
        }
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v26[1].Blink) & 0x2000) != 0
          && BYTE1(v26[1].Blink) >= 5u )
        {
          WPP_SF_(v26[1].Flink, 1346, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          v26 = WPP_GLOBAL_Control;
        }
        if ( v9 )
        {
          if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(v26[1].Blink) & 0x2000) != 0 && BYTE1(v26[1].Blink) >= 5u )
            {
              WPP_SF_(v26[1].Flink, 1347, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              v26 = WPP_GLOBAL_Control;
            }
            if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v26[1].Blink) & 0x2000) != 0
              && BYTE1(v26[1].Blink) >= 4u )
            {
              WPP_SF_(v26[1].Flink, 1348, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            }
          }
          v36 = v66;
          if ( v21 )
          {
            v37 = DeleteWStringFromWMultiString(&lpData, &cbData, v66);
            if ( v37 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1351, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v37);
              }
            }
            else
            {
              v38 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
              if ( v38 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control[1].Flink,
                    1349,
                    (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                    (unsigned int)L"AutoTriggerDisabledProfilesList",
                    v38);
                }
              }
              else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                     && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1350, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              }
            }
          }
        }
        else
        {
          if ( v21 )
          {
            if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v26[1].Blink) & 0x2000) != 0
              && BYTE1(v26[1].Blink) >= 5u )
            {
              WPP_SF_(v26[1].Flink, 1352, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              v26 = WPP_GLOBAL_Control;
            }
            UserSid = 1206;
            if ( v26 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(v26[1].Blink) & 0x2000) == 0
              || BYTE1(v26[1].Blink) < 2u )
            {
              goto LABEL_267;
            }
            v39 = 1353;
            goto LABEL_161;
          }
          v36 = v66;
        }
        v41 = RegDeleteValueW(hKey, L"AutoTriggeringDisabled");
        if ( v41
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control[1].Flink,
            1354,
            (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
            (unsigned int)L"AutoTriggeringDisabled",
            v41);
        }
        v42 = -1;
        v43 = -1;
        do
          ++v43;
        while ( *(_WORD *)&v10[2 * v43] );
        LastError = RegSetValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, 1u, v10, 2 * v43 + 2);
        UserSid = LastError;
        if ( LastError )
        {
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v46 = 1355;
            v47 = L"AutoTriggerProfilePhonebookPath";
LABEL_176:
            WPP_SF_Sd(
              v45[1].Flink,
              v46,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (_DWORD)v47,
              LastError);
          }
LABEL_267:
          if ( lpData )
            LocalFree(lpData);
          goto LABEL_269;
        }
        v48 = -1;
        do
          ++v48;
        while ( *(_WORD *)&v36[2 * v48] );
        LastError = RegSetValueExW(hKey, L"AutoTriggerProfileEntryName", 0, 1u, v36, 2 * v48 + 2);
        UserSid = LastError;
        if ( LastError )
        {
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_267;
          }
          v46 = 1356;
          goto LABEL_184;
        }
        v49 = (BYTE *)hMem;
        if ( hMem )
        {
          v50 = -1;
          do
            ++v50;
          while ( *((_WORD *)hMem + v50) );
          if ( v50 )
            goto LABEL_237;
        }
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1357, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        if ( (unsigned int)IsPublicPhonebook(v10) )
        {
          v51 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1358, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            v51 = WPP_GLOBAL_Control;
          }
          v49 = (BYTE *)L"S-1-1-0";
          hMem = (HLOCAL)L"S-1-1-0";
LABEL_231:
          if ( v51 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            v52 = L"<NULL>";
            if ( (HIDWORD(v51[1].Blink) & 0x2000) != 0 && BYTE1(v51[1].Blink) >= 5u )
            {
              v53 = v51[1].Flink;
              v54 = L"<NULL>";
              if ( v49 )
                v54 = (const char *)v49;
              WPP_SF_S(v53, 1365, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v54);
            }
            do
LABEL_238:
              ++v42;
            while ( *(_WORD *)&v49[2 * v42] );
            LastError = RegSetValueExW(hKey, L"UserSID", 0, 1u, v49, 2 * v42 + 2);
            UserSid = LastError;
            if ( LastError )
            {
              v45 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_267;
              }
              v46 = 1366;
LABEL_184:
              v47 = L"AutoTriggerProfileEntryName";
              goto LABEL_176;
            }
            v55 = RegSetValueExW(hKey, L"AutoTriggerProfileGUID", 0, 3u, v72, 0x10u);
            UserSid = v55;
            if ( v55 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1367,
                  (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  (unsigned int)L"AutoTriggerProfileGUID",
                  v55);
              }
              goto LABEL_267;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              v56 = L"<NULL>";
              if ( v49 )
                v56 = (const char *)v49;
              WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 1368, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v56);
            }
            v57 = VpnProfileActiveSet(v10, v66, v49, 1);
            UserSid = v57;
            if ( v57 )
            {
              v58 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                goto LABEL_267;
              if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
LABEL_261:
                if ( v58 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v58[1].Blink) & 0x2000) != 0
                  && BYTE1(v58[1].Blink) >= 5u )
                {
                  v59 = v58[1].Flink;
                  if ( v49 )
                    v52 = (const char *)v49;
                  WPP_SF_S(v59, 1370, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v52);
                }
                goto LABEL_267;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1369, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v57);
            }
            v58 = WPP_GLOBAL_Control;
            goto LABEL_261;
          }
LABEL_237:
          v52 = L"<NULL>";
          goto LABEL_238;
        }
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1359, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        hMem = LocalAlloc(0x40u, 0x1388u);
        v49 = (BYTE *)hMem;
        v68 = 1;
        if ( hMem )
        {
          LastError = RpcImpersonateClient(g_hRpcHandle);
          UserSid = LastError;
          if ( LastError )
          {
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_267;
            }
            v46 = 1361;
          }
          else
          {
            UserSid = GetUserSid(v49);
            if ( UserSid
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1362, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
            }
            if ( RevertToSelf() )
            {
              if ( !UserSid )
              {
                v51 = WPP_GLOBAL_Control;
                goto LABEL_231;
              }
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_267;
              }
              v39 = 1364;
              goto LABEL_161;
            }
            LastError = GetLastError();
            UserSid = LastError;
            if ( !LastError )
              goto LABEL_267;
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_267;
            }
            v46 = 1363;
          }
          LODWORD(v47) = (_DWORD)v10;
          goto LABEL_176;
        }
        UserSid = 8;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_267;
        }
        v39 = 1360;
LABEL_161:
        Flink = v26[1].Flink;
LABEL_162:
        WPP_SF_d(Flink, v39, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
        goto LABEL_267;
      }
      v27 = 1332;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1329, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      v24 = (BYTE *)LocalAlloc(0x40u, cbData);
      lpData = v24;
      v25 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, v24, &cbData);
      if ( v25 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_54;
        WPP_SF_Sd(
          WPP_GLOBAL_Control[1].Flink,
          1331,
          (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          (unsigned int)L"AutoTriggerDisabledProfilesList",
          v25);
        goto LABEL_53;
      }
      if ( Type != 7 )
      {
LABEL_53:
        v26 = WPP_GLOBAL_Control;
        goto LABEL_54;
      }
      v22 = WideMultiStringListLookUp(v24, cbData, v66);
      if ( !v22 )
      {
        v21 = 1;
        goto LABEL_53;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_54;
      v27 = 1330;
    }
    WPP_SF_d(v26[1].Flink, v27, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v22);
    goto LABEL_53;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v20 = 1328;
    goto LABEL_24;
  }
LABEL_269:
  if ( hMem && v68 )
    LocalFree(hMem);
  if ( hKey )
    RegCloseKey(hKey);
  *v71 = UserSid;
  if ( (Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_featureState & 0x10) != 0 )
    result = Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_featureState & 1;
  else
    result = Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
    result = SendAutoConnectModifiedNotification();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1371, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
  }
  return result;
}

```

## disassembly

```asm
0x180030670  push    rbp
0x180030672  push    rbx
0x180030673  push    rsi
0x180030674  push    rdi
0x180030675  push    r12
0x180030677  push    r13
0x180030679  push    r14
0x18003067b  push    r15
0x18003067d  lea     rbp, [rsp-1Fh]
0x180030682  sub     rsp, 0B8h
0x180030689  mov     rax, cs:__security_cookie
0x180030690  xor     rax, rsp
0x180030693  mov     [rbp+57h+var_48], rax
0x180030697  mov     rbx, r8
0x18003069a  mov     [rbp+57h+var_60], rbx
0x18003069e  mov     rdi, cs:WPP_GLOBAL_Control
0x1800306a5  lea     rax, WPP_GLOBAL_Control
0x1800306ac  cmp     rdi, rax
0x1800306af  jz      short loc_1800306DC
0x1800306b1  test    dword ptr [rdi+1Ch], 2000h
0x1800306b8  jz      short loc_1800306DC
0x1800306ba  cmp     byte ptr [rdi+19h], 6
0x1800306be  jb      short loc_1800306DC
0x1800306c0  mov     rcx, [rdi+10h]
0x1800306c4  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800306cb  mov     edx, 52Ch
0x1800306d0  call    WPP_SF_
0x1800306d5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800306dc  movups  xmm0, xmmword ptr [rbx+410h]
0x1800306e3  mov     r14d, [rbx+420h]
0x1800306ea  lea     rsi, [rbx+4]
0x1800306ee  mov     r13d, [rbx+424h]
0x1800306f5  lea     rax, [rbx+428h]
0x1800306fc  mov     r15d, [rbx+62Ch]
0x180030703  lea     r12, [rbx+206h]
0x18003070a  xor     ebx, ebx
0x18003070c  mov     [rbp+57h+var_88], rsi
0x180030710  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x180030715  mov     [rbp+57h+hMem], rax
0x180030719  mov     [rbp+57h+var_78], 0
0x180030720  mov     [rbp+57h+lpData], rbx
0x180030724  mov     [rbp+57h+cbData], ebx
0x180030727  mov     [rbp+57h+Type], ebx
0x18003072a  mov     [rbp+57h+hKey], rbx
0x18003072e  mov     dword ptr [rbp+57h+Data], 1
0x180030735  lea     rdx, WPP_GLOBAL_Control
0x18003073c  lea     rcx, aNull_4; "<NULL>"
0x180030743  cmp     rdi, rdx
0x180030746  jz      short loc_1800307C4
0x180030748  test    dword ptr [rdi+1Ch], 2000h
0x18003074f  jz      short loc_1800307C4
0x180030751  cmp     byte ptr [rdi+19h], 5
0x180030755  jb      short loc_1800307C4
0x180030757  test    rax, rax
0x18003075a  mov     r11, rcx
0x18003075d  mov     r10, rcx
0x180030760  mov     r9, rcx
0x180030763  cmovnz  r11, rax
0x180030767  mov     edx, 52Dh
0x18003076c  test    rsi, rsi
0x18003076f  cmovnz  r10, rsi
0x180030773  test    r12, r12
0x180030776  cmovnz  r9, r12
0x18003077a  test    r15d, r15d
0x18003077d  setnz   r8b
0x180030781  test    r13d, r13d
0x180030784  mov     [rsp+0F0h+var_A8], r8b
0x180030789  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030790  setnz   cl
0x180030793  test    r14d, r14d
0x180030796  mov     byte ptr [rsp+0F0h+lpdwDisposition], cl
0x18003079a  mov     rcx, [rdi+10h]
0x18003079e  setnz   al
0x1800307a1  mov     byte ptr [rsp+0F0h+phkResult], al
0x1800307a5  lea     rax, [rbp+57h+var_58]
0x1800307a9  mov     [rsp+0F0h+lpSecurityAttributes], rax
0x1800307ae  mov     qword ptr [rsp+0F0h+samDesired], r11
0x1800307b3  mov     qword ptr [rsp+0F0h+dwOptions], r10
0x1800307b8  call    WPP_SF_SSS_guid_ccc
0x1800307bd  mov     rdi, cs:WPP_GLOBAL_Control
0x1800307c4  test    r12, r12
0x1800307c7  jz      loc_180031753
0x1800307cd  test    rsi, rsi
0x1800307d0  jz      loc_180031753
0x1800307d6  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800307dd  nop     dword ptr [rax+rax+00h]
0x1800307e2  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x1800307e7  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800307ee  test    al, al
0x1800307f0  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800307f7  lea     rax, [rbp+57h+hKey]
0x1800307fb  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180030800  cmovz   rdx, rcx; lpSubKey
0x180030804  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180030809  xor     r9d, r9d; lpClass
0x18003080c  mov     [rsp+0F0h+samDesired], 20007h; samDesired
0x180030814  xor     r8d, r8d; Reserved
0x180030817  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003081e  mov     [rsp+0F0h+dwOptions], ebx; dwOptions
0x180030822  call    cs:__imp_RegCreateKeyExW
0x180030829  nop     dword ptr [rax+rax+00h]
0x18003082e  mov     ebx, eax
0x180030830  test    eax, eax
0x180030832  jz      short loc_180030885
0x180030834  mov     rcx, cs:WPP_GLOBAL_Control
0x18003083b  lea     r15, WPP_GLOBAL_Control
0x180030842  mov     r13d, 2000h
0x180030848  cmp     rcx, r15
0x18003084b  jz      loc_18003170B
0x180030851  test    [rcx+1Ch], r13d
0x180030855  jz      loc_18003170B
0x18003085b  mov     sil, 2
0x18003085e  cmp     [rcx+19h], sil
0x180030862  jb      loc_18003170B
0x180030868  mov     edx, 52Fh
0x18003086d  mov     rcx, [rcx+10h]
0x180030871  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030878  mov     r9d, eax
0x18003087b  call    WPP_SF_d
0x180030880  jmp     loc_18003170B
0x180030885  mov     rdx, r12
0x180030888  mov     rcx, rsi
0x18003088b  call    ProfileSatisifesLockDownPolicy
0x180030890  mov     ebx, eax
0x180030892  test    eax, eax
0x180030894  jz      short loc_1800308D1
0x180030896  mov     rcx, cs:WPP_GLOBAL_Control
0x18003089d  lea     r15, WPP_GLOBAL_Control
0x1800308a4  mov     r13d, 2000h
0x1800308aa  cmp     rcx, r15
0x1800308ad  jz      loc_18003170B
0x1800308b3  test    [rcx+1Ch], r13d
0x1800308b7  jz      loc_18003170B
0x1800308bd  mov     sil, 2
0x1800308c0  cmp     [rcx+19h], sil
0x1800308c4  jb      loc_18003170B
0x1800308ca  mov     edx, 530h
0x1800308cf  jmp     short loc_18003086D
0x1800308d1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800308d5  lea     rax, [rbp+57h+cbData]
0x1800308d9  xor     ebx, ebx
0x1800308db  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x1800308e0  lea     r9, [rbp+57h+Type]; lpType
0x1800308e4  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x1800308e9  xor     r8d, r8d; lpReserved
0x1800308ec  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x1800308f3  mov     edi, ebx
0x1800308f5  call    cs:__imp_RegQueryValueExW
0x1800308fc  nop     dword ptr [rax+rax+00h]
0x180030901  mov     sil, 2
0x180030904  test    eax, eax
0x180030906  jnz     loc_180030A3C
0x18003090c  cmp     [rbp+57h+Type], 7
0x180030910  jnz     loc_180030A3C
0x180030916  mov     rcx, cs:WPP_GLOBAL_Control
0x18003091d  lea     rax, WPP_GLOBAL_Control
0x180030924  cmp     rcx, rax
0x180030927  jz      short loc_18003094D
0x180030929  test    dword ptr [rcx+1Ch], 2000h
0x180030930  jz      short loc_18003094D
0x180030932  cmp     byte ptr [rcx+19h], 4
0x180030936  jb      short loc_18003094D
0x180030938  mov     rcx, [rcx+10h]
0x18003093c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030943  mov     edx, 531h
0x180030948  call    WPP_SF_
0x18003094d  mov     edx, [rbp+57h+cbData]; uBytes
0x180030950  mov     ecx, 40h ; '@'; uFlags
0x180030955  call    cs:__imp_LocalAlloc
0x18003095c  nop     dword ptr [rax+rax+00h]
0x180030961  mov     rcx, [rbp+57h+hKey]; hKey
0x180030965  lea     r9, [rbp+57h+Type]; lpType
0x180030969  mov     rbx, rax
0x18003096c  mov     [rbp+57h+lpData], rax
0x180030970  lea     rax, [rbp+57h+cbData]
0x180030974  xor     r8d, r8d; lpReserved
0x180030977  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x18003097c  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x180030983  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x180030988  call    cs:__imp_RegQueryValueExW
0x18003098f  nop     dword ptr [rax+rax+00h]
0x180030994  test    eax, eax
0x180030996  jnz     short loc_1800309F4
0x180030998  cmp     [rbp+57h+Type], 7
0x18003099c  jnz     loc_180030A76
0x1800309a2  mov     r8, [rbp+57h+var_88]
0x1800309a6  mov     rcx, rbx
0x1800309a9  mov     edx, [rbp+57h+cbData]
0x1800309ac  call    WideMultiStringListLookUp
0x1800309b1  xor     ebx, ebx
0x1800309b3  test    eax, eax
0x1800309b5  jnz     short loc_1800309BF
0x1800309b7  lea     edi, [rbx+1]
0x1800309ba  jmp     loc_180030A76
0x1800309bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309c6  lea     rdx, WPP_GLOBAL_Control
0x1800309cd  cmp     rcx, rdx
0x1800309d0  jz      loc_180030ACA
0x1800309d6  test    dword ptr [rcx+1Ch], 2000h
0x1800309dd  jz      loc_180030A7D
0x1800309e3  cmp     [rcx+19h], sil
0x1800309e7  jb      loc_180030A7D
0x1800309ed  mov     edx, 532h
0x1800309f2  jmp     short loc_180030A63
0x1800309f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309fb  lea     rdx, WPP_GLOBAL_Control
0x180030a02  cmp     rcx, rdx
0x180030a05  jz      loc_180030ACA
0x180030a0b  test    dword ptr [rcx+1Ch], 2000h
0x180030a12  jz      short loc_180030A7D
0x180030a14  cmp     [rcx+19h], sil
0x180030a18  jb      short loc_180030A7D
0x180030a1a  mov     rcx, [rcx+10h]
0x180030a1e  lea     r9, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x180030a25  mov     edx, 533h
0x180030a2a  mov     [rsp+0F0h+dwOptions], eax
0x180030a2e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030a35  call    WPP_SF_Sd
0x180030a3a  jmp     short loc_180030A76
0x180030a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a43  lea     rdx, WPP_GLOBAL_Control
0x180030a4a  cmp     rcx, rdx
0x180030a4d  jz      short loc_180030ACA
0x180030a4f  test    dword ptr [rcx+1Ch], 2000h
0x180030a56  jz      short loc_180030A7D
0x180030a58  cmp     byte ptr [rcx+19h], 4
0x180030a5c  jb      short loc_180030A7D
0x180030a5e  mov     edx, 534h
0x180030a63  mov     rcx, [rcx+10h]
0x180030a67  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030a6e  mov     r9d, eax
0x180030a71  call    WPP_SF_d
0x180030a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a7d  lea     rax, WPP_GLOBAL_Control
0x180030a84  cmp     rcx, rax
0x180030a87  jz      short loc_180030AD1
0x180030a89  test    dword ptr [rcx+1Ch], 2000h
0x180030a90  jz      short loc_180030AD1
0x180030a92  cmp     byte ptr [rcx+19h], 5
0x180030a96  jb      short loc_180030AD1
0x180030a98  mov     rcx, [rcx+10h]
0x180030a9c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030aa3  test    r15d, r15d
0x180030aa6  mov     byte ptr [rsp+0F0h+samDesired], dil
0x180030aab  mov     edx, 535h
0x180030ab0  setnz   al
0x180030ab3  test    r14d, r14d
0x180030ab6  mov     byte ptr [rsp+0F0h+dwOptions], al
0x180030aba  setnz   r9b
0x180030abe  call    WPP_SF_ccc
0x180030ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aca  lea     rax, WPP_GLOBAL_Control
0x180030ad1  xor     ebx, ebx
0x180030ad3  test    r14d, r14d
0x180030ad6  jz      loc_180030EE6
0x180030adc  mov     r12d, 2000h
0x180030ae2  cmp     rcx, rax
0x180030ae5  jz      short loc_180030B08
0x180030ae7  test    [rcx+1Ch], r12d
0x180030aeb  jz      short loc_180030B08
0x180030aed  cmp     byte ptr [rcx+19h], 5
0x180030af1  jb      short loc_180030B08
0x180030af3  mov     rcx, [rcx+10h]
0x180030af7  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030afe  mov     edx, 536h
0x180030b03  call    WPP_SF_
0x180030b08  mov     r9d, r14d
0x180030b0b  mov     [rsp+0F0h+dwOptions], 1; int
0x180030b13  xor     r8d, r8d; void *
0x180030b16  xor     edx, edx; void *
0x180030b18  xor     ecx, ecx; Src
0x180030b1a  call    VpnProfileActiveSet
0x180030b1f  test    eax, eax
0x180030b21  jz      short loc_180030B5C
0x180030b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b2a  lea     r14, WPP_GLOBAL_Control
0x180030b31  cmp     rcx, r14
0x180030b34  jz      short loc_180030B63
0x180030b36  test    [rcx+1Ch], r12d
0x180030b3a  jz      short loc_180030B63
0x180030b3c  cmp     [rcx+19h], sil
0x180030b40  jb      short loc_180030B63
0x180030b42  mov     rcx, [rcx+10h]
0x180030b46  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180030b4d  mov     edx, 537h
0x180030b52  mov     r9d, eax
0x180030b55  call    WPP_SF_d
0x180030b5a  jmp     short loc_180030B63
0x180030b5c  lea     r14, WPP_GLOBAL_Control
0x180030b63  mov     rcx, [rbp+57h+hKey]; hKey
0x180030b67  lea     rdx, aAutotriggerpro_2; "AutoTriggerProfilePhonebookPath"
0x180030b6e  call    cs:__imp_RegDeleteValueW
0x180030b75  nop     dword ptr [rax+rax+00h]
0x180030b7a  test    eax, eax
0x180030b7c  jz      short loc_180030BB6
0x180030b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b85  cmp     rcx, r14
0x180030b88  jz      short loc_180030BB6
0x180030b8a  test    [rcx+1Ch], r12d
0x180030b8e  jz      short loc_180030BB6
  ... truncated ...
```
