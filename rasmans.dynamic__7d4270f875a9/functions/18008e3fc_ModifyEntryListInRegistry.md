# ModifyEntryListInRegistry

- ea: `0x18008e3fc`
- end: `0x1800907a2`
- name: `ModifyEntryListInRegistry`
- size: `9126`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f488`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x18005fbf4`
- `0x180060830`
- `0x180061064`
- `0x18007ff30`
- `0x180080430`
- `0x180085100`
- `0x18008e0f4`
- `0x18008e3bc`
- `0x18008e3fc`
- `0x1800907a8`
- `0x180090938`
- `0x180090ba4`
- `0x180090c1c`
- `0x180092320`
- `0x18009239c`
- `0x180092b0c`
- `0x180092bd4`
- `0x180092cc8`
- `0x180092d58`
- `0x180092f58`
- `0x180093010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008e64c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008e64c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fdc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fde7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800905d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009064b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fdc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fde7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fe9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800905d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009064b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e595`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e626`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e693`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fd3e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e595`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e626`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008e693`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fd3e`

## string_xrefs

- `0x18008e937`: `RedialAttempts`
- `0x18008e9a4`: `RedialOnLinkFailure`
- `0x18008e9e6`: `CustomDialDll`
- `0x18008e807`: `ExcludedProtocols`
- `0x18008e832`: `LcpExtensions`
- `0x18008e87e`: `SwCompression`
- `0x18008e8a9`: `NegotiateMultilinkAlways`
- `0x18008ec2d`: `PreferredProtocol`
- `0x18008ec55`: `PreferredCompression`
- `0x18008ea28`: `CustomRasDialDll`
- `0x18008ea48`: `ForceSecureCompartment`
- `0x18008ee3f`: `IpHeaderCompression`
- `0x18008ec91`: `PreferredMdmProtocol`
- `0x18008ed59`: `ShowMonitorIconInTaskBar`
- `0x18008f298`: `ImsConfig`
- `0x18008f347`: `CacheCredentials`
- `0x18008f7f8`: `ApnInfoCompression`
- `0x18008f823`: `DeviceComplianceEnabled`
- `0x18008f84e`: `DeviceComplianceSsoEnabled`
- `0x18008f86f`: `DeviceComplianceSsoEku`
- `0x18008f890`: `DeviceComplianceSsoIssuer`
- `0x18008f728`: `SecurityDescriptor`
- `0x18008f7ac`: `ApnInfoAccessPoint`
- `0x18008fae5`: `AutoConfigScript`
- `0x18008f9f9`: `PowershellCreatedProfile`
- `0x18008fc8b`: `PluginStorage`

## pseudocode

