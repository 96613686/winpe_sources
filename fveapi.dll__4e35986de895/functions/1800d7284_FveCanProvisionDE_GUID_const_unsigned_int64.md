# FveCanProvisionDE(_GUID const *,unsigned __int64 *)

- ea: `0x1800d7284`
- end: `0x1800d7c6c`
- name: `?FveCanProvisionDE@@YAHPEBU_GUID@@PEA_K@Z`
- size: `2536`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053e94`

## callees

- `0x180004158`
- `0x1800042c0`
- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004ad74`
- `0x1800d7284`
- `0x1800d8120`
- `0x1800d8788`
- `0x1800d91c0`
- `0x1800d9de0`
- `0x1800d9e1c`
- `0x1800d9e74`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d72fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d72fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d737b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d73fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d737b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d73fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d7c3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d7c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7413`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d75fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d75fb`

## string_xrefs

- `0x1800d72c5`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall FveCanProvisionDE(struct _GUID *a1, unsigned __int64 *a2)
{
  bool v2; // r13
  unsigned int v3; // r14d
  bool v4; // si
  bool v5; // r12
  HMODULE Library; // rax
  HMODULE v7; // r15
  signed int LastError; // eax
  unsigned int v9; // ebx
  FARPROC ProcAddress; // r12
  signed int v11; // eax
  int (*v12)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *); // r13
  signed int v13; // eax
  int v14; // eax
  int v15; // esi
  unsigned __int64 v16; // rax
  int v17; // eax
  int v18; // esi
  unsigned __int64 v19; // rax
  LSTATUS ValueW; // eax
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // esi
  int ShouldDeferForMdmPolicySync; // eax
  unsigned __int64 v25; // r8
  int IsAutoPilotScenario; // eax
  bool v27; // r9
  bool v28; // cl
  unsigned __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  PVOID *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  bool v40; // [rsp+90h] [rbp-49h] BYREF
  bool v41; // [rsp+91h] [rbp-48h] BYREF
  bool v42; // [rsp+92h] [rbp-47h] BYREF
  bool v43; // [rsp+93h] [rbp-46h] BYREF
  bool v44; // [rsp+94h] [rbp-45h] BYREF
  unsigned __int64 v45; // [rsp+98h] [rbp-41h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp-39h] BYREF
  int pvData; // [rsp+A4h] [rbp-35h] BYREF
  int v48; // [rsp+A8h] [rbp-31h] BYREF
  int v49; // [rsp+ACh] [rbp-2Dh] BYREF
  int v50; // [rsp+B0h] [rbp-29h] BYREF
  int v51; // [rsp+B4h] [rbp-25h] BYREF
  HMODULE v52; // [rsp+B8h] [rbp-21h] BYREF
  int v53; // [rsp+C0h] [rbp-19h] BYREF
  int v54; // [rsp+C4h] [rbp-15h] BYREF
  unsigned int v55; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v56[96]; // [rsp+D0h] [rbp-9h] BYREF
  GUID *rguid; // [rsp+140h] [rbp+67h] BYREF
  unsigned __int64 *v58; // [rsp+148h] [rbp+6Fh] BYREF
  bool v59; // [rsp+150h] [rbp+77h] BYREF
  bool v60; // [rsp+158h] [rbp+7Fh] BYREF

  v58 = a2;
  rguid = a1;
  pcbData = 4;
  v2 = 1;
  v54 = 0;
  v40 = 0;
  v59 = 0;
  v60 = 0;
  v3 = 0;
  v44 = 0;
  v4 = 0;
  v43 = 0;
  v5 = 0;
  v41 = 1;
  pvData = 0;
  v49 = 0;
  v48 = 0;
  v53 = 0;
  v50 = 0;
  v51 = 0;
  v45 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v52 = Library;
  v7 = Library;
  if ( !Library )
  {
    v45 |= 1u;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
    goto LABEL_101;
  }
  ProcAddress = GetProcAddress(Library, "NtQueryWnfStateData");
  if ( !ProcAddress )
  {
    v45 |= 2u;
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v5 = 0;
    }
    else
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
      v5 = 0;
    }
    goto LABEL_101;
  }
  v12 = (int (*)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *))GetProcAddress(
                                                                                                   v7,
                                                                                                   "NtQueryLicenseValue");
  if ( v12 )
  {
    pvData = 0;
    pcbData = 4;
    v9 = 0;
    v14 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
            &WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED,
            0,
            0,
            &v54,
            &pvData,
            &pcbData);
    v15 = v14;
    if ( v14 >= 0 )
    {
      if ( pcbData > 4 )
      {
        v16 = v45 | 0x10;
      }
      else
      {
        v40 = pvData == 1;
        v16 = v45 | (32 * ((pvData != 1) + 1LL));
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)v14);
      v16 = v45 | 8;
      v49 = v15;
    }
    v45 = v16;
    pvData = 0;
    pcbData = 4;
    v17 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
            &WNF_SHEL_OOBE_USER_LOGON_COMPLETE,
            0,
            0,
            &v54,
            &pvData,
            &pcbData);
    v18 = v17;
    if ( v17 >= 0 )
    {
      if ( pcbData > 4 )
      {
        v19 = v45 | 0x100;
      }
      else
      {
        v59 = pvData == 1;
        v19 = v45 | (((pvData != 1) + 1LL) << 9);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)v17);
      v19 = v45 | 0x80;
      v48 = v18;
    }
    v45 = v19;
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
               L"SetupDisplayedEula",
               0x20000010u,
               0,
               &pvData,
               &pcbData);
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW > 0 )
        v9 = (unsigned __int16)ValueW | 0x80070000;
      else
        v9 = ValueW;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
      v21 = v45 | 0x800;
    }
    else
    {
      v21 = v45;
    }
    if ( pcbData > 4 )
    {
      v4 = 0;
      v45 = v21 | 0x1000;
    }
    else
    {
      v4 = pvData == 1;
      v42 = pvData == 1;
      v45 = v21 | (((pvData != 1) + 1LL) << 13);
      if ( pvData == 1 )
      {
        pvData = 0;
        pcbData = 4;
        v22 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
                &WNF_DEP_OOBE_COMPLETE,
                0,
                0,
                &v54,
                &pvData,
                &pcbData);
        v23 = v22;
        if ( v22 >= 0 )
        {
          v4 = v42;
          if ( pcbData > 4 )
          {
            v45 |= 0x10000u;
          }
          else
          {
            v60 = pvData == 1;
            v45 |= ((unsigned __int64)(pvData != 1) << 17) + 0x20000;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              42,
              &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
              (unsigned int)v22);
          v45 |= 0x8000u;
          v53 = v23;
          v4 = v42;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
    {
      ShouldDeferForMdmPolicySync = FveShouldDeferForMdmPolicySync(
                                      (int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *))ProcAddress,
                                      v12,
                                      &v41,
                                      &v45);
      v51 = ShouldDeferForMdmPolicySync;
      if ( ShouldDeferForMdmPolicySync >= 0 )
      {
        v2 = v41;
        v5 = v59;
        v25 = ((-(__int64)v41 & 0xFFFFFFFFFFF00000uLL) + 0x200000) | v45;
        if ( v59 || !v41 )
          v3 = 1;
        goto LABEL_71;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)ShouldDeferForMdmPolicySync);
      v5 = v59;
      v25 = v45 | 0x80000;
LABEL_70:
      v2 = v41;
LABEL_71:
      v27 = v40;
      v28 = v60;
      goto LABEL_72;
    }
    IsAutoPilotScenario = FveIsAutoPilotScenario(
                            (int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *))ProcAddress,
                            (__int64 (__fastcall *)(struct _UNICODE_STRING *, int *, int *, __int64, int *))v12,
                            &v44,
                            &v43,
                            &v45);
    v50 = IsAutoPilotScenario;
    if ( IsAutoPilotScenario == -2147024875 )
    {
      v25 = v45 | 0x400000;
      v45 |= 0x400000u;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
    }
    else if ( IsAutoPilotScenario >= 0 )
    {
      if ( !IsAutoPilotScenario )
      {
        v5 = v59;
        v25 = ((-(__int64)v44 & 0xFFFFFFFFFF000000uLL) + 0x2000000) | v45;
        if ( !v44 )
        {
          v27 = v40;
          v28 = v60;
          if ( v40 || v59 || v60 )
            v3 = 1;
          v2 = v41;
LABEL_72:
          v29 = (((v3 ^ 1LL) << 26) + 0x4000000) | v25;
          v45 = v29;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_llll(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v29, v27, v4, v5, v28);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
          {
            v32 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v2);
LABEL_96:
                v32 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_97;
              }
              goto LABEL_97;
            }
          }
          else
          {
            v32 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v44, v43);
                goto LABEL_96;
              }
