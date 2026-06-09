# UpdateAutoTriggerRegKeys

- ea: `0x18002f250`
- end: `0x180030331`
- name: `UpdateAutoTriggerRegKeys`
- size: `4321`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180055620`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18000e650`
- `0x18001248c`
- `0x180017548`
- `0x180019ba4`
- `0x18002f250`
- `0x180032168`
- `0x1800324b0`
- `0x180032d90`
- `0x180045e34`
- `0x18005c710`
- `0x180066068`
- `0x18007f9ec`
- `0x1800dc318`
- `0x1800e7260`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18002f3b6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002f3b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffc3`
- `RPCRT4!RpcImpersonateClient` at `0x18002ff30`
- `RPCRT4!RpcImpersonateClient` at `0x18002ff30`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ffb9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ffb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f4c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f550`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f4c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f550`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030284`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fb5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fd34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fdbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800300bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003012b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fb5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fd34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fdbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800300bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003012b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f730`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f780`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f7d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f82d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fcbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f730`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f780`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f7d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f82d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fcbd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f3fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f3fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f523`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fed8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f523`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003025d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030275`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003025d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030275`

## string_xrefs

- `0x18002f3c1`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18002f3ca`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18002f7c9`: `UserSID`
- `0x18002f7fd`: `UserSID`
- `0x1800300aa`: `UserSID`
- `0x18002f729`: `AutoTriggerProfilePhonebookPath`
- `0x18002f756`: `AutoTriggerProfilePhonebookPath`
- `0x18002fd1f`: `AutoTriggerProfilePhonebookPath`
- `0x18002fd6b`: `AutoTriggerProfilePhonebookPath`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1324, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
      (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
      WPP_SF_d(v19[1].Flink, v20, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v17);
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
          WPP_SF_ccc(v26[1].Flink, 1333, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v23, dwOptions, samDesired);
          v26 = WPP_GLOBAL_Control;
        }