```c
__int64 __fastcall ModifyEntryListInRegistry(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rsi
  struct _LIST_ENTRY *v4; // rcx
  __int64 *v5; // rax
  unsigned int ProvisionedProfilePath; // ebx
  int v7; // r15d
  __int64 v8; // r13
  __int64 v9; // rdi
  _DWORD *v10; // r14
  int v11; // eax
  WCHAR *v12; // rsi
  const WCHAR *v13; // rcx
  __int64 result; // rax
  HGLOBAL v15; // rsi
  __int64 v16; // rax
  void *v17; // rsi
  unsigned int v18; // eax
  unsigned int inserted; // eax
  const char *v20; // r8
  const char *v21; // r8
  __int64 v22; // r8
  const char *v23; // r8
  const char *v24; // r8
  const char *v25; // r8
  const char *v26; // r8
  const char *v27; // r8
  const char *v28; // r8
  const char *v29; // r8
  const char *v30; // r8
  const char *v31; // r8
  const char *v32; // r8
  const char *v33; // r8
  const char *v34; // r8
  const char *v35; // r8
  const char *v36; // r8
  const char *v37; // r8
  const char *v38; // r8
  const char *v39; // r8
  const char *v40; // r8
  const char *v41; // r8
  __int64 v42; // r8
  const char *v43; // r8
  const char *v44; // r8
  const WCHAR *v45; // r8
  const WCHAR *v46; // r8
  const WCHAR *v47; // r8
  const WCHAR *v48; // r8
  const WCHAR *v49; // r8
  const WCHAR *v50; // r8
  const char *v51; // r8
  const WCHAR *v52; // r8
  const WCHAR *v53; // r8
  const char *v54; // r8
  const char *v55; // r8
  const char *v56; // r8
  const char *v57; // r8
  __int64 v58; // r8
  __int64 v59; // r8
  __int64 v60; // r9
  const char *v61; // r8
  __int64 v62; // r8
  __int64 v63; // r9
  const char *v64; // r8
  const char *v65; // r8
  __int64 v66; // r8
  __int64 v67; // r8
  const char *v68; // r8
  void *v69; // rcx
  HGLOBAL v70; // rsi
  unsigned int v71; // eax
  void *v72; // rcx
  HGLOBAL v73; // rsi
  const char *v74; // r8
  const char *v75; // r8
  const char *v76; // r8
  const char *v77; // r8
  __int64 v78; // r8
  __int64 v79; // r8
  __int64 v80; // r8
  const char *v81; // r8
  const char *v82; // r8
  const char *v83; // r8
  const char *v84; // r8
  const char *v85; // r8
  __int64 v86; // rdx
  __int64 v87; // r8
  const char *v88; // r8
  const char *v89; // r8
  const char *v90; // r8
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 *v93; // rax
  __int64 v94; // r14
  __int64 v95; // rsi
  __int64 v96; // rax
  void *v97; // r15
  __int64 v98; // r8
  struct _LIST_ENTRY *v99; // rcx
  __int64 v100; // rdx
  __int64 v101; // r9
  struct _LIST_ENTRY *v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rdx
  unsigned int v105; // edi
  HKEY hKey; // [rsp+20h] [rbp-38h] BYREF
  HGLOBAL hMem; // [rsp+28h] [rbp-30h]
  __int64 v108; // [rsp+30h] [rbp-28h]
  HKEY v109; // [rsp+38h] [rbp-20h] BYREF
  HGLOBAL v110; // [rsp+40h] [rbp-18h]
  int v111; // [rsp+A0h] [rbp+48h]
  HKEY v113; // [rsp+B0h] [rbp+58h] BYREF
  HKEY v114; // [rsp+B8h] [rbp+60h] BYREF

  v2 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 134, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(__int64 **)(a1 + 16);
  ProvisionedProfilePath = 0;
  v7 = 0;
  hKey = 0;
  v113 = 0;
  v111 = 0;
  v8 = *v5;
  if ( !*v5 )
    goto LABEL_519;
  while ( 1 )
  {
    v9 = *(_QWORD *)(v8 + 16);
    v10 = (_DWORD *)(v9 + 540);
    if ( !*(_DWORD *)(v9 + 532) && !*v10 )
      goto LABEL_15;
    v11 = *(_DWORD *)(a1 + 32) & 0x100;
    if ( v11 && *(_DWORD *)(v9 + 548) )
    {
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
        WPP_SF_S(v4[1].Flink, 135, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, *(_QWORD *)(v9 + 8));
      *(_DWORD *)(v9 + 532) = 0;
      *(_DWORD *)(v9 + 540) = 0;
      v4 = WPP_GLOBAL_Control;
      goto LABEL_15;
    }
    v110 = 0;
    v108 = 0;
    hMem = 0;
    if ( *(_DWORD *)(v9 + 548) && *(_DWORD *)(a1 + 8) != 4 )
    {
      ProvisionedProfilePath = GetProvisionedProfilePath(*(STRSAFE_LPCWSTR *)a1, *(STRSAFE_LPCWSTR *)(v9 + 8));
      if ( ProvisionedProfilePath )
        goto LABEL_515;
      v12 = (WCHAR *)hMem;
      goto LABEL_26;
    }
    v13 = *(const WCHAR **)a1;
    if ( v11 )
    {
      ProvisionedProfilePath = GetLUAPhonebookPath(v13);
      if ( ProvisionedProfilePath )
        goto LABEL_515;
      v12 = (WCHAR *)hMem;
    }
    else
    {
      v12 = (WCHAR *)StrDup(v13);
    }
    if ( !v12 )
      break;
LABEL_26:
    ProvisionedProfilePath = RegistryPathConverter(v12);
    if ( v12 )
      GlobalFree(v12);
    result = 235;
    if ( ProvisionedProfilePath == 235 )
      return result;
    v15 = v110;
    if ( !(unsigned int)RegSetKeySecurityInfo((LPCSTR)v110) )
      goto LABEL_34;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 137, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
LABEL_34:
      v4 = WPP_GLOBAL_Control;
    }
    if ( ProvisionedProfilePath )
    {
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 2u )
      {
        v104 = 138;
        goto LABEL_528;
      }
      return ProvisionedProfilePath;
    }
    ProvisionedProfilePath = CreateOrOpenSubkey(v108, v15, &hKey);
    if ( v15 )
      GlobalFree(v15);
    if ( ProvisionedProfilePath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v104 = 139;
        goto LABEL_528;
      }
      return ProvisionedProfilePath;
    }
    UpdateEntryTimeStamp(v9);
    RegDeleteTreeW(hKey, *(LPCWSTR *)(v9 + 8));
    if ( !*v10 )
    {
      v16 = StrdupWtoA(*(LPCWCH *)(v9 + 8));
      v17 = (void *)v16;
      if ( v16 )
      {
        v18 = CreateOrOpenSubkey(hKey, v16, &v113);
        ProvisionedProfilePath = v18;
        if ( !v18 )
        {
          GlobalFree(v17);
          inserted = RegInsertLong(v113, "Encoding", 1);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 142;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "PBVersion", 8);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 143;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "Type", *(unsigned int *)(v9 + 24));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 144;
            goto LABEL_484;
          }
          v20 = "1";
          if ( !*(_DWORD *)(v9 + 176) )
            v20 = "0";
          inserted = RegInsertStringA(v113, "AutoLogon", v20);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 145;
            goto LABEL_484;
          }
          v21 = "1";
          if ( !*(_DWORD *)(v9 + 180) )
            v21 = "0";
          inserted = RegInsertStringA(v113, "UseRasCredentials", v21);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 146;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "LowDateTime", *(unsigned int *)(v9 + 16));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 147;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "HighDateTime", *(unsigned int *)(v9 + 20));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 148;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "DialParamsUID", *(unsigned int *)(v9 + 456));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 149;
            goto LABEL_484;
          }
          v22 = *(_QWORD *)(v9 + 464);
          if ( v22 )
          {
            inserted = RegInsertBinary(v113, "Guid", v22, 16);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v99 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v100 = 150;
                goto LABEL_484;
              }
              goto LABEL_490;
            }
          }
          inserted = RegInsertLong(v113, "VpnStrategy", *(unsigned int *)(v9 + 168));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 151;
            goto LABEL_484;
          }
          inserted = RegInsertLong(v113, "ExcludedProtocols", *(unsigned int *)(v9 + 236));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 152;
            goto LABEL_484;
          }
          v23 = "1";
          if ( !*(_DWORD *)(v9 + 240) )
            v23 = "0";
          inserted = RegInsertStringA(v113, "LcpExtensions", v23);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 153;
LABEL_484:
            v101 = inserted;
            goto LABEL_485;
          }
          inserted = RegInsertLong(v113, "DataEncryption", *(unsigned int *)(v9 + 172));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_490;
            }
            v100 = 154;
            goto LABEL_484;
          }
          v24 = "1";
          if ( !*(_DWORD *)(v9 + 244) )
            v24 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "SwCompression", v24);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v25 = "1";
          if ( !*(_DWORD *)(v9 + 248) )
            v25 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "NegotiateMultilinkAlways", v25);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v26 = "1";
          if ( !*(_DWORD *)(v9 + 252) )
            v26 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "SkipDoubleDialDialog", v26);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "DialMode", *(unsigned int *)(v9 + 132));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "OverridePref", *(unsigned int *)(v9 + 144));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "RedialAttempts", *(unsigned int *)(v9 + 148));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "RedialSeconds", *(unsigned int *)(v9 + 152));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IdleDisconnectSeconds", *(unsigned int *)(v9 + 156));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v27 = "1";
          if ( !*(_DWORD *)(v9 + 160) )
            v27 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "RedialOnLinkFailure", v27);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "CallbackMode", *(unsigned int *)(v9 + 420));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "CustomDialDll", *(_QWORD *)(v9 + 432));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "CustomDialFunc", *(_QWORD *)(v9 + 440));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "CustomRasDialDll", *(_QWORD *)(v9 + 448));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          *(_DWORD *)(v9 + 184) = 0;
          ProvisionedProfilePath = RegInsertStringA(v113, "ForceSecureCompartment", "0");
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v28 = "1";
          if ( !*(_DWORD *)(v9 + 188) )
            v28 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DisableIKENameEkuCheck", v28);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v29 = "1";
          if ( !*(_DWORD *)(v9 + 424) )
            v29 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "AuthenticateServer", v29);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v30 = "1";
          if ( !*(_DWORD *)(v9 + 256) )
            v30 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "ShareMsFilePrint", v30);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v31 = "1";
          if ( !*(_DWORD *)(v9 + 260) )
            v31 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "BindMsNetClient", v31);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v32 = "1";
          if ( !*(_DWORD *)(v9 + 40) )
            v32 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "SharedPhoneNumbers", v32);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v33 = "1";
          if ( !*(_DWORD *)(v9 + 44) )
            v33 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "GlobalDeviceSettings", v33);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "PrerequisiteEntry", *(_QWORD *)(v9 + 56));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "PrerequisitePbk", *(_QWORD *)(v9 + 64));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "PreferredPort", *(_QWORD *)(v9 + 72));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "PreferredDevice", *(_QWORD *)(v9 + 80));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "PreferredBps", *(unsigned int *)(v9 + 88));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v34 = "1";
          if ( !*(_DWORD *)(v9 + 92) )
            v34 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreferredHwFlow", v34);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v35 = "1";
          if ( !*(_DWORD *)(v9 + 96) )
            v35 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreferredProtocol", v35);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v36 = "1";
          if ( !*(_DWORD *)(v9 + 100) )
            v36 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreferredCompression", v36);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "PreferredSpeaker", *(unsigned int *)(v9 + 104));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "PreferredMdmProtocol", *(unsigned int *)(v9 + 108));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v37 = "1";
          if ( !*(_DWORD *)(v9 + 116) )
            v37 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreviewUserPw", v37);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v38 = "1";
          if ( !*(_DWORD *)(v9 + 120) )
            v38 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreviewDomain", v38);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v39 = "1";
          if ( !*(_DWORD *)(v9 + 124) )
            v39 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PreviewPhoneNumber", v39);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v40 = "1";
          if ( !*(_DWORD *)(v9 + 112) )
            v40 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "ShowDialingProgress", v40);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v41 = "1";
          if ( !*(_DWORD *)(v9 + 48) )
            v41 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "ShowMonitorIconInTaskBar", v41);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "CustomAuthKey", *(unsigned int *)(v9 + 192));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v42 = *(_QWORD *)(v9 + 200);
          if ( v42 )
          {
            ProvisionedProfilePath = RegInsertBinary(v113, "CustomAuthData", v42, *(unsigned int *)(v9 + 208));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "AuthRestrictions", *(unsigned int *)(v9 + 164));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v43 = "1";
          if ( !*(_DWORD *)(v9 + 272) )
            v43 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "IpPrioritizeRemote", v43);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpInterfaceMetric", *(unsigned int *)(v9 + 352));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v44 = "1";
          if ( !*(_DWORD *)(v9 + 276) )
            v44 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "IpHeaderCompression", v44);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v45 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 280) )
            v45 = *(const WCHAR **)(v9 + 280);
          ProvisionedProfilePath = RegInsertString(v113, "IpAddress", v45);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v46 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 288) )
            v46 = *(const WCHAR **)(v9 + 288);
          ProvisionedProfilePath = RegInsertString(v113, "IpDnsAddress", v46);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v47 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 296) )
            v47 = *(const WCHAR **)(v9 + 296);
          ProvisionedProfilePath = RegInsertString(v113, "IpDns2Address", v47);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v48 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 304) )
            v48 = *(const WCHAR **)(v9 + 304);
          ProvisionedProfilePath = RegInsertString(v113, "IpWinsAddress", v48);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v49 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 312) )
            v49 = *(const WCHAR **)(v9 + 312);
          ProvisionedProfilePath = RegInsertString(v113, "IpWins2Address", v49);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpAssign", *(unsigned int *)(v9 + 320));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpNameAssign", *(unsigned int *)(v9 + 324));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpDnsFlags", *(unsigned int *)(v9 + 328));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpNBTFlags", *(unsigned int *)(v9 + 332));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "TcpWindowSize", *(unsigned int *)(v9 + 336));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "UseFlags", *(unsigned int *)(v9 + 136));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "IpSecFlags", *(unsigned int *)(v9 + 140));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "IpDnsSuffix", *(_QWORD *)(v9 + 344));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "Ipv6Assign", *(unsigned int *)(v9 + 356));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v50 = L"::";
          if ( *(_QWORD *)(v9 + 360) )
            v50 = *(const WCHAR **)(v9 + 360);
          ProvisionedProfilePath = RegInsertString(v113, "Ipv6Address", v50);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "Ipv6PrefixLength", *(unsigned int *)(v9 + 368));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v51 = "1";
          if ( !*(_DWORD *)(v9 + 372) )
            v51 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "Ipv6PrioritizeRemote", v51);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "Ipv6InterfaceMetric", *(unsigned int *)(v9 + 416));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "Ipv6NameAssign", *(unsigned int *)(v9 + 376));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v52 = L"::";
          if ( *(_QWORD *)(v9 + 384) )
            v52 = *(const WCHAR **)(v9 + 384);
          ProvisionedProfilePath = RegInsertString(v113, "Ipv6DnsAddress", v52);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v53 = L"::";
          if ( *(_QWORD *)(v9 + 392) )
            v53 = *(const WCHAR **)(v9 + 392);
          ProvisionedProfilePath = RegInsertString(v113, "Ipv6Dns2Address", v53);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertBinary(v113, "Ipv6Prefix", v9 + 408, 8);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertBinary(v113, "Ipv6InterfaceId", v9 + 400, 8);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v54 = "1";
          if ( !*(_DWORD *)(v9 + 544) )
            v54 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DisableClassBasedDefaultRoute", v54);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v55 = "1";
          if ( !*(_DWORD *)(v9 + 488) )
            v55 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DisableMobility", v55);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "NetworkOutageTime", *(unsigned int *)(v9 + 492));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          if ( (unsigned int)RegInsertString(v113, "IDI", *(_QWORD *)(v9 + 496)) )
          {
            inserted = 1;
            ProvisionedProfilePath = 1;
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 155;
              goto LABEL_484;
            }
LABEL_490:
            RegCloseKey(v113);
LABEL_500:
            RegCloseKey(hKey);
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v104 = 179;
              goto LABEL_528;
            }
            return ProvisionedProfilePath;
          }
          if ( (unsigned int)RegInsertString(v113, "IDR", *(_QWORD *)(v9 + 504)) )
          {
            inserted = 1;
            ProvisionedProfilePath = 1;
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 156;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v56 = "1";
          if ( !*(_DWORD *)(v9 + 512) )
            v56 = "0";
          inserted = RegInsertStringA(v113, "ImsConfig", v56);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 157;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          inserted = RegInsertLong(v113, "IdiType", *(unsigned int *)(v9 + 516));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 158;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          inserted = RegInsertLong(v113, "IdrType", *(unsigned int *)(v9 + 520));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 159;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "ProvisionType", *(unsigned int *)(v9 + 548));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "PreSharedKey", *(_QWORD *)(v9 + 552));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v57 = "1";
          if ( !*(_DWORD *)(v9 + 128) )
            v57 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "CacheCredentials", v57);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "NumCustomPolicy", *(unsigned int *)(v9 + 596));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v58 = *(_QWORD *)(v9 + 608);
          if ( v58 )
          {
            if ( *(_DWORD *)(v9 + 596) )
            {
              ProvisionedProfilePath = RegInsertBinary(v113, "CustomIPSecPolicies", v58, *(unsigned int *)(v9 + 600));
              if ( ProvisionedProfilePath )
                goto LABEL_490;
            }
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumEku", *(unsigned int *)(v9 + 616));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v59 = *(_QWORD *)(v9 + 624);
          if ( v59 )
          {
            if ( *(_DWORD *)(v9 + 616) )
            {
              v60 = *(unsigned int *)(v9 + 620);
              if ( (_DWORD)v60 )
              {
                ProvisionedProfilePath = RegInsertBinary(v113, "CertificateEKU", v59, v60);
                if ( ProvisionedProfilePath )
                  goto LABEL_490;
              }
            }
          }
          v61 = "1";
          if ( !*(_DWORD *)(v9 + 632) )
            v61 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "UseMachineRootCert", v61);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          if ( *(_DWORD *)(v9 + 632) == 1 )
          {
            v62 = *(_QWORD *)(v9 + 648);
            if ( v62 )
            {
              v63 = *(unsigned int *)(v9 + 640);
              if ( (_DWORD)v63 )
              {
                ProvisionedProfilePath = RegInsertBinary(v113, "RootCertificate", v62, v63);
                if ( ProvisionedProfilePath )
                  goto LABEL_490;
              }
            }
          }
          v64 = "1";
          if ( !*(_DWORD *)(v9 + 524) )
            v64 = "0";
          inserted = RegInsertStringA(v113, "Disable_IKEv2_Fragmentation", v64);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 160;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v65 = "1";
          if ( !*(_DWORD *)(v9 + 528) )
            v65 = "0";
          inserted = RegInsertStringA(v113, "PlumbIKEv2TSAsRoutes", v65);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 161;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumServers", *(unsigned int *)(v9 + 656));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          if ( *(_QWORD *)(v9 + 664) )
          {
            if ( *(_DWORD *)(v9 + 656) )
            {
              inserted = RegCreateServerLists(v113);
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v99 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v100 = 162;
                  goto LABEL_484;
                }
                goto LABEL_490;
              }
            }
          }
          inserted = RegInsertLong(v113, "RouteVersion", 1);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 163;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          inserted = RegInsertLong(v113, "NumRoutes", *(unsigned int *)(v9 + 672));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 164;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v66 = *(_QWORD *)(v9 + 680);
          if ( v66 )
          {
            if ( *(_DWORD *)(v9 + 672) )
            {
              inserted = RegInsertBinary(v113, "Routes", v66, *(unsigned int *)(v9 + 676));
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v99 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v100 = 165;
                  goto LABEL_484;
                }
                goto LABEL_490;
              }
            }
          }
          inserted = RegInsertLong(v113, "NumNrptRules", *(unsigned int *)(v9 + 688));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 166;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v67 = *(_QWORD *)(v9 + 696);
          if ( v67 )
          {
            if ( *(_DWORD *)(v9 + 688) )
            {
              inserted = RegInsertBinary(v113, "NrptRules", v67, *(unsigned int *)(v9 + 692));
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v99 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v100 = 167;
                  goto LABEL_484;
                }
                goto LABEL_490;
              }
            }
          }
          v68 = "1";
          if ( !*(_DWORD *)(v9 + 704) )
            v68 = "0";
          inserted = RegInsertStringA(v113, "AutoTiggerCapable", v68);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 168;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumAppIds", *(unsigned int *)(v9 + 728));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v69 = *(void **)(v9 + 736);
          if ( v69 && *(_DWORD *)(v9 + 728) )
          {
            v110 = 0;
            inserted = RegCreateDtlList(v69);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v99 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v100 = 169;
                goto LABEL_484;
              }
              goto LABEL_490;
            }
            v70 = v110;
            v71 = RegInsertStringList(v113, "ApplicationIds");
            ProvisionedProfilePath = v71;
            if ( v71 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 170, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v71);
              }
              DtlDestroyList(v70);
              goto LABEL_490;
            }
            DtlDestroyList(v70);
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumClassicAppIds", *(unsigned int *)(v9 + 708));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v72 = *(void **)(v9 + 720);
          if ( v72 && *(_DWORD *)(v9 + 708) )
          {
            v110 = 0;
            inserted = RegCreateDtlList(v72);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v99 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v100 = 171;
                goto LABEL_484;
              }
              goto LABEL_490;
            }
            v73 = v110;
            ProvisionedProfilePath = RegInsertStringList(v113, "ClassicApplicationIds");
            if ( ProvisionedProfilePath )
            {
              DtlDestroyList(v73);
              v99 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_490;
              }
              v100 = 172;
              v101 = ProvisionedProfilePath;
LABEL_485:
              WPP_SF_d(v99[1].Flink, v100, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v101);
              goto LABEL_490;
            }
            DtlDestroyList(v73);
          }
          inserted = RegInsertString(v113, "SecurityDescriptor", *(_QWORD *)(v9 + 744));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 173;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertString(v113, "ApnInfoProviderId", *(_QWORD *)(v9 + 864));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "ApnInfoUsername", *(_QWORD *)(v9 + 880));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "ApnInfoPassword", *(_QWORD *)(v9 + 888));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "ApnInfoAccessPoint", *(_QWORD *)(v9 + 872));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "ApnInfoAuthentication", *(unsigned int *)(v9 + 900));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v74 = "1";
          if ( !*(_DWORD *)(v9 + 896) )
            v74 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "ApnInfoCompression", v74);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v75 = "1";
          if ( !*(_DWORD *)(v9 + 904) )
            v75 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DeviceComplianceEnabled", v75);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v76 = "1";
          if ( !*(_DWORD *)(v9 + 912) )
            v76 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DeviceComplianceSsoEnabled", v76);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "DeviceComplianceSsoEku", *(_QWORD *)(v9 + 920));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertString(v113, "DeviceComplianceSsoIssuer", *(_QWORD *)(v9 + 928));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "FlagsSet", *(unsigned int *)(v9 + 952));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "Options", *(unsigned int *)(v9 + 956));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v77 = "1";
          if ( !*(_DWORD *)(v9 + 788) )
            v77 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "DisableDefaultDnsSuffixes", v77);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "NumTrustedNetworks", *(unsigned int *)(v9 + 792));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v78 = *(_QWORD *)(v9 + 800);
          if ( v78 )
          {
            if ( *(_DWORD *)(v9 + 792) )
            {
              ProvisionedProfilePath = RegInsertBinary(v113, "TrustedNetworks", v78, *(unsigned int *)(v9 + 796));
              if ( ProvisionedProfilePath )
                goto LABEL_490;
            }
          }
          v79 = *(_QWORD *)(v9 + 760);
          if ( v79 )
          {
            ProvisionedProfilePath = RegInsertBinary(v113, "ThirdPartyProfileInfo", v79, *(unsigned int *)(v9 + 752));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumDnsSearchSuffixes", *(unsigned int *)(v9 + 768));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v80 = *(_QWORD *)(v9 + 776);
          if ( v80 )
          {
            ProvisionedProfilePath = RegInsertBinary(v113, "DnsSuffixSearchList", v80, *(unsigned int *)(v9 + 772));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          v81 = "1";
          if ( !*(_DWORD *)(v9 + 784) )
            v81 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PowershellCreatedProfile", v81);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          ProvisionedProfilePath = RegInsertLong(v113, "ProxyFlags", *(unsigned int *)(v9 + 560));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v82 = "1";
          if ( !*(_DWORD *)(v9 + 820) )
            v82 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "ProxySettingsModified", v82);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          if ( (*(_BYTE *)(v9 + 560) & 2) != 0 )
          {
            ProvisionedProfilePath = RegInsertString(v113, "Proxy", *(_QWORD *)(v9 + 576));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
            ProvisionedProfilePath = RegInsertString(v113, "ExcludeList", *(_QWORD *)(v9 + 584));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
            v83 = "1";
            if ( !*(_DWORD *)(v9 + 592) )
              v83 = "0";
            ProvisionedProfilePath = RegInsertStringA(v113, "BypassProxyForLocal", v83);
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          if ( (*(_BYTE *)(v9 + 560) & 4) != 0 )
          {
            ProvisionedProfilePath = RegInsertString(v113, "AutoConfigScript", *(_QWORD *)(v9 + 568));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertString(v113, "ProvisioningAuthority", *(_QWORD *)(v9 + 808));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v84 = "1";
          if ( !*(_DWORD *)(v9 + 816) )
            v84 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "AuthTypeOTP", v84);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v85 = "1";
          if ( !*(_DWORD *)(v9 + 824) )
            v85 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "GREKeyDefined", v85);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          if ( *(_DWORD *)(v9 + 824) )
          {
            ProvisionedProfilePath = RegInsertULong(v113, v86, *(unsigned int *)(v9 + 828));
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          ProvisionedProfilePath = RegInsertLong(v113, "NumPerAppTrafficFilters", *(unsigned int *)(v9 + 832));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v87 = *(_QWORD *)(v9 + 840);
          if ( v87 )
          {
            if ( *(_DWORD *)(v9 + 832) )
            {
              ProvisionedProfilePath = RegInsertBinary(v113, "PerAppTrafficFilters", v87, *(unsigned int *)(v9 + 836));
              if ( ProvisionedProfilePath )
                goto LABEL_490;
            }
          }
          v88 = "1";
          if ( !*(_DWORD *)(v9 + 848) )
            v88 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "AlwaysOnCapable", v88);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v89 = "1";
          if ( !*(_DWORD *)(v9 + 856) )
            v89 = "0";
          inserted = RegInsertStringA(v113, "DeviceTunnel", v89);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 174;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v90 = "1";
          if ( !*(_DWORD *)(v9 + 852) )
            v90 = "0";
          ProvisionedProfilePath = RegInsertStringA(v113, "PrivateNetwork", v90);
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          v91 = *(_QWORD *)(v9 + 944);
          if ( v91 )
          {
            v92 = *(unsigned int *)(v9 + 936);
            if ( (_DWORD)v92 )
            {
              ProvisionedProfilePath = RegInsertBinary(v113, "PluginStorage", v91, v92);
              if ( ProvisionedProfilePath )
                goto LABEL_490;
            }
          }
          ProvisionedProfilePath = RegInsertString(v113, "ManagementApp", *(_QWORD *)(v9 + 960));
          if ( ProvisionedProfilePath )
            goto LABEL_490;
          RegInsertNetComponents(v113, *(_QWORD *)(v9 + 264));
          v109 = 0;
          inserted = CreateOrOpenSubkey(v113, "MEDIA", &v109);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v99 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v100 = 175;
              goto LABEL_484;
            }
            goto LABEL_490;
          }
          v93 = *(__int64 **)(v9 + 32);
          v114 = 0;
          v94 = *v93;
          if ( *v93 )
          {
            while ( 1 )
            {
              v95 = *(_QWORD *)(v94 + 16);
              v96 = StrdupWtoA(*(LPCWCH *)(v95 + 24));
              v97 = (void *)v96;
              if ( !v96 )
                break;
              ProvisionedProfilePath = CreateOrOpenSubkey(v109, v96, &v114);
              if ( ProvisionedProfilePath )
                goto LABEL_345;
              GlobalFree(v97);
              ProvisionedProfilePath = RegInsertString(v114, "Port", *(_QWORD *)v95);
              if ( ProvisionedProfilePath
                || (v98 = *(_QWORD *)(v95 + 16)) != 0
                && (ProvisionedProfilePath = RegInsertString(v114, "Device", v98)) != 0
                || (*(_DWORD *)(v95 + 40) == 3 || (*(_BYTE *)(v95 + 48) & 4) != 0)
                && (ProvisionedProfilePath = RegInsertLong(v114, "ConnectBPS", *(unsigned int *)(v95 + 104))) != 0
                || (ProvisionedProfilePath = RegInsertDeviceList(a1, v114, v9, v95)) != 0 )
              {
                RegCloseKey(v114);
LABEL_345:
                v7 = v111;
                goto LABEL_346;
              }
              RegCloseKey(v114);
              v94 = *(_QWORD *)(v94 + 8);
              if ( !v94 )
                goto LABEL_345;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 176, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 8);
            }
            v7 = v111;
          }
LABEL_346:
          RegCloseKey(v109);
          if ( *(_DWORD *)(v9 + 548) )
          {
            ProvisionedProfilePath = RegInsertProxySettings(v113, v9);
            if ( ProvisionedProfilePath )
              goto LABEL_490;
          }
          *(_DWORD *)(v9 + 532) = 0;
          RegCloseKey(v113);
          goto LABEL_350;
        }
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_500;
        }
        v103 = 141;
      }
      else
      {
        v18 = 8;
        ProvisionedProfilePath = 8;
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_500;
        }
        v103 = 140;
      }
      WPP_SF_d(v102[1].Flink, v103, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v18);
      goto LABEL_500;
    }
    v111 = ++v7;
LABEL_350:
    RegCloseKey(hKey);
    v4 = WPP_GLOBAL_Control;
LABEL_15:
    v8 = *(_QWORD *)(v8 + 8);
    if ( !v8 )
    {
      if ( ProvisionedProfilePath )
        goto LABEL_524;
      v2 = a2;
LABEL_519:
      v105 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) - v7;
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_d(v4[1].Flink, 177, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v105);
        v4 = WPP_GLOBAL_Control;
      }
      *v2 = v105;
LABEL_524:
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
      {
        v104 = 178;
LABEL_528:
        WPP_SF_d(v4[1].Flink, v104, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, ProvisionedProfilePath);
      }
      return ProvisionedProfilePath;
    }
  }
  ProvisionedProfilePath = 8;
LABEL_515:
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v104 = 136;
    goto LABEL_528;
  }
  return ProvisionedProfilePath;
}

```