LABEL_97:
              if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 8) != 0 )
                WPP_SF_D(v32[2], 49, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v3);
            }
          }
          v7 = v52;
          goto LABEL_101;
        }
        if ( v43 || v59 )
          v3 = 1;
        goto LABEL_70;
      }
    }
    else
    {
      v25 = v45 | 0x800000;
      v45 |= 0x800000u;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)IsAutoPilotScenario);
    }
    v25 = v45;
LABEL_69:
    v5 = v59;
    LOBYTE(v3) = v59;
    goto LABEL_70;
  }
  v45 |= 4u;
  v13 = GetLastError();
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v2 = v41;
    v5 = 0;
  }
  else
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
    v2 = v41;
    v5 = 0;
  }
LABEL_101:
  if ( rguid )
    FveRecordDeCheck(rguid, v45, v3);
  if ( v58 )
    *v58 = v45;
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v56,
    &g_hBitLockerDelayProvider,
    &g_bitLockerDelayProviderInitLock,
    &g_bitLockerDelayProviderRefCount);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_180172550 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180172550, 0x400000000000LL) )
    {
      LOBYTE(v58) = v43;
      v59 = v44;
      v55 = v9;
      LOBYTE(rguid) = v2;
      LODWORD(v52) = v3;
      v42 = v5;
      v41 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v33,
        (int)&word_18015FE86,
        v34,
        v35,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&rguid,
        (__int64)&v51,
        (__int64)&v55);
    }
  }
  else if ( (unsigned int)dword_180172550 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180172550, 0x400000000000LL) )
  {
    v51 = v53;
    LOBYTE(rguid) = v43;
    LOBYTE(v58) = v44;
    v59 = v60;
    LODWORD(v52) = v9;
    v55 = v3;
    v60 = v5;
    v42 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v36,
      (int)byte_180160083,
      v37,
      v38,
      (__int64)&v40,
      (__int64)&v42,
      (__int64)&v60,
      (__int64)&v59,
      (__int64)&v58,
      (__int64)&rguid,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v51,
      (__int64)&v55,
      (__int64)&v52);
  }
  if ( v7 )
    FreeLibrary(v7);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v56);
  return v3;
}

