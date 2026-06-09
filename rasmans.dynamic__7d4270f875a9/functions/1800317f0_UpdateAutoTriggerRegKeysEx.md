# UpdateAutoTriggerRegKeysEx

- ea: `0x1800317f0`
- end: `0x180032a28`
- name: `UpdateAutoTriggerRegKeysEx`
- size: `4664`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x18000ec50`
- `0x180012c24`
- `0x180017ec8`
- `0x18001a588`
- `0x1800317f0`
- `0x1800338d4`
- `0x180033ad8`
- `0x180034434`
- `0x180048180`
- `0x18005f6f4`
- `0x180069848`
- `0x180083b18`
- `0x1800df660`
- `0x1800e8ef0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180031960`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180031960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326cf`
- `RPCRT4!RpcImpersonateClient` at `0x18003262a`
- `RPCRT4!RpcImpersonateClient` at `0x18003262a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800326bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800326bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031f00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031fe9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032168`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032373`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003240b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800327da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003284d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031f00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031fe9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032168`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032373`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003240b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800327da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003284d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003249c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003249c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031d10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031d66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031dbc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031e1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800322f0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031d10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031d66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031dbc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031e1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800322f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800319c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800319c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031b2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031b2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031aff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800325c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031aff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800325c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003246b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003246b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032487`

## string_xrefs