## disassembly

```asm
0x18008e3fc  mov     [rsp-40h+arg_8], rdx
0x18008e401  push    rbp
0x18008e402  push    rbx
0x18008e403  push    rsi
0x18008e404  push    rdi
0x18008e405  push    r12
0x18008e407  push    r13
0x18008e409  push    r14
0x18008e40b  push    r15
0x18008e40d  mov     rbp, rsp
0x18008e410  sub     rsp, 58h
0x18008e414  mov     rsi, rdx
0x18008e417  mov     r12, rcx
0x18008e41a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e421  lea     rdx, WPP_GLOBAL_Control
0x18008e428  cmp     rcx, rdx
0x18008e42b  jz      short loc_18008E45C
0x18008e42d  test    byte ptr [rcx+1Ch], 80h
0x18008e431  jz      short loc_18008E45C
0x18008e433  cmp     byte ptr [rcx+19h], 6
0x18008e437  jb      short loc_18008E45C
0x18008e439  mov     rcx, [rcx+10h]
0x18008e43d  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008e444  mov     edx, 86h
0x18008e449  call    WPP_SF_
0x18008e44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e455  lea     rdx, WPP_GLOBAL_Control
0x18008e45c  mov     rax, [r12+10h]
0x18008e461  xor     ebx, ebx
0x18008e463  xor     r15d, r15d
0x18008e466  mov     [rbp+hKey], rbx
0x18008e46a  mov     [rbp+arg_10], rbx
0x18008e46e  mov     [rbp+arg_0], r15d
0x18008e472  mov     r13, [rax]
0x18008e475  test    r13, r13
0x18008e478  jz      loc_180090721
0x18008e47e  xor     esi, esi
0x18008e480  mov     rdi, [r13+10h]
0x18008e484  lea     r14, [rdi+21Ch]
0x18008e48b  cmp     [rdi+214h], esi
0x18008e491  jnz     short loc_18008E498
0x18008e493  cmp     [r14], esi
0x18008e496  jz      short loc_18008E4E9
0x18008e498  mov     eax, [r12+20h]
0x18008e49d  and     eax, 100h
0x18008e4a2  jz      short loc_18008E509
0x18008e4a4  cmp     [rdi+224h], esi
0x18008e4aa  jz      short loc_18008E509
0x18008e4ac  cmp     rcx, rdx
0x18008e4af  jz      short loc_18008E4D6
0x18008e4b1  test    byte ptr [rcx+1Ch], 80h
0x18008e4b5  jz      short loc_18008E4D6
0x18008e4b7  cmp     byte ptr [rcx+19h], 5
0x18008e4bb  jb      short loc_18008E4D6
0x18008e4bd  mov     r9, [rdi+8]
0x18008e4c1  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008e4c8  mov     rcx, [rcx+10h]
0x18008e4cc  mov     edx, 87h
0x18008e4d1  call    WPP_SF_S
0x18008e4d6  mov     [rdi+214h], esi
0x18008e4dc  mov     [rdi+21Ch], esi
0x18008e4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e4e9  lea     r14, WPP_GLOBAL_Control
0x18008e4f0  mov     r13, [r13+8]
0x18008e4f4  test    r13, r13
0x18008e4f7  jz      loc_180090685
0x18008e4fd  lea     rdx, WPP_GLOBAL_Control
0x18008e504  jmp     loc_18008E480
0x18008e509  mov     [rbp+var_18], rsi
0x18008e50d  mov     [rbp+var_28], rsi
0x18008e511  mov     [rbp+hMem], rsi
0x18008e515  cmp     [rdi+224h], esi
0x18008e51b  jz      short loc_18008E546
0x18008e51d  cmp     dword ptr [r12+8], 4
0x18008e523  jz      short loc_18008E546
0x18008e525  mov     rdx, [rdi+8]; STRSAFE_LPCWSTR
0x18008e529  lea     r8, [rbp+hMem]
0x18008e52d  mov     rcx, [r12]; pszSrc
0x18008e531  call    GetProvisionedProfilePath
0x18008e536  mov     ebx, eax
0x18008e538  test    eax, eax
0x18008e53a  jnz     loc_1800906F7
0x18008e540  mov     rsi, [rbp+hMem]
0x18008e544  jmp     short loc_18008E578
0x18008e546  mov     rcx, [r12]; pszSrc
0x18008e54a  test    eax, eax
0x18008e54c  jz      short loc_18008E567
0x18008e54e  lea     rdx, [rbp+hMem]
0x18008e552  call    GetLUAPhonebookPath
0x18008e557  mov     ebx, eax
0x18008e559  test    eax, eax
0x18008e55b  jnz     loc_1800906F7
0x18008e561  mov     rsi, [rbp+hMem]
0x18008e565  jmp     short loc_18008E56F
0x18008e567  call    StrDup
0x18008e56c  mov     rsi, rax
0x18008e56f  test    rsi, rsi
0x18008e572  jz      loc_1800906F2
0x18008e578  lea     r9, [rbp+var_18]
0x18008e57c  mov     rdx, r12
0x18008e57f  lea     r8, [rbp+var_28]
0x18008e583  mov     rcx, rsi; lpWideCharStr
0x18008e586  call    RegistryPathConverter
0x18008e58b  mov     ebx, eax
0x18008e58d  test    rsi, rsi
0x18008e590  jz      short loc_18008E5A1
0x18008e592  mov     rcx, rsi; hMem
0x18008e595  call    cs:__imp_GlobalFree
0x18008e59c  nop     dword ptr [rax+rax+00h]
0x18008e5a1  mov     eax, 0EBh
0x18008e5a6  cmp     ebx, eax
0x18008e5a8  jz      loc_180090790
0x18008e5ae  mov     rsi, [rbp+var_18]
0x18008e5b2  mov     rdx, [rbp+var_28]
0x18008e5b6  mov     rcx, rsi; lpSubKey
0x18008e5b9  call    RegSetKeySecurityInfo
0x18008e5be  test    eax, eax
0x18008e5c0  jz      short loc_18008E5F6
0x18008e5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e5c9  lea     rax, WPP_GLOBAL_Control
0x18008e5d0  cmp     rcx, rax
0x18008e5d3  jz      short loc_18008E604
0x18008e5d5  test    byte ptr [rcx+1Ch], 80h
0x18008e5d9  jz      short loc_18008E604
0x18008e5db  cmp     byte ptr [rcx+19h], 2
0x18008e5df  jb      short loc_18008E604
0x18008e5e1  mov     rcx, [rcx+10h]
0x18008e5e5  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008e5ec  mov     edx, 89h
0x18008e5f1  call    WPP_SF_
0x18008e5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e5fd  lea     rax, WPP_GLOBAL_Control
0x18008e604  test    ebx, ebx
0x18008e606  jnz     loc_1800906CB
0x18008e60c  mov     rcx, [rbp+var_28]
0x18008e610  lea     r8, [rbp+hKey]
0x18008e614  mov     rdx, rsi
0x18008e617  call    CreateOrOpenSubkey
0x18008e61c  mov     ebx, eax
0x18008e61e  test    rsi, rsi
0x18008e621  jz      short loc_18008E632
0x18008e623  mov     rcx, rsi; hMem
0x18008e626  call    cs:__imp_GlobalFree
0x18008e62d  nop     dword ptr [rax+rax+00h]
0x18008e632  xor     esi, esi
0x18008e634  test    ebx, ebx
0x18008e636  jnz     loc_180090696
0x18008e63c  mov     rcx, rdi
0x18008e63f  call    UpdateEntryTimeStamp
0x18008e644  mov     rdx, [rdi+8]; lpSubKey
0x18008e648  mov     rcx, [rbp+hKey]; hKey
0x18008e64c  call    cs:__imp_RegDeleteTreeW
0x18008e653  nop     dword ptr [rax+rax+00h]
0x18008e658  cmp     [r14], esi
0x18008e65b  jnz     loc_18008FE8A
0x18008e661  mov     rcx, [rdi+8]; lpWideCharStr
0x18008e665  call    _StrdupWtoA
0x18008e66a  mov     rsi, rax
0x18008e66d  test    rax, rax
0x18008e670  jz      loc_180090609
0x18008e676  mov     rcx, [rbp+hKey]
0x18008e67a  lea     r8, [rbp+arg_10]
0x18008e67e  mov     rdx, rax
0x18008e681  call    CreateOrOpenSubkey
0x18008e686  mov     ebx, eax
0x18008e688  test    eax, eax
0x18008e68a  jnz     loc_1800905E3
0x18008e690  mov     rcx, rsi; hMem
0x18008e693  call    cs:__imp_GlobalFree
0x18008e69a  nop     dword ptr [rax+rax+00h]
0x18008e69f  mov     rcx, [rbp+arg_10]
0x18008e6a3  lea     r8d, [rbx+1]
0x18008e6a7  lea     rdx, aEncoding; "Encoding"
0x18008e6ae  call    RegInsertLong
0x18008e6b3  xor     esi, esi
0x18008e6b5  mov     ebx, eax
0x18008e6b7  test    eax, eax
0x18008e6b9  jnz     loc_1800905A4
0x18008e6bf  mov     rcx, [rbp+arg_10]
0x18008e6c3  lea     r8d, [rax+8]
0x18008e6c7  lea     rdx, aPbversion; "PBVersion"
0x18008e6ce  call    RegInsertLong
0x18008e6d3  mov     ebx, eax
0x18008e6d5  test    eax, eax
0x18008e6d7  jnz     loc_18009056B
0x18008e6dd  mov     r8d, [rdi+18h]
0x18008e6e1  lea     rdx, aType; "Type"
0x18008e6e8  mov     rcx, [rbp+arg_10]
0x18008e6ec  call    RegInsertLong
0x18008e6f1  mov     ebx, eax
0x18008e6f3  test    eax, eax
0x18008e6f5  jnz     loc_180090545
0x18008e6fb  cmp     [rdi+0B0h], esi
0x18008e701  lea     r8, a1; "1"
0x18008e708  mov     rcx, [rbp+arg_10]
0x18008e70c  lea     r14, a0; "0"
0x18008e713  cmovz   r8, r14
0x18008e717  lea     rdx, aAutologon; "AutoLogon"
0x18008e71e  call    RegInsertStringA
0x18008e723  mov     ebx, eax
0x18008e725  test    eax, eax
0x18008e727  jnz     loc_180090513
0x18008e72d  cmp     [rdi+0B4h], esi
0x18008e733  lea     r8, a1; "1"
0x18008e73a  mov     rcx, [rbp+arg_10]
0x18008e73e  lea     rdx, aUserascredenti; "UseRasCredentials"
0x18008e745  cmovz   r8, r14
0x18008e749  call    RegInsertStringA
0x18008e74e  mov     ebx, eax
0x18008e750  test    eax, eax
0x18008e752  jnz     loc_1800904E1
0x18008e758  mov     r8d, [rdi+10h]
0x18008e75c  lea     rdx, aLowdatetime; "LowDateTime"
0x18008e763  mov     rcx, [rbp+arg_10]
0x18008e767  call    RegInsertLong
0x18008e76c  mov     ebx, eax
0x18008e76e  test    eax, eax
0x18008e770  jnz     loc_1800904AC
0x18008e776  mov     r8d, [rdi+14h]
0x18008e77a  lea     rdx, aHighdatetime; "HighDateTime"
0x18008e781  mov     rcx, [rbp+arg_10]
0x18008e785  call    RegInsertLong
0x18008e78a  mov     ebx, eax
0x18008e78c  test    eax, eax
0x18008e78e  jnz     loc_180090477
0x18008e794  mov     r8d, [rdi+1C8h]
0x18008e79b  lea     rdx, aDialparamsuid; "DialParamsUID"
0x18008e7a2  mov     rcx, [rbp+arg_10]
0x18008e7a6  call    RegInsertLong
0x18008e7ab  mov     ebx, eax
0x18008e7ad  test    eax, eax
0x18008e7af  jnz     loc_180090442
0x18008e7b5  mov     r8, [rdi+1D0h]
0x18008e7bc  test    r8, r8
0x18008e7bf  jz      short loc_18008E7DF
0x18008e7c1  mov     rcx, [rbp+arg_10]
0x18008e7c5  lea     r9d, [rsi+10h]
0x18008e7c9  lea     rdx, aGuid; "Guid"
0x18008e7d0  call    RegInsertBinary
0x18008e7d5  mov     ebx, eax
0x18008e7d7  test    eax, eax
0x18008e7d9  jnz     loc_18008FEB4
0x18008e7df  mov     r8d, [rdi+0A8h]
0x18008e7e6  lea     rdx, aVpnstrategy; "VpnStrategy"
0x18008e7ed  mov     rcx, [rbp+arg_10]
0x18008e7f1  call    RegInsertLong
0x18008e7f6  mov     ebx, eax
0x18008e7f8  test    eax, eax
0x18008e7fa  jnz     loc_18009040D
0x18008e800  mov     r8d, [rdi+0ECh]
0x18008e807  lea     rdx, aExcludedprotoc; "ExcludedProtocols"
0x18008e80e  mov     rcx, [rbp+arg_10]
0x18008e812  call    RegInsertLong
0x18008e817  mov     ebx, eax
0x18008e819  test    eax, eax
0x18008e81b  jnz     loc_1800903D8
0x18008e821  cmp     [rdi+0F0h], esi
0x18008e827  lea     r8, a1; "1"
0x18008e82e  mov     rcx, [rbp+arg_10]
0x18008e832  lea     rdx, aLcpextensions; "LcpExtensions"
0x18008e839  cmovz   r8, r14
0x18008e83d  call    RegInsertStringA
0x18008e842  mov     ebx, eax
0x18008e844  test    eax, eax
0x18008e846  jnz     loc_1800903A3
0x18008e84c  mov     r8d, [rdi+0ACh]
0x18008e853  lea     rdx, aDataencryption; "DataEncryption"
0x18008e85a  mov     rcx, [rbp+arg_10]
0x18008e85e  call    RegInsertLong
0x18008e863  mov     ebx, eax
0x18008e865  test    eax, eax
0x18008e867  jnz     loc_18009036E
0x18008e86d  cmp     [rdi+0F4h], esi
0x18008e873  lea     r8, a1; "1"
0x18008e87a  mov     rcx, [rbp+arg_10]
0x18008e87e  lea     rdx, aSwcompression; "SwCompression"
0x18008e885  cmovz   r8, r14
0x18008e889  call    RegInsertStringA
0x18008e88e  mov     ebx, eax
0x18008e890  test    eax, eax
0x18008e892  jnz     loc_1800905CA
0x18008e898  cmp     [rdi+0F8h], esi
0x18008e89e  lea     r8, a1; "1"
0x18008e8a5  mov     rcx, [rbp+arg_10]
0x18008e8a9  lea     rdx, aNegotiatemulti; "NegotiateMultilinkAlways"
0x18008e8b0  cmovz   r8, r14
0x18008e8b4  call    RegInsertStringA
0x18008e8b9  mov     ebx, eax
0x18008e8bb  test    eax, eax
0x18008e8bd  jnz     loc_1800905CA
0x18008e8c3  cmp     [rdi+0FCh], esi
0x18008e8c9  lea     r8, a1; "1"
0x18008e8d0  mov     rcx, [rbp+arg_10]
0x18008e8d4  lea     rdx, aSkipdoubledial; "SkipDoubleDialDialog"
0x18008e8db  cmovz   r8, r14
0x18008e8df  call    RegInsertStringA
0x18008e8e4  mov     ebx, eax
0x18008e8e6  test    eax, eax
0x18008e8e8  jnz     loc_1800905CA
0x18008e8ee  mov     r8d, [rdi+84h]
  ... truncated ...
```