LABEL_58:
        if ( v6 )
        {
          if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v26[1].Blink) & 0x2000) != 0
            && BYTE1(v26[1].Blink) >= 5u )
          {
            WPP_SF_(v26[1].Flink, 1334, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          active = VpnProfileActiveSet(0, 0, 0, 1);
          if ( active
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1335, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, active);
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
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
            WPP_SF_(v33[1].Flink, 1340, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1343, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v34);
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
                  (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
                      WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
                WPP_SF_(v33[1].Flink, 1345, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              }
              goto LABEL_267;
            }
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1342, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          v33 = WPP_GLOBAL_Control;
          goto LABEL_112;
        }
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v26[1].Blink) & 0x2000) != 0
          && BYTE1(v26[1].Blink) >= 5u )
        {
          WPP_SF_(v26[1].Flink, 1346, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          v26 = WPP_GLOBAL_Control;
        }
        if ( v9 )
        {
          if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(v26[1].Blink) & 0x2000) != 0 && BYTE1(v26[1].Blink) >= 5u )
            {
              WPP_SF_(v26[1].Flink, 1347, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              v26 = WPP_GLOBAL_Control;
            }
            if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v26[1].Blink) & 0x2000) != 0
              && BYTE1(v26[1].Blink) >= 4u )
            {
              WPP_SF_(v26[1].Flink, 1348, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1351, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v37);
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
                    (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                    (unsigned int)L"AutoTriggerDisabledProfilesList",
                    v38);
                }
              }
              else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                     && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1350, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
              WPP_SF_(v26[1].Flink, 1352, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
            (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1357, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
        if ( (unsigned int)IsPublicPhonebook((const char *)v10) )
        {
          v51 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1358, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
              WPP_SF_S(v53, 1365, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v54);
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
                  (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
              WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 1368, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v56);
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
                  WPP_SF_S(v59, 1370, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v52);
                }
                goto LABEL_267;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1369, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v57);
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1359, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1362, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
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
        WPP_SF_d(Flink, v39, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
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
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1329, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
          (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
    WPP_SF_d(v26[1].Flink, v27, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v22);
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
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1371, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
  }
  return result;
}

```

## disassembly

```asm
0x18002f250  push    rbp
0x18002f252  push    rbx
0x18002f253  push    rsi
0x18002f254  push    rdi
0x18002f255  push    r12
0x18002f257  push    r13
0x18002f259  push    r14
0x18002f25b  push    r15
0x18002f25d  lea     rbp, [rsp-1Fh]
0x18002f262  sub     rsp, 0B8h
0x18002f269  mov     rax, cs:__security_cookie
0x18002f270  xor     rax, rsp
0x18002f273  mov     [rbp+57h+var_48], rax
0x18002f277  mov     rbx, r8
0x18002f27a  mov     [rbp+57h+var_60], rbx
0x18002f27e  mov     rdi, cs:WPP_GLOBAL_Control
0x18002f285  lea     rax, WPP_GLOBAL_Control
0x18002f28c  cmp     rdi, rax
0x18002f28f  jz      short loc_18002F2BC
0x18002f291  test    dword ptr [rdi+1Ch], 2000h
0x18002f298  jz      short loc_18002F2BC
0x18002f29a  cmp     byte ptr [rdi+19h], 6
0x18002f29e  jb      short loc_18002F2BC
0x18002f2a0  mov     rcx, [rdi+10h]
0x18002f2a4  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f2ab  mov     edx, 52Ch
0x18002f2b0  call    WPP_SF_
0x18002f2b5  mov     rdi, cs:WPP_GLOBAL_Control
0x18002f2bc  movups  xmm0, xmmword ptr [rbx+410h]
0x18002f2c3  mov     r14d, [rbx+420h]
0x18002f2ca  lea     rsi, [rbx+4]
0x18002f2ce  mov     r13d, [rbx+424h]
0x18002f2d5  lea     rax, [rbx+428h]
0x18002f2dc  mov     r15d, [rbx+62Ch]
0x18002f2e3  lea     r12, [rbx+206h]
0x18002f2ea  xor     ebx, ebx
0x18002f2ec  mov     [rbp+57h+var_88], rsi
0x18002f2f0  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18002f2f5  mov     [rbp+57h+hMem], rax
0x18002f2f9  mov     [rbp+57h+var_78], 0
0x18002f300  mov     [rbp+57h+lpData], rbx
0x18002f304  mov     [rbp+57h+cbData], ebx
0x18002f307  mov     [rbp+57h+Type], ebx
0x18002f30a  mov     [rbp+57h+hKey], rbx
0x18002f30e  mov     dword ptr [rbp+57h+Data], 1
0x18002f315  lea     rdx, WPP_GLOBAL_Control
0x18002f31c  lea     rcx, aNull_5; "<NULL>"
0x18002f323  cmp     rdi, rdx
0x18002f326  jz      short loc_18002F3A4
0x18002f328  test    dword ptr [rdi+1Ch], 2000h
0x18002f32f  jz      short loc_18002F3A4
0x18002f331  cmp     byte ptr [rdi+19h], 5
0x18002f335  jb      short loc_18002F3A4
0x18002f337  test    rax, rax
0x18002f33a  mov     r11, rcx
0x18002f33d  mov     r10, rcx
0x18002f340  mov     r9, rcx
0x18002f343  cmovnz  r11, rax
0x18002f347  mov     edx, 52Dh
0x18002f34c  test    rsi, rsi
0x18002f34f  cmovnz  r10, rsi
0x18002f353  test    r12, r12
0x18002f356  cmovnz  r9, r12
0x18002f35a  test    r15d, r15d
0x18002f35d  setnz   r8b
0x18002f361  test    r13d, r13d
0x18002f364  mov     [rsp+0F0h+var_A8], r8b
0x18002f369  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f370  setnz   cl
0x18002f373  test    r14d, r14d
0x18002f376  mov     byte ptr [rsp+0F0h+lpdwDisposition], cl
0x18002f37a  mov     rcx, [rdi+10h]
0x18002f37e  setnz   al
0x18002f381  mov     byte ptr [rsp+0F0h+phkResult], al
0x18002f385  lea     rax, [rbp+57h+var_58]
0x18002f389  mov     [rsp+0F0h+lpSecurityAttributes], rax
0x18002f38e  mov     qword ptr [rsp+0F0h+samDesired], r11
0x18002f393  mov     qword ptr [rsp+0F0h+dwOptions], r10
0x18002f398  call    WPP_SF_SSS_guid_ccc
0x18002f39d  mov     rdi, cs:WPP_GLOBAL_Control
0x18002f3a4  test    r12, r12
0x18002f3a7  jz      loc_18003029F
0x18002f3ad  test    rsi, rsi
0x18002f3b0  jz      loc_18003029F
0x18002f3b6  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002f3bc  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x18002f3c1  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18002f3c8  test    al, al
0x18002f3ca  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18002f3d1  lea     rax, [rbp+57h+hKey]
0x18002f3d5  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002f3da  cmovz   rdx, rcx; lpSubKey
0x18002f3de  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002f3e3  xor     r9d, r9d; lpClass
0x18002f3e6  mov     [rsp+0F0h+samDesired], 20007h; samDesired
0x18002f3ee  xor     r8d, r8d; Reserved
0x18002f3f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f3f8  mov     [rsp+0F0h+dwOptions], ebx; dwOptions
0x18002f3fc  call    cs:__imp_RegCreateKeyExW
0x18002f402  mov     ebx, eax
0x18002f404  test    eax, eax
0x18002f406  jz      short loc_18002F459
0x18002f408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f40f  lea     r15, WPP_GLOBAL_Control
0x18002f416  mov     r13d, 2000h
0x18002f41c  cmp     rcx, r15
0x18002f41f  jz      loc_180030263
0x18002f425  test    [rcx+1Ch], r13d
0x18002f429  jz      loc_180030263
0x18002f42f  mov     sil, 2
0x18002f432  cmp     [rcx+19h], sil
0x18002f436  jb      loc_180030263
0x18002f43c  mov     edx, 52Fh
0x18002f441  mov     rcx, [rcx+10h]
0x18002f445  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f44c  mov     r9d, eax
0x18002f44f  call    WPP_SF_d
0x18002f454  jmp     loc_180030263
0x18002f459  mov     rdx, r12
0x18002f45c  mov     rcx, rsi
0x18002f45f  call    ProfileSatisifesLockDownPolicy
0x18002f464  mov     ebx, eax
0x18002f466  test    eax, eax
0x18002f468  jz      short loc_18002F4A5
0x18002f46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f471  lea     r15, WPP_GLOBAL_Control
0x18002f478  mov     r13d, 2000h
0x18002f47e  cmp     rcx, r15
0x18002f481  jz      loc_180030263
0x18002f487  test    [rcx+1Ch], r13d
0x18002f48b  jz      loc_180030263
0x18002f491  mov     sil, 2
0x18002f494  cmp     [rcx+19h], sil
0x18002f498  jb      loc_180030263
0x18002f49e  mov     edx, 530h
0x18002f4a3  jmp     short loc_18002F441
0x18002f4a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f4a9  lea     rax, [rbp+57h+cbData]
0x18002f4ad  xor     ebx, ebx
0x18002f4af  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x18002f4b4  lea     r9, [rbp+57h+Type]; lpType
0x18002f4b8  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x18002f4bd  xor     r8d, r8d; lpReserved
0x18002f4c0  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x18002f4c7  mov     edi, ebx
0x18002f4c9  call    cs:__imp_RegQueryValueExW
0x18002f4cf  mov     sil, 2
0x18002f4d2  test    eax, eax
0x18002f4d4  jnz     loc_18002F5FE
0x18002f4da  cmp     [rbp+57h+Type], 7
0x18002f4de  jnz     loc_18002F5FE
0x18002f4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4eb  lea     rax, WPP_GLOBAL_Control
0x18002f4f2  cmp     rcx, rax
0x18002f4f5  jz      short loc_18002F51B
0x18002f4f7  test    dword ptr [rcx+1Ch], 2000h
0x18002f4fe  jz      short loc_18002F51B
0x18002f500  cmp     byte ptr [rcx+19h], 4
0x18002f504  jb      short loc_18002F51B
0x18002f506  mov     rcx, [rcx+10h]
0x18002f50a  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f511  mov     edx, 531h
0x18002f516  call    WPP_SF_
0x18002f51b  mov     edx, [rbp+57h+cbData]; uBytes
0x18002f51e  mov     ecx, 40h ; '@'; uFlags
0x18002f523  call    cs:__imp_LocalAlloc
0x18002f529  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f52d  lea     r9, [rbp+57h+Type]; lpType
0x18002f531  mov     rbx, rax
0x18002f534  mov     [rbp+57h+lpData], rax
0x18002f538  lea     rax, [rbp+57h+cbData]
0x18002f53c  xor     r8d, r8d; lpReserved
0x18002f53f  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x18002f544  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x18002f54b  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x18002f550  call    cs:__imp_RegQueryValueExW
0x18002f556  test    eax, eax
0x18002f558  jnz     short loc_18002F5B6
0x18002f55a  cmp     [rbp+57h+Type], 7
0x18002f55e  jnz     loc_18002F638
0x18002f564  mov     r8, [rbp+57h+var_88]
0x18002f568  mov     rcx, rbx
0x18002f56b  mov     edx, [rbp+57h+cbData]
0x18002f56e  call    WideMultiStringListLookUp
0x18002f573  xor     ebx, ebx
0x18002f575  test    eax, eax
0x18002f577  jnz     short loc_18002F581
0x18002f579  lea     edi, [rbx+1]
0x18002f57c  jmp     loc_18002F638
0x18002f581  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f588  lea     rdx, WPP_GLOBAL_Control
0x18002f58f  cmp     rcx, rdx
0x18002f592  jz      loc_18002F68C
0x18002f598  test    dword ptr [rcx+1Ch], 2000h
0x18002f59f  jz      loc_18002F63F
0x18002f5a5  cmp     [rcx+19h], sil
0x18002f5a9  jb      loc_18002F63F
0x18002f5af  mov     edx, 532h
0x18002f5b4  jmp     short loc_18002F625
0x18002f5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5bd  lea     rdx, WPP_GLOBAL_Control
0x18002f5c4  cmp     rcx, rdx
0x18002f5c7  jz      loc_18002F68C
0x18002f5cd  test    dword ptr [rcx+1Ch], 2000h
0x18002f5d4  jz      short loc_18002F63F
0x18002f5d6  cmp     [rcx+19h], sil
0x18002f5da  jb      short loc_18002F63F
0x18002f5dc  mov     rcx, [rcx+10h]
0x18002f5e0  lea     r9, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x18002f5e7  mov     edx, 533h
0x18002f5ec  mov     [rsp+0F0h+dwOptions], eax
0x18002f5f0  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f5f7  call    WPP_SF_Sd
0x18002f5fc  jmp     short loc_18002F638
0x18002f5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f605  lea     rdx, WPP_GLOBAL_Control
0x18002f60c  cmp     rcx, rdx
0x18002f60f  jz      short loc_18002F68C
0x18002f611  test    dword ptr [rcx+1Ch], 2000h
0x18002f618  jz      short loc_18002F63F
0x18002f61a  cmp     byte ptr [rcx+19h], 4
0x18002f61e  jb      short loc_18002F63F
0x18002f620  mov     edx, 534h
0x18002f625  mov     rcx, [rcx+10h]
0x18002f629  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f630  mov     r9d, eax
0x18002f633  call    WPP_SF_d
0x18002f638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f63f  lea     rax, WPP_GLOBAL_Control
0x18002f646  cmp     rcx, rax
0x18002f649  jz      short loc_18002F693
0x18002f64b  test    dword ptr [rcx+1Ch], 2000h
0x18002f652  jz      short loc_18002F693
0x18002f654  cmp     byte ptr [rcx+19h], 5
0x18002f658  jb      short loc_18002F693
0x18002f65a  mov     rcx, [rcx+10h]
0x18002f65e  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f665  test    r15d, r15d
0x18002f668  mov     byte ptr [rsp+0F0h+samDesired], dil
0x18002f66d  mov     edx, 535h
0x18002f672  setnz   al
0x18002f675  test    r14d, r14d
0x18002f678  mov     byte ptr [rsp+0F0h+dwOptions], al
0x18002f67c  setnz   r9b
0x18002f680  call    WPP_SF_ccc
0x18002f685  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f68c  lea     rax, WPP_GLOBAL_Control
0x18002f693  xor     ebx, ebx
0x18002f695  test    r14d, r14d
0x18002f698  jz      loc_18002FA80
0x18002f69e  mov     r12d, 2000h
0x18002f6a4  cmp     rcx, rax
0x18002f6a7  jz      short loc_18002F6CA
0x18002f6a9  test    [rcx+1Ch], r12d
0x18002f6ad  jz      short loc_18002F6CA
0x18002f6af  cmp     byte ptr [rcx+19h], 5
0x18002f6b3  jb      short loc_18002F6CA
0x18002f6b5  mov     rcx, [rcx+10h]
0x18002f6b9  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f6c0  mov     edx, 536h
0x18002f6c5  call    WPP_SF_
0x18002f6ca  mov     r9d, r14d
0x18002f6cd  mov     [rsp+0F0h+dwOptions], 1; int
0x18002f6d5  xor     r8d, r8d; void *
0x18002f6d8  xor     edx, edx; void *
0x18002f6da  xor     ecx, ecx; Src
0x18002f6dc  call    VpnProfileActiveSet
0x18002f6e1  test    eax, eax
0x18002f6e3  jz      short loc_18002F71E
0x18002f6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6ec  lea     r14, WPP_GLOBAL_Control
0x18002f6f3  cmp     rcx, r14
0x18002f6f6  jz      short loc_18002F725
0x18002f6f8  test    [rcx+1Ch], r12d
0x18002f6fc  jz      short loc_18002F725
0x18002f6fe  cmp     [rcx+19h], sil
0x18002f702  jb      short loc_18002F725
0x18002f704  mov     rcx, [rcx+10h]
0x18002f708  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002f70f  mov     edx, 537h
0x18002f714  mov     r9d, eax
0x18002f717  call    WPP_SF_d
0x18002f71c  jmp     short loc_18002F725
0x18002f71e  lea     r14, WPP_GLOBAL_Control
0x18002f725  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f729  lea     rdx, aAutotriggerpro_2; "AutoTriggerProfilePhonebookPath"
0x18002f730  call    cs:__imp_RegDeleteValueW
0x18002f736  test    eax, eax
0x18002f738  jz      short loc_18002F772
0x18002f73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f741  cmp     rcx, r14
0x18002f744  jz      short loc_18002F772
0x18002f746  test    [rcx+1Ch], r12d
0x18002f74a  jz      short loc_18002F772
0x18002f74c  cmp     [rcx+19h], sil
0x18002f750  jb      short loc_18002F772
0x18002f752  mov     rcx, [rcx+10h]
0x18002f756  lea     r9, aAutotriggerpro_2; "AutoTriggerProfilePhonebookPath"
0x18002f75d  mov     edx, 538h
0x18002f762  mov     [rsp+0F0h+dwOptions], eax
  ... truncated ...
```