- `0x180031970`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180031977`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180031987`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x180031980`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x180031db5`: `UserSID`
- `0x180031def`: `UserSID`
- `0x1800327c7`: `UserSID`
- `0x180031d09`: `AutoTriggerProfilePhonebookPath`
- `0x180031d3c`: `AutoTriggerProfilePhonebookPath`
- `0x18003235b`: `AutoTriggerProfilePhonebookPath`
- `0x1800323ba`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall UpdateAutoTriggerRegKeysEx(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rdi
  int v5; // esi
  BYTE *v6; // rdx
  int v7; // r14d
  int v8; // r13d
  BYTE *v9; // r12
  int v10; // r15d
  struct _LIST_ENTRY **v11; // r8
  const char *v12; // rcx
  const char *v13; // r11
  const char *v14; // r10
  const char *v15; // r9
  char IsStateSeparationEnabled; // al
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r9
  unsigned int UserSid; // ebx
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  int v25; // edi
  unsigned int v26; // eax
  LSTATUS v27; // eax
  struct _LIST_ENTRY *v28; // rcx
  __int64 v29; // rdx
  unsigned int active; // eax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  struct _LIST_ENTRY *v35; // rcx
  unsigned int v36; // eax
  LSTATUS v37; // eax
  BYTE *v38; // r14
  unsigned int v39; // eax
  LSTATUS v40; // eax
  __int64 v41; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  LSTATUS v43; // eax
  __int64 v44; // rdi
  __int64 v45; // rax
  DWORD LastError; // eax
  struct _LIST_ENTRY *v47; // rcx
  int v48; // edx
  const WCHAR *v49; // r9
  __int64 v50; // rax
  LSTATUS v51; // eax
  __int64 result; // rax
  int v53; // r13d
  BYTE *v54; // r15
  __int64 v55; // rax
  struct _LIST_ENTRY *v56; // rcx
  struct _LIST_ENTRY *v57; // rcx
  const char *v58; // r9
  const BYTE *v59; // rcx
  LSTATUS v60; // eax
  const char *v61; // rdi
  const char *v62; // r9
  unsigned int v63; // eax
  struct _LIST_ENTRY *v64; // rcx
  struct _LIST_ENTRY *v65; // rcx
  int dwOptions; // [rsp+20h] [rbp-99h]
  int samDesired; // [rsp+28h] [rbp-91h]
  DWORD cbData; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  DWORD Type; // [rsp+70h] [rbp-49h] BYREF
  BYTE *v71; // [rsp+78h] [rbp-41h]
  int v72; // [rsp+80h] [rbp-39h]
  BYTE *lpData; // [rsp+88h] [rbp-31h] BYREF
  int v74; // [rsp+90h] [rbp-29h]
  HLOCAL hMem; // [rsp+98h] [rbp-21h]
  BYTE Data[8]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int *v77; // [rsp+A8h] [rbp-11h]
  BYTE v78[16]; // [rsp+B0h] [rbp-9h] BYREF

  v77 = (unsigned int *)a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1372, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD *)(a3 + 1580);
  v6 = (BYTE *)(a3 + 4);
  v7 = *(_DWORD *)(a3 + 1056);
  v8 = *(_DWORD *)(a3 + 1060);
  v9 = (BYTE *)(a3 + 518);
  v10 = *(_DWORD *)(a3 + 1584);
  *(_OWORD *)v78 = *(_OWORD *)(a3 + 1040);
  v71 = (BYTE *)(a3 + 4);
  hMem = (HLOCAL)(a3 + 1064);
  v74 = 0;
  v72 = v5;
  lpData = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  *(_DWORD *)Data = 1;
  v11 = &WPP_GLOBAL_Control;
  v12 = L"<NULL>";
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 5u )
  {
    v13 = L"<NULL>";
    v14 = L"<NULL>";
    v15 = L"<NULL>";
    if ( a3 != -1064 )
      v13 = (const char *)(a3 + 1064);
    if ( a3 != -4 )
      v14 = (const char *)(a3 + 4);
    if ( a3 != -518 )
      LODWORD(v15) = a3 + 518;
    LOBYTE(v11) = v5 != 0;
    LOBYTE(v6) = v10 != 0;
    WPP_SF_SSS_guid_cccc(
      v4[1].Flink,
      (_DWORD)v6,
      (_DWORD)v11,
      (_DWORD)v15,
      (__int64)v14,
      (__int64)v13,
      (__int64)v78,
      v7 != 0,
      v8 != 0,
      v10 != 0,
      v5 != 0);
    v6 = v71;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a3 == -518 || !v6 )
  {
    UserSid = 87;
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v4[1].Blink) & 0x2000) == 0
      || BYTE1(v4[1].Blink) < 2u )
    {
      goto LABEL_194;
    }
    Flink = v4[1].Flink;
    v41 = 1374;
    goto LABEL_170;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v12);
  if ( v5 )
  {
    v17 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    v18 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  }
  else
  {
    v18 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
    v17 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  }
  if ( !IsStateSeparationEnabled )
    v18 = v17;
  v19 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0, 0, 0x20007u, 0, &hKey, 0);
  UserSid = v19;
  if ( v19 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v23 = 1375;
LABEL_27:
      WPP_SF_d(v22[1].Flink, v23, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v19);
      goto LABEL_194;
    }
    goto LABEL_194;
  }
  if ( !v5 || (v19 = ProfileSatisifesLockDownPolicy(v71, v9), (UserSid = v19) == 0) )
  {
    v24 = v72;
    v25 = 0;
    if ( v72 )
    {
      v26 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, 0, &cbData);
      if ( v26 || Type != 7 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
        {
LABEL_59:
          if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v28[1].Blink) & 0x2000) != 0
            && BYTE1(v28[1].Blink) >= 5u )
          {
            LOBYTE(samDesired) = v25;
            LOBYTE(dwOptions) = v10 != 0;
            LOBYTE(v20) = v7 != 0;
            WPP_SF_ccc(v28[1].Flink, 1381, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v20, dwOptions, samDesired);
            v28 = WPP_GLOBAL_Control;
          }