```

## disassembly

```asm
0x1800d7284  mov     [rsp-8+arg_8], rdx
0x1800d7289  mov     [rsp-8+rguid], rcx
0x1800d728e  push    rbp
0x1800d728f  push    rbx
0x1800d7290  push    rsi
0x1800d7291  push    rdi
0x1800d7292  push    r12
0x1800d7294  push    r13
0x1800d7296  push    r14
0x1800d7298  push    r15
0x1800d729a  lea     rbp, [rsp-1Fh]
0x1800d729f  sub     rsp, 0F8h
0x1800d72a6  xor     edi, edi
0x1800d72a8  mov     [rbp+57h+var_90], 4
0x1800d72af  mov     r13b, 1
0x1800d72b2  mov     [rbp+57h+var_6C], edi
0x1800d72b5  xor     edx, edx; hFile
0x1800d72b7  mov     [rbp+57h+var_A0], dil
0x1800d72bb  mov     r8d, 800h; dwFlags
0x1800d72c1  mov     [rbp+57h+arg_10], dil
0x1800d72c5  lea     rcx, ModuleName; "ntdll.dll"
0x1800d72cc  mov     [rbp+57h+arg_18], dil
0x1800d72d0  mov     r14d, edi
0x1800d72d3  mov     [rbp+57h+var_9C], dil
0x1800d72d7  mov     sil, dil
0x1800d72da  mov     [rbp+57h+var_9D], dil
0x1800d72de  mov     r12b, dil
0x1800d72e1  mov     [rbp+57h+var_9F], r13b
0x1800d72e5  mov     [rbp+57h+var_8C], edi
0x1800d72e8  mov     [rbp+57h+var_84], edi
0x1800d72eb  mov     [rbp+57h+var_88], edi
0x1800d72ee  mov     [rbp+57h+var_70], edi
0x1800d72f1  mov     [rbp+57h+var_80], edi
0x1800d72f4  mov     [rbp+57h+var_7C], edi
0x1800d72f7  mov     [rbp+57h+var_98], rdi
0x1800d72fb  call    cs:__imp_LoadLibraryExW
0x1800d7302  nop     dword ptr [rax+rax+00h]
0x1800d7307  mov     [rbp+57h+var_78], rax
0x1800d730b  mov     r15, rax
0x1800d730e  test    rax, rax
0x1800d7311  jnz     short loc_1800D7371
0x1800d7313  or      [rbp+57h+var_98], 1
0x1800d7318  call    cs:__imp_GetLastError
0x1800d731f  nop     dword ptr [rax+rax+00h]
0x1800d7324  mov     ebx, eax
0x1800d7326  test    eax, eax
0x1800d7328  jle     short loc_1800D7333
0x1800d732a  movzx   ebx, ax
0x1800d732d  or      ebx, 80070000h
0x1800d7333  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d733a  lea     rdi, WPP_GLOBAL_Control
0x1800d7341  cmp     rcx, rdi
0x1800d7344  jz      loc_1800D79E0
0x1800d734a  test    byte ptr [rcx+1Ch], 2
0x1800d734e  jz      loc_1800D79E0
0x1800d7354  mov     rcx, [rcx+10h]
0x1800d7358  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d735f  mov     edx, 24h ; '$'
0x1800d7364  mov     r9d, ebx
0x1800d7367  call    WPP_SF_d
0x1800d736c  jmp     loc_1800D79E0
0x1800d7371  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800d7378  mov     rcx, r15; hModule
0x1800d737b  call    cs:__imp_GetProcAddress
0x1800d7382  nop     dword ptr [rax+rax+00h]
0x1800d7387  mov     r12, rax
0x1800d738a  test    rax, rax
0x1800d738d  jnz     short loc_1800D73F0
0x1800d738f  or      [rbp+57h+var_98], 2
0x1800d7394  call    cs:__imp_GetLastError
0x1800d739b  nop     dword ptr [rax+rax+00h]
0x1800d73a0  mov     ebx, eax
0x1800d73a2  test    eax, eax
0x1800d73a4  jle     short loc_1800D73AF
0x1800d73a6  movzx   ebx, ax
0x1800d73a9  or      ebx, 80070000h
0x1800d73af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d73b6  lea     rdi, WPP_GLOBAL_Control
0x1800d73bd  cmp     rcx, rdi
0x1800d73c0  jz      loc_1800D7B51
0x1800d73c6  test    byte ptr [rcx+1Ch], 2
0x1800d73ca  jz      loc_1800D7B51
0x1800d73d0  mov     rcx, [rcx+10h]
0x1800d73d4  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d73db  mov     edx, 25h ; '%'
0x1800d73e0  mov     r9d, ebx
0x1800d73e3  call    WPP_SF_d
0x1800d73e8  mov     r12b, sil
0x1800d73eb  jmp     loc_1800D79E0
0x1800d73f0  lea     rdx, aNtquerylicense; "NtQueryLicenseValue"
0x1800d73f7  mov     rcx, r15; hModule
0x1800d73fa  call    cs:__imp_GetProcAddress
0x1800d7401  nop     dword ptr [rax+rax+00h]
0x1800d7406  mov     r13, rax
0x1800d7409  test    rax, rax
0x1800d740c  jnz     short loc_1800D7473
0x1800d740e  or      [rbp+57h+var_98], 4
0x1800d7413  call    cs:__imp_GetLastError
0x1800d741a  nop     dword ptr [rax+rax+00h]
0x1800d741f  mov     ebx, eax
0x1800d7421  test    eax, eax
0x1800d7423  jle     short loc_1800D742E
0x1800d7425  movzx   ebx, ax
0x1800d7428  or      ebx, 80070000h
0x1800d742e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7435  lea     rdi, WPP_GLOBAL_Control
0x1800d743c  cmp     rcx, rdi
0x1800d743f  jz      loc_1800D7B45
0x1800d7445  test    byte ptr [rcx+1Ch], 2
0x1800d7449  jz      loc_1800D7B45
0x1800d744f  mov     rcx, [rcx+10h]
0x1800d7453  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d745a  mov     edx, 26h ; '&'
0x1800d745f  mov     r9d, ebx
0x1800d7462  call    WPP_SF_d
0x1800d7467  mov     r13b, [rbp+57h+var_9F]
0x1800d746b  mov     r12b, sil
0x1800d746e  jmp     loc_1800D79E0
0x1800d7473  lea     rax, [rbp+57h+var_90]
0x1800d7477  mov     [rbp+57h+var_8C], edi
0x1800d747a  mov     [rsp+130h+pvData], rax
0x1800d747f  lea     r9, [rbp+57h+var_6C]
0x1800d7483  lea     rax, [rbp+57h+var_8C]
0x1800d7487  mov     [rbp+57h+var_90], 4
0x1800d748e  mov     [rsp+130h+pdwType], rax
0x1800d7493  lea     rcx, WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED
0x1800d749a  mov     rax, r12
0x1800d749d  xor     r8d, r8d
0x1800d74a0  xor     edx, edx
0x1800d74a2  mov     ebx, edi
0x1800d74a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d74a9  lea     rdi, WPP_GLOBAL_Control
0x1800d74b0  mov     esi, eax
0x1800d74b2  lea     r15, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d74b9  test    eax, eax
0x1800d74bb  jns     short loc_1800D74F0
0x1800d74bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d74c4  cmp     rcx, rdi
0x1800d74c7  jz      short loc_1800D74E3
0x1800d74c9  test    byte ptr [rcx+1Ch], 2
0x1800d74cd  jz      short loc_1800D74E3
0x1800d74cf  mov     rcx, [rcx+10h]
0x1800d74d3  mov     edx, 27h ; '''
0x1800d74d8  mov     r9d, eax
0x1800d74db  mov     r8, r15
0x1800d74de  call    WPP_SF_d
0x1800d74e3  mov     rax, [rbp+57h+var_98]
0x1800d74e7  or      rax, 8
0x1800d74eb  mov     [rbp+57h+var_84], esi
0x1800d74ee  jmp     short loc_1800D751C
0x1800d74f0  cmp     [rbp+57h+var_90], 4
0x1800d74f4  ja      short loc_1800D7514
0x1800d74f6  cmp     [rbp+57h+var_8C], 1
0x1800d74fa  setz    al
0x1800d74fd  mov     [rbp+57h+var_A0], al
0x1800d7500  movzx   eax, al
0x1800d7503  xor     rax, 1
0x1800d7507  inc     rax
0x1800d750a  shl     rax, 5
0x1800d750e  or      rax, [rbp+57h+var_98]
0x1800d7512  jmp     short loc_1800D751C
0x1800d7514  mov     rax, [rbp+57h+var_98]
0x1800d7518  or      rax, 10h
0x1800d751c  mov     [rbp+57h+var_98], rax
0x1800d7520  lea     r9, [rbp+57h+var_6C]
0x1800d7524  lea     rax, [rbp+57h+var_90]
0x1800d7528  mov     [rbp+57h+var_8C], ebx
0x1800d752b  mov     [rsp+130h+pvData], rax
0x1800d7530  lea     rcx, WNF_SHEL_OOBE_USER_LOGON_COMPLETE
0x1800d7537  lea     rax, [rbp+57h+var_8C]
0x1800d753b  mov     [rbp+57h+var_90], 4
0x1800d7542  mov     [rsp+130h+pdwType], rax
0x1800d7547  xor     r8d, r8d
0x1800d754a  mov     rax, r12
0x1800d754d  xor     edx, edx
0x1800d754f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7554  mov     esi, eax
0x1800d7556  test    eax, eax
0x1800d7558  jns     short loc_1800D758E
0x1800d755a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7561  cmp     rcx, rdi
0x1800d7564  jz      short loc_1800D7580
0x1800d7566  test    byte ptr [rcx+1Ch], 2
0x1800d756a  jz      short loc_1800D7580
0x1800d756c  mov     rcx, [rcx+10h]
0x1800d7570  mov     edx, 28h ; '('
0x1800d7575  mov     r9d, eax
0x1800d7578  mov     r8, r15
0x1800d757b  call    WPP_SF_d
0x1800d7580  mov     rax, [rbp+57h+var_98]
0x1800d7584  bts     rax, 7
0x1800d7589  mov     [rbp+57h+var_88], esi
0x1800d758c  jmp     short loc_1800D75BB
0x1800d758e  cmp     [rbp+57h+var_90], 4
0x1800d7592  ja      short loc_1800D75B2
0x1800d7594  cmp     [rbp+57h+var_8C], 1
0x1800d7598  setz    al
0x1800d759b  mov     [rbp+57h+arg_10], al
0x1800d759e  movzx   eax, al
0x1800d75a1  xor     rax, 1
0x1800d75a5  inc     rax
0x1800d75a8  shl     rax, 9
0x1800d75ac  or      rax, [rbp+57h+var_98]
0x1800d75b0  jmp     short loc_1800D75BB
0x1800d75b2  mov     rax, [rbp+57h+var_98]
0x1800d75b6  bts     rax, 8
0x1800d75bb  mov     [rbp+57h+var_98], rax
0x1800d75bf  lea     r8, aSetupdisplayed; "SetupDisplayedEula"
0x1800d75c6  lea     rax, [rbp+57h+var_90]
0x1800d75ca  mov     [rbp+57h+var_8C], ebx
0x1800d75cd  mov     [rsp+130h+pcbData], rax; pcbData
0x1800d75d2  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d75d9  lea     rax, [rbp+57h+var_8C]
0x1800d75dd  mov     [rbp+57h+var_90], 4
0x1800d75e4  mov     [rsp+130h+pvData], rax; pvData
0x1800d75e9  mov     r9d, 20000010h; dwFlags
0x1800d75ef  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d75f6  mov     [rsp+130h+pdwType], rbx; pdwType
0x1800d75fb  call    cs:__imp_RegGetValueW
0x1800d7602  nop     dword ptr [rax+rax+00h]
0x1800d7607  test    eax, 0FFFFFFFDh
0x1800d760c  jz      short loc_1800D7650
0x1800d760e  test    eax, eax
0x1800d7610  jg      short loc_1800D7616
0x1800d7612  mov     ebx, eax
0x1800d7614  jmp     short loc_1800D761F
0x1800d7616  movzx   ebx, ax
0x1800d7619  or      ebx, 80070000h
0x1800d761f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7626  cmp     rcx, rdi
0x1800d7629  jz      short loc_1800D7645
0x1800d762b  test    byte ptr [rcx+1Ch], 2
0x1800d762f  jz      short loc_1800D7645
0x1800d7631  mov     rcx, [rcx+10h]
0x1800d7635  mov     edx, 29h ; ')'
0x1800d763a  mov     r9d, ebx
0x1800d763d  mov     r8, r15
0x1800d7640  call    WPP_SF_d
0x1800d7645  mov     rcx, [rbp+57h+var_98]
0x1800d7649  bts     rcx, 0Bh
0x1800d764e  jmp     short loc_1800D7654
0x1800d7650  mov     rcx, [rbp+57h+var_98]
0x1800d7654  cmp     [rbp+57h+var_90], 4
0x1800d7658  ja      loc_1800D772C
0x1800d765e  cmp     [rbp+57h+var_8C], 1
0x1800d7662  setz    sil
0x1800d7666  movzx   eax, sil
0x1800d766a  xor     rax, 1
0x1800d766e  mov     [rbp+57h+var_9E], sil
0x1800d7672  inc     rax
0x1800d7675  shl     rax, 0Dh
0x1800d7679  or      rax, rcx
0x1800d767c  mov     [rbp+57h+var_98], rax
0x1800d7680  test    sil, sil
0x1800d7683  jz      loc_1800D7738
0x1800d7689  lea     rax, [rbp+57h+var_90]
0x1800d768d  mov     [rbp+57h+var_8C], r14d
0x1800d7691  mov     [rsp+130h+pvData], rax
0x1800d7696  lea     r9, [rbp+57h+var_6C]
0x1800d769a  lea     rax, [rbp+57h+var_8C]
0x1800d769e  mov     [rbp+57h+var_90], 4
0x1800d76a5  mov     [rsp+130h+pdwType], rax
0x1800d76aa  lea     rcx, WNF_DEP_OOBE_COMPLETE
0x1800d76b1  mov     rax, r12
0x1800d76b4  xor     r8d, r8d
0x1800d76b7  xor     edx, edx
0x1800d76b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76be  mov     esi, eax
0x1800d76c0  test    eax, eax
0x1800d76c2  jns     short loc_1800D76F9
0x1800d76c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d76cb  cmp     rcx, rdi
0x1800d76ce  jz      short loc_1800D76EA
0x1800d76d0  test    byte ptr [rcx+1Ch], 2
0x1800d76d4  jz      short loc_1800D76EA
0x1800d76d6  mov     rcx, [rcx+10h]
0x1800d76da  mov     edx, 2Ah ; '*'
0x1800d76df  mov     r9d, eax
0x1800d76e2  mov     r8, r15
0x1800d76e5  call    WPP_SF_d
0x1800d76ea  bts     [rbp+57h+var_98], 0Fh
0x1800d76f0  mov     [rbp+57h+var_70], esi
0x1800d76f3  mov     sil, [rbp+57h+var_9E]
0x1800d76f7  jmp     short loc_1800D7738
0x1800d76f9  cmp     [rbp+57h+var_90], 4
0x1800d76fd  mov     sil, [rbp+57h+var_9E]
0x1800d7701  ja      short loc_1800D7724
0x1800d7703  cmp     [rbp+57h+var_8C], 1
0x1800d7707  setz    al
0x1800d770a  mov     [rbp+57h+arg_18], al
0x1800d770d  movzx   eax, al
0x1800d7710  xor     rax, 1
0x1800d7714  shl     rax, 11h
0x1800d7718  add     rax, 20000h
0x1800d771e  or      [rbp+57h+var_98], rax
0x1800d7722  jmp     short loc_1800D7738
0x1800d7724  bts     [rbp+57h+var_98], 10h
0x1800d772a  jmp     short loc_1800D7738
0x1800d772c  bts     rcx, 0Ch
0x1800d7731  mov     sil, r14b
  ... truncated ...
```