LABEL_63:
          if ( v7 )
          {
            if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v28[1].Blink) & 0x2000) != 0
              && BYTE1(v28[1].Blink) >= 5u )
            {
              WPP_SF_(v28[1].Flink, 1382, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            }
            active = VpnProfileActiveSet(0, 0, 0, v24);
            if ( active
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1383, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, active);
            }
            v31 = RegDeleteValueW(hKey, L"AutoTriggerProfilePhonebookPath");
            if ( v31
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1384,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)L"AutoTriggerProfilePhonebookPath",
                v31);
            }
            v32 = RegDeleteValueW(hKey, L"AutoTriggerProfileEntryName");
            if ( v32
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1385,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)L"AutoTriggerProfileEntryName",
                v32);
            }
            v33 = RegDeleteValueW(hKey, L"UserSID");
            if ( v33
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1386,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)L"UserSID",
                v33);
            }
            v34 = RegDeleteValueW(hKey, L"AutoTriggerProfileGUID");
            UserSid = v34;
            if ( v34 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1387,
                  (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  (unsigned int)L"AutoTriggerProfileGUID",
                  v34);
                v35 = WPP_GLOBAL_Control;
              }
              UserSid = 0;
            }
            else
            {
              v35 = WPP_GLOBAL_Control;
            }
            if ( !v72 || !v10 )
              goto LABEL_118;
            if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v35[1].Blink) & 0x2000) != 0
              && BYTE1(v35[1].Blink) >= 4u )
            {
              WPP_SF_(v35[1].Flink, 1388, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              v35 = WPP_GLOBAL_Control;
            }
            if ( v25 )
              goto LABEL_118;
            v36 = AddWStringToWMultiStringStart(&lpData, &cbData, v71);
            UserSid = 0;
            if ( v36 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_118;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1391, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v36);
            }
            else
            {
              v37 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
              UserSid = v37;
              if ( v37 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control[1].Flink,
                    1389,
                    (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                    (unsigned int)L"AutoTriggerDisabledProfilesList",
                    v37);
                  v35 = WPP_GLOBAL_Control;
                }
                UserSid = 0;
                goto LABEL_118;
              }
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
              {
LABEL_118:
                if ( v8 )
                {
                  UserSid = RegSetValueExW(hKey, L"AutoTriggeringDisabled", 0, 4u, Data, 4u);
                  if ( UserSid )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
                    {
                      WPP_SF_S(
                        WPP_GLOBAL_Control[1].Flink,
                        1392,
                        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                        L"AutoTriggeringDisabled");
                      v35 = WPP_GLOBAL_Control;
                    }
                    UserSid = 0;
                  }
                  else
                  {
                    v35 = WPP_GLOBAL_Control;
                  }
                }
                if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v35[1].Blink) & 0x2000) != 0
                  && BYTE1(v35[1].Blink) >= 4u )
                {
                  WPP_SF_(v35[1].Flink, 1393, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
                }
                goto LABEL_192;
              }
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1390, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            }
            v35 = WPP_GLOBAL_Control;
            goto LABEL_118;
          }
          if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v28[1].Blink) & 0x2000) != 0
            && BYTE1(v28[1].Blink) >= 5u )
          {
            WPP_SF_(v28[1].Flink, 1394, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v10 && v24 )
          {
            if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(v28[1].Blink) & 0x2000) != 0 && BYTE1(v28[1].Blink) >= 5u )
              {
                WPP_SF_(v28[1].Flink, 1395, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
                v28 = WPP_GLOBAL_Control;
              }
              if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v28[1].Blink) & 0x2000) != 0
                && BYTE1(v28[1].Blink) >= 4u )
              {
                WPP_SF_(v28[1].Flink, 1396, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              }
            }
            v38 = v71;
            if ( v25 )
            {
              v39 = DeleteWStringFromWMultiString(&lpData, &cbData, v71);
              if ( v39 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1399, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v39);
                }
              }
              else
              {
                v40 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
                if ( v40 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_Sd(
                      WPP_GLOBAL_Control[1].Flink,
                      1397,
                      (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                      (unsigned int)L"AutoTriggerDisabledProfilesList",
                      v40);
                  }
                }
                else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                       && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1398, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
                }
              }
            }
          }
          else
          {
            if ( v25 && v24 )
            {
              if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v28[1].Blink) & 0x2000) != 0
                && BYTE1(v28[1].Blink) >= 5u )
              {
                WPP_SF_(v28[1].Flink, 1400, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
                v28 = WPP_GLOBAL_Control;
              }
              UserSid = 1206;
              if ( v28 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(v28[1].Blink) & 0x2000) == 0
                || BYTE1(v28[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v41 = 1401;
              goto LABEL_169;
            }
            v38 = v71;
          }
          v43 = RegDeleteValueW(hKey, L"AutoTriggeringDisabled");
          if ( v43
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control[1].Flink,
              1402,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (unsigned int)L"AutoTriggeringDisabled",
              v43);
          }
          v44 = -1;
          v45 = -1;
          do
            ++v45;
          while ( *(_WORD *)&v9[2 * v45] );
          LastError = RegSetValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, 1u, v9, 2 * v45 + 2);
          UserSid = LastError;
          if ( LastError )
          {
            v47 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v48 = 1403;
              v49 = L"AutoTriggerProfilePhonebookPath";
LABEL_184:
              WPP_SF_Sd(
                v47[1].Flink,
                v48,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (_DWORD)v49,
                LastError);
            }
LABEL_192:
            if ( lpData )
              LocalFree(lpData);
            goto LABEL_194;
          }
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)&v38[2 * v50] );
          v51 = RegSetValueExW(hKey, L"AutoTriggerProfileEntryName", 0, 1u, v38, 2 * v50 + 2);
          UserSid = v51;
          if ( v51 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1404,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)L"AutoTriggerProfileEntryName",
                v51);
            }
            goto LABEL_192;
          }
          v53 = v72;
          v54 = (BYTE *)hMem;
          if ( !v72 )
          {
            v59 = (const BYTE *)L"S-1-5-80-4176366874-305252471-2256717057-2714189771-3552532790";
            do
LABEL_256:
              ++v44;
            while ( *(_WORD *)&v54[2 * v44] );
            UserSid = RegSetValueExW(hKey, L"UserSID", 0, 1u, v59, 2 * v44 + 2);
            if ( UserSid )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1414,
                  (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  (unsigned int)L"AutoTriggerProfileEntryName",
                  UserSid);
              }
              goto LABEL_192;
            }
            v60 = RegSetValueExW(hKey, L"AutoTriggerProfileGUID", 0, 3u, v78, 0x10u);
            UserSid = v60;
            if ( v60 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1415,
                  (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  (unsigned int)L"AutoTriggerProfileGUID",
                  v60);
              }
              goto LABEL_192;
            }
            v61 = L"<NULL>";
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              v62 = L"<NULL>";
              if ( v54 )
                v62 = (const char *)v54;
              WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 1416, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v62);
            }
            v63 = VpnProfileActiveSet(v9, v71, v54, v53);
            UserSid = v63;
            if ( v63 )
            {
              v64 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                goto LABEL_192;
              if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
LABEL_279:
                if ( v64 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v64[1].Blink) & 0x2000) != 0
                  && BYTE1(v64[1].Blink) >= 5u )
                {
                  v65 = v64[1].Flink;
                  if ( v54 )
                    v61 = (const char *)v54;
                  WPP_SF_S(v65, 1418, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v61);
                }
                goto LABEL_192;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1417, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v63);
            }
            v64 = WPP_GLOBAL_Control;
            goto LABEL_279;
          }
          if ( hMem )
          {
            v55 = -1;
            do
              ++v55;
            while ( *((_WORD *)hMem + v55) );
            if ( v55 )
            {
LABEL_254:
              v59 = v54;
              goto LABEL_256;
            }
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1405, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          if ( (unsigned int)IsPublicPhonebook(v9) )
          {
            v56 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1406, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              v56 = WPP_GLOBAL_Control;
            }
            v54 = (BYTE *)L"S-1-1-0";
            hMem = (HLOCAL)L"S-1-1-0";
            goto LABEL_248;
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1407, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          hMem = LocalAlloc(0x40u, 0x1388u);
          v54 = (BYTE *)hMem;
          v74 = 1;
          if ( hMem )
          {
            LastError = RpcImpersonateClient(g_hRpcHandle);
            UserSid = LastError;
            if ( LastError )
            {
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v48 = 1409;
            }
            else
            {
              UserSid = GetUserSid(v54);
              if ( UserSid
                && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1410, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
              }
              if ( RevertToSelf() )
              {
                if ( !UserSid )
                {
                  v56 = WPP_GLOBAL_Control;
LABEL_248:
                  if ( v56 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v56[1].Blink) & 0x2000) != 0
                    && BYTE1(v56[1].Blink) >= 5u )
                  {
                    v57 = v56[1].Flink;
                    v58 = L"<NULL>";
                    if ( v54 )
                      v58 = (const char *)v54;
                    WPP_SF_S(v57, 1413, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v58);
                  }
                  goto LABEL_254;
                }
                v28 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                {
                  goto LABEL_192;
                }
                v41 = 1412;
                goto LABEL_169;
              }
              LastError = GetLastError();
              UserSid = LastError;
              if ( !LastError )
                goto LABEL_192;
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v48 = 1411;
            }
            LODWORD(v49) = (_DWORD)v9;
            goto LABEL_184;
          }
          UserSid = 8;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_192;
          }
          v41 = 1408;
LABEL_169:
          Flink = v28[1].Flink;
LABEL_170:
          WPP_SF_d(Flink, v41, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
          goto LABEL_192;
        }
        v29 = 1380;
        goto LABEL_57;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1377, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      lpData = (BYTE *)LocalAlloc(0x40u, cbData);
      v27 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, lpData, &cbData);
      if ( v27 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_59;
        WPP_SF_Sd(
          WPP_GLOBAL_Control[1].Flink,
          1379,
          (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          (unsigned int)L"AutoTriggerDisabledProfilesList",
          v27);
        goto LABEL_58;
      }
      if ( Type == 7 )
      {
        v26 = WideMultiStringListLookUp(lpData, cbData, v71);
        if ( !v26 )
        {
          v25 = 1;
          goto LABEL_58;
        }
        v25 = 0;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_59;
        v29 = 1378;
LABEL_57:
        WPP_SF_d(v28[1].Flink, v29, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v26);
      }
    }
LABEL_58:
    v28 = WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v23 = 1376;
    goto LABEL_27;
  }
LABEL_194:
  if ( hMem && v74 )
    LocalFree(hMem);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  *v77 = UserSid;
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
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1419, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, UserSid);
  }
  return result;
}

```

## disassembly

```asm
0x1800317f0  push    rbp
0x1800317f2  push    rbx
0x1800317f3  push    rsi
0x1800317f4  push    rdi
0x1800317f5  push    r12
0x1800317f7  push    r13
0x1800317f9  push    r14
0x1800317fb  push    r15
0x1800317fd  lea     rbp, [rsp-1Fh]
0x180031802  sub     rsp, 0D8h
0x180031809  mov     rax, cs:__security_cookie
0x180031810  xor     rax, rsp
0x180031813  mov     [rbp+57h+var_50], rax
0x180031817  mov     rbx, r8
0x18003181a  mov     [rbp+57h+var_68], rbx
0x18003181e  mov     rdi, cs:WPP_GLOBAL_Control
0x180031825  lea     rax, WPP_GLOBAL_Control
0x18003182c  cmp     rdi, rax
0x18003182f  jz      short loc_18003185C
0x180031831  test    dword ptr [rdi+1Ch], 2000h
0x180031838  jz      short loc_18003185C
0x18003183a  cmp     byte ptr [rdi+19h], 6
0x18003183e  jb      short loc_18003185C
0x180031840  mov     rcx, [rdi+10h]
0x180031844  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18003184b  mov     edx, 55Ch
0x180031850  call    WPP_SF_
0x180031855  mov     rdi, cs:WPP_GLOBAL_Control
0x18003185c  movups  xmm0, xmmword ptr [rbx+410h]
0x180031863  mov     esi, [rbx+62Ch]
0x180031869  lea     rdx, [rbx+4]
0x18003186d  mov     r14d, [rbx+420h]
0x180031874  lea     rax, [rbx+428h]
0x18003187b  mov     r13d, [rbx+424h]
0x180031882  lea     r12, [rbx+206h]
0x180031889  mov     r15d, [rbx+630h]
0x180031890  xor     ebx, ebx
0x180031892  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180031897  mov     [rbp+57h+var_98], rdx
0x18003189b  mov     [rbp+57h+hMem], rax
0x18003189f  mov     [rbp+57h+var_80], 0
0x1800318a6  mov     [rbp+57h+var_90], esi
0x1800318a9  mov     [rbp+57h+lpData], rbx
0x1800318ad  mov     [rbp+57h+cbData], ebx
0x1800318b0  mov     [rbp+57h+Type], ebx
0x1800318b3  mov     [rbp+57h+hKey], rbx
0x1800318b7  mov     dword ptr [rbp+57h+Data], 1
0x1800318be  lea     r8, WPP_GLOBAL_Control
0x1800318c5  lea     rcx, aNull_4; "<NULL>"
0x1800318cc  cmp     rdi, r8
0x1800318cf  jz      short loc_18003194E
0x1800318d1  test    dword ptr [rdi+1Ch], 2000h
0x1800318d8  jz      short loc_18003194E
0x1800318da  cmp     byte ptr [rdi+19h], 5
0x1800318de  jb      short loc_18003194E
0x1800318e0  test    rax, rax
0x1800318e3  mov     r11, rcx
0x1800318e6  mov     r10, rcx
0x1800318e9  mov     r9, rcx
0x1800318ec  cmovnz  r11, rax
0x1800318f0  test    rdx, rdx
0x1800318f3  cmovnz  r10, rdx
0x1800318f7  test    r12, r12
0x1800318fa  cmovnz  r9, r12
0x1800318fe  test    esi, esi
0x180031900  setnz   r8b
0x180031904  test    r15d, r15d
0x180031907  mov     [rsp+110h+var_C0], r8b
0x18003190c  setnz   dl
0x18003190f  test    r13d, r13d
0x180031912  mov     [rsp+110h+var_C8], dl
0x180031916  setnz   cl
0x180031919  test    r14d, r14d
0x18003191c  mov     byte ptr [rsp+110h+lpdwDisposition], cl
0x180031920  mov     rcx, [rdi+10h]
0x180031924  setnz   al
0x180031927  mov     byte ptr [rsp+110h+phkResult], al
0x18003192b  lea     rax, [rbp+57h+var_60]
0x18003192f  mov     [rsp+110h+lpSecurityAttributes], rax
0x180031934  mov     qword ptr [rsp+110h+samDesired], r11
0x180031939  mov     qword ptr [rsp+110h+dwOptions], r10
0x18003193e  call    WPP_SF_SSS_guid_cccc
0x180031943  mov     rdx, [rbp+57h+var_98]
0x180031947  mov     rdi, cs:WPP_GLOBAL_Control
0x18003194e  test    r12, r12
0x180031951  jz      loc_180032989
0x180031957  test    rdx, rdx
0x18003195a  jz      loc_180032989
0x180031960  call    cs:__imp_RtlIsStateSeparationEnabled
0x180031967  nop     dword ptr [rax+rax+00h]
0x18003196c  test    esi, esi
0x18003196e  jz      short loc_180031980
0x180031970  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180031977  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18003197e  jmp     short loc_18003198E
0x180031980  lea     rdx, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180031987  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18003198e  mov     [rsp+110h+lpdwDisposition], rbx; lpdwDisposition
0x180031993  test    al, al
0x180031995  lea     rax, [rbp+57h+hKey]
0x180031999  mov     [rsp+110h+phkResult], rax; phkResult
0x18003199e  cmovz   rdx, rcx; lpSubKey
0x1800319a2  mov     [rsp+110h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800319a7  xor     r9d, r9d; lpClass
0x1800319aa  mov     [rsp+110h+samDesired], 20007h; samDesired
0x1800319b2  xor     r8d, r8d; Reserved
0x1800319b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800319bc  mov     [rsp+110h+dwOptions], ebx; dwOptions
0x1800319c0  call    cs:__imp_RegCreateKeyExW
0x1800319c7  nop     dword ptr [rax+rax+00h]
0x1800319cc  xor     ecx, ecx
0x1800319ce  mov     ebx, eax
0x1800319d0  test    eax, eax
0x1800319d2  jz      short loc_180031A22
0x1800319d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319db  lea     r14, WPP_GLOBAL_Control
0x1800319e2  cmp     rcx, r14
0x1800319e5  jz      loc_180032477
0x1800319eb  test    dword ptr [rcx+1Ch], 2000h
0x1800319f2  jz      loc_180032477
0x1800319f8  mov     sil, 2
0x1800319fb  cmp     [rcx+19h], sil
0x1800319ff  jb      loc_180032477
0x180031a05  mov     edx, 55Fh
0x180031a0a  mov     rcx, [rcx+10h]
0x180031a0e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031a15  mov     r9d, eax
0x180031a18  call    WPP_SF_d
0x180031a1d  jmp     loc_180032477
0x180031a22  test    esi, esi
0x180031a24  jz      short loc_180031A72
0x180031a26  mov     rcx, [rbp+57h+var_98]
0x180031a2a  mov     rdx, r12
0x180031a2d  call    ProfileSatisifesLockDownPolicy
0x180031a32  xor     ecx, ecx
0x180031a34  mov     ebx, eax
0x180031a36  test    eax, eax
0x180031a38  jz      short loc_180031A72
0x180031a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a41  lea     r14, WPP_GLOBAL_Control
0x180031a48  cmp     rcx, r14
0x180031a4b  jz      loc_180032477
0x180031a51  test    dword ptr [rcx+1Ch], 2000h
0x180031a58  jz      loc_180032477
0x180031a5e  mov     sil, 2
0x180031a61  cmp     [rcx+19h], sil
0x180031a65  jb      loc_180032477
0x180031a6b  mov     edx, 560h
0x180031a70  jmp     short loc_180031A0A
0x180031a72  mov     ebx, [rbp+57h+var_90]
0x180031a75  mov     edi, ecx
0x180031a77  mov     sil, 2
0x180031a7a  test    ebx, ebx
0x180031a7c  jz      loc_180031C1E
0x180031a82  lea     rax, [rbp+57h+cbData]
0x180031a86  xor     r8d, r8d; lpReserved
0x180031a89  mov     qword ptr [rsp+110h+samDesired], rax; lpcbData
0x180031a8e  lea     r9, [rbp+57h+Type]; lpType
0x180031a92  mov     qword ptr [rsp+110h+dwOptions], rcx; lpData
0x180031a97  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x180031a9e  mov     rcx, [rbp+57h+hKey]; hKey
0x180031aa2  call    cs:__imp_RegQueryValueExW
0x180031aa9  nop     dword ptr [rax+rax+00h]
0x180031aae  test    eax, eax
0x180031ab0  jnz     loc_180031BE4
0x180031ab6  cmp     [rbp+57h+Type], 7
0x180031aba  jnz     loc_180031BE4
0x180031ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ac7  lea     rax, WPP_GLOBAL_Control
0x180031ace  cmp     rcx, rax
0x180031ad1  jz      short loc_180031AF7
0x180031ad3  test    dword ptr [rcx+1Ch], 2000h
0x180031ada  jz      short loc_180031AF7
0x180031adc  cmp     byte ptr [rcx+19h], 4
0x180031ae0  jb      short loc_180031AF7
0x180031ae2  mov     rcx, [rcx+10h]
0x180031ae6  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031aed  mov     edx, 561h
0x180031af2  call    WPP_SF_
0x180031af7  mov     edx, [rbp+57h+cbData]; uBytes
0x180031afa  mov     ecx, 40h ; '@'; uFlags
0x180031aff  call    cs:__imp_LocalAlloc
0x180031b06  nop     dword ptr [rax+rax+00h]
0x180031b0b  lea     rcx, [rbp+57h+cbData]
0x180031b0f  xor     r8d, r8d; lpReserved
0x180031b12  lea     r9, [rbp+57h+Type]; lpType
0x180031b16  mov     [rbp+57h+lpData], rax
0x180031b1a  mov     qword ptr [rsp+110h+samDesired], rcx; lpcbData
0x180031b1f  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x180031b26  mov     rcx, [rbp+57h+hKey]; hKey
0x180031b2a  mov     qword ptr [rsp+110h+dwOptions], rax; lpData
0x180031b2f  call    cs:__imp_RegQueryValueExW
0x180031b36  nop     dword ptr [rax+rax+00h]
0x180031b3b  test    eax, eax
0x180031b3d  jnz     short loc_180031B9C
0x180031b3f  cmp     [rbp+57h+Type], 7
0x180031b43  jnz     loc_180031C1E
0x180031b49  mov     r8, [rbp+57h+var_98]
0x180031b4d  mov     edx, [rbp+57h+cbData]
0x180031b50  mov     rcx, [rbp+57h+lpData]
0x180031b54  call    WideMultiStringListLookUp
0x180031b59  test    eax, eax
0x180031b5b  jnz     short loc_180031B65
0x180031b5d  lea     edi, [rax+1]
0x180031b60  jmp     loc_180031C1E
0x180031b65  xor     edi, edi
0x180031b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b6e  lea     r8, WPP_GLOBAL_Control
0x180031b75  cmp     rcx, r8
0x180031b78  jz      loc_180031C72
0x180031b7e  test    dword ptr [rcx+1Ch], 2000h
0x180031b85  jz      loc_180031C25
0x180031b8b  cmp     [rcx+19h], sil
0x180031b8f  jb      loc_180031C25
0x180031b95  mov     edx, 562h
0x180031b9a  jmp     short loc_180031C0B
0x180031b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ba3  lea     r8, WPP_GLOBAL_Control
0x180031baa  cmp     rcx, r8
0x180031bad  jz      loc_180031C72
0x180031bb3  test    dword ptr [rcx+1Ch], 2000h
0x180031bba  jz      short loc_180031C25
0x180031bbc  cmp     [rcx+19h], sil
0x180031bc0  jb      short loc_180031C25
0x180031bc2  mov     rcx, [rcx+10h]
0x180031bc6  lea     r9, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x180031bcd  mov     edx, 563h
0x180031bd2  mov     [rsp+110h+dwOptions], eax
0x180031bd6  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031bdd  call    WPP_SF_Sd
0x180031be2  jmp     short loc_180031C1E
0x180031be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180031beb  lea     rdx, WPP_GLOBAL_Control
0x180031bf2  cmp     rcx, rdx
0x180031bf5  jz      short loc_180031C72
0x180031bf7  test    dword ptr [rcx+1Ch], 2000h
0x180031bfe  jz      short loc_180031C25
0x180031c00  cmp     byte ptr [rcx+19h], 4
0x180031c04  jb      short loc_180031C25
0x180031c06  mov     edx, 564h
0x180031c0b  mov     rcx, [rcx+10h]
0x180031c0f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031c16  mov     r9d, eax
0x180031c19  call    WPP_SF_d
0x180031c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c25  lea     rax, WPP_GLOBAL_Control
0x180031c2c  cmp     rcx, rax
0x180031c2f  jz      short loc_180031C72
0x180031c31  test    dword ptr [rcx+1Ch], 2000h
0x180031c38  jz      short loc_180031C72
0x180031c3a  cmp     byte ptr [rcx+19h], 5
0x180031c3e  jb      short loc_180031C72
0x180031c40  mov     rcx, [rcx+10h]
0x180031c44  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031c4b  test    r15d, r15d
0x180031c4e  mov     byte ptr [rsp+110h+samDesired], dil
0x180031c53  mov     edx, 565h
0x180031c58  setnz   al
0x180031c5b  test    r14d, r14d
0x180031c5e  mov     byte ptr [rsp+110h+dwOptions], al
0x180031c62  setnz   r9b
0x180031c66  call    WPP_SF_ccc
0x180031c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c72  test    r14d, r14d
0x180031c75  jz      loc_18003207F
0x180031c7b  lea     rax, WPP_GLOBAL_Control
0x180031c82  mov     r12d, 2000h
0x180031c88  cmp     rcx, rax
0x180031c8b  jz      short loc_180031CAE
0x180031c8d  test    [rcx+1Ch], r12d
0x180031c91  jz      short loc_180031CAE
0x180031c93  cmp     byte ptr [rcx+19h], 5
0x180031c97  jb      short loc_180031CAE
0x180031c99  mov     rcx, [rcx+10h]
0x180031c9d  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031ca4  mov     edx, 566h
0x180031ca9  call    WPP_SF_
0x180031cae  mov     r9d, r14d
0x180031cb1  mov     [rsp+110h+dwOptions], ebx; int
0x180031cb5  xor     r8d, r8d; void *
0x180031cb8  xor     edx, edx; void *
0x180031cba  xor     ecx, ecx; Src
0x180031cbc  call    VpnProfileActiveSet
0x180031cc1  test    eax, eax
0x180031cc3  jz      short loc_180031CFE
0x180031cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ccc  lea     r14, WPP_GLOBAL_Control
0x180031cd3  cmp     rcx, r14
0x180031cd6  jz      short loc_180031D05
0x180031cd8  test    [rcx+1Ch], r12d
0x180031cdc  jz      short loc_180031D05
0x180031cde  cmp     [rcx+19h], sil
0x180031ce2  jb      short loc_180031D05
0x180031ce4  mov     rcx, [rcx+10h]
0x180031ce8  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180031cef  mov     edx, 567h
0x180031cf4  mov     r9d, eax
0x180031cf7  call    WPP_SF_d
0x180031cfc  jmp     short loc_180031D05
0x180031cfe  lea     r14, WPP_GLOBAL_Control
  ... truncated ...
```
