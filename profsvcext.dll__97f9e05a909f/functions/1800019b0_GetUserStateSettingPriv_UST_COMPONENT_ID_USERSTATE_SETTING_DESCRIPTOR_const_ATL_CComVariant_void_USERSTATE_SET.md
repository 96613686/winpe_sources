# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x1800019b0`
- end: `0x18000230e`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `2398`
- prototype: `__int64 __fastcall(unsigned int, __int64, VARIANTARG *, void *, int, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800024c0`

## callees

- `0x1800019b0`
- `0x1800024c0`
- `0x1800025b0`
- `0x180002940`
- `0x180002960`
- `0x1800029b0`
- `0x180006bac`
- `0x18001aca0`
- `0x18001ad28`
- `0x18001ae58`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001b008`
- `0x18001b068`
- `0x18001b0ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e3d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e6b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002127`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800021ac`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e0c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e3d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180001e6b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002127`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800021ac`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001bdd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001bdd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800022af`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800022af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ca2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180001d11`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180001d11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d8f`
- `OLEAUT32!__imp_VariantClear` at `0x180001a0f`
- `OLEAUT32!__imp_VariantClear` at `0x180001bad`
- `OLEAUT32!__imp_VariantClear` at `0x180001c79`
- `OLEAUT32!__imp_VariantClear` at `0x180001a0f`
- `OLEAUT32!__imp_VariantClear` at `0x180001bad`
- `OLEAUT32!__imp_VariantClear` at `0x180001c79`
- `OLEAUT32!__imp_VariantChangeType` at `0x180001ec7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002242`
- `OLEAUT32!__imp_VariantChangeType` at `0x180001ec7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002242`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserStateSettingPriv(
        unsigned int a1,
        __int64 a2,
        VARIANTARG *a3,
        void *a4,
        int a5,
        LPCWSTR lpSubKey)
{
  int v10; // esi
  __int64 v11; // r9
  UstCommon::CImpersonator *v12; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // ebx
  char v17; // di
  unsigned int v18; // r14d
  ATL::CComVariant *v19; // rsi
  const struct tagVARIANT *v20; // r12
  __int64 v21; // r9
  __int64 v22; // r9
  unsigned int StoredValue; // eax
  __int64 v24; // r9
  BOOL v25; // ebx
  signed int LastError; // eax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rdx
  LPCWSTR v31; // rbx
  VARIANTARG *p_pvarg; // rdx
  HRESULT v33; // eax
  int v34; // edx
  int v35; // r8d
  const wchar_t *bstrVal; // rcx
  unsigned int v37; // edi
  const wchar_t *v38; // r9
  unsigned int v39; // eax
  __int64 v40; // r9
  __int64 v41; // r9
  VARIANTARG *v42; // rdx
  HRESULT v43; // eax
  int v44; // edx
  int v45; // r8d
  const wchar_t *v46; // r9
  int v47; // [rsp+50h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  __int64 v49; // [rsp+60h] [rbp-29h]
  __int64 v50; // [rsp+68h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v10 = a5;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v31 = L"NULL";
    if ( lpSubKey )
      v31 = lpSubKey;
    p_pvarg = &pvarg;
    if ( a3 )
      p_pvarg = a3;
    v33 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v33 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_dddSqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v34,
      v35,
      a1,
      *(_DWORD *)a2,
      a3->vt,
      (__int64)bstrVal,
      (char)a4,
      v10,
      (__int64)v31);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
  }
  VariantClear(&pvarg);
  if ( (v10 & 0x30) == 0 )
    v10 |= *(_DWORD *)(a2 + 8) & 0x30;
  if ( (v10 & 0x30) != 0x30 )
  {
    v12 = WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a1);
    v12 = WPP_GLOBAL_Control;
  }
  if ( a1 == 1 )
  {
    v21 = 0;
  }
  else
  {
    v37 = a1 - 2;
    if ( v37 )
    {
      if ( v37 != 1 )
      {
        if ( v12 == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 2) == 0 )
          goto LABEL_35;
        WPP_SF_(*((_QWORD *)v12 + 2), 18, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v11);
LABEL_34:
        v12 = WPP_GLOBAL_Control;
LABEL_35:
        LOBYTE(v10) = v10 & 0xDF;
        goto LABEL_6;
      }
      v21 = 2;
    }
    else
    {
      v21 = 1;
    }
  }
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  if ( (int)GetUserStateSetting(0, qword_18002D760, 3, v21, &pvarg, 0, 0, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v22);
    }
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v38 = L"SA_WMI";
    if ( pvarg.bVal != 1 )
      v38 = L"SA_GP";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v38);
  }
  v25 = pvarg.bVal == 1;
  ATL::CComVariant::Clear((ATL::CComVariant *)&pvarg);
  v12 = WPP_GLOBAL_Control;
  if ( !v25 )
    goto LABEL_35;
  LOBYTE(v10) = v10 & 0xEF;
LABEL_6:
  if ( (v10 & 0x20) != 0 )
  {
    v14 = 40;
    v15 = 32;
  }
  else
  {
    if ( (v10 & 0x10) == 0 )
    {
      if ( v12 == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 2) == 0 )
        return 2147942487LL;
      v30 = 22;
LABEL_147:
      WPP_SF_(*((_QWORD *)v12 + 2), v30, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v11);
      return 2147942487LL;
    }
    v14 = 24;
    v15 = 16;
  }
  v50 = v15;
  v49 = v14;
  if ( (v10 & 7) == 0 )
    v10 = *(_DWORD *)(a2 + 8) & 7;
  v16 = 0;
  v47 = 0;
  v17 = 0;
  LOBYTE(a5) = 0;
  if ( (v10 & 1) == 0 )
  {
    v18 = 0;
    if ( (v10 & 4) == 0 )
      goto LABEL_15;
  }
  if ( a4 )
  {
    v18 = 1;
    if ( !UstCommon::CImpersonator::_IsThreadImpersonating(v12) )
    {
      if ( ImpersonateLoggedOnUser(a4) )
      {
        v17 = 1;
        LOBYTE(a5) = 1;
        v18 = 0;
      }
      else
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v18);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 2) == 0 )
      goto LABEL_41;
    WPP_SF_d(*((_QWORD *)v12 + 2), 24, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v18);
    goto LABEL_112;
  }
  v39 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v47, (int *)v15);
  v18 = v39;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v39);
    v16 = v47;
LABEL_112:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v16 = v47;
LABEL_41:
  if ( (v18 & 0x80000000) != 0 )
  {
    if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 25, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v18);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v16 )
      return v18;
LABEL_116:
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v40);
    }
    return v18;
  }
  v14 = v49;
  v15 = v50;
LABEL_15:
  hKey = 0;
  if ( (v10 & 2) != 0 )
  {
    hKey = HKEY_LOCAL_MACHINE;
    goto LABEL_17;
  }
  if ( (v10 & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v27 = RegOpenCurrentUser(0x20019u, &hKey);
    v18 = v27;
    if ( v27 > 0 )
      v18 = (unsigned __int16)v27 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v18);
      v12 = WPP_GLOBAL_Control;
    }
    v14 = v49;
    v15 = v50;
LABEL_17:
    if ( (v18 & 0x80000000) != 0 )
    {
      v19 = (ATL::CComVariant *)a3;
      goto LABEL_19;
    }
LABEL_43:
    v19 = (ATL::CComVariant *)a3;
    StoredValue = GetStoredValue(
                    hKey,
                    *(const unsigned __int16 **)(v15 + a2),
                    *(unsigned __int16 **)(v14 + a2),
                    *(_WORD *)(a2 + 4),
                    a3);
    v18 = StoredValue;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_313c576492293c0704086ae70e07ed75_Traceguids, StoredValue);
      v12 = WPP_GLOBAL_Control;
    }
    if ( (v18 & 0x80000000) == 0 )
    {
LABEL_45:
      memset(&pvarg, 0, sizeof(pvarg));
      if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      {
        v42 = &pvarg;
        if ( v19 )
          v42 = (VARIANTARG *)v19;
        v43 = VariantChangeType(&pvarg, v42, 0, 8u);
        v46 = L"<undefined>";
        if ( v43 >= 0 )
          LODWORD(v46) = pvarg.lVal;
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, v45, (_DWORD)v46, v18);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
      }
      VariantClear(&pvarg);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v24);
        }
        RevertToSelf();
      }
      if ( !v16 )
        return v18;
      goto LABEL_116;
    }
LABEL_19:
    v20 = (const struct tagVARIANT *)(a2 + 48);
    if ( v20->vt )
    {
      if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)v12 + 2), 31, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v11);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v19 != (ATL::CComVariant *)v20 )
      {
        ATL::CComVariant::InternalCopy(v19, v20);
        v12 = WPP_GLOBAL_Control;
      }
      v18 = 1;
    }
    goto LABEL_45;
  }
  if ( (v10 & 4) == 0 )
  {
    if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 29, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v18);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v16 )
      return 2147942487LL;
LABEL_74:
    CoRevertToSelf();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      return 2147942487LL;
    }
    v30 = 11;
    goto LABEL_147;
  }
  if ( !lpSubKey )
  {
    if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v12 + 2), 27, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v11);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v16 )
      return 2147942487LL;
    goto LABEL_74;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v28 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hKey);
  v29 = v28;
  if ( v28 > 0 )
    v29 = (unsigned __int16)v28 | 0x80070000;
  if ( (v29 & 0x80000000) == 0 )
  {
    v14 = v49;
    v15 = v50;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
  if ( v16 )
  {
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v41);
    }
  }
  return v29;
}

```

## disassembly

```asm
0x1800019b0  mov     [rsp-8+pvarSrc], r8
0x1800019b5  push    rbp
0x1800019b6  push    rbx
0x1800019b7  push    rsi
0x1800019b8  push    rdi
0x1800019b9  push    r12
0x1800019bb  push    r13
0x1800019bd  push    r14
0x1800019bf  push    r15
0x1800019c1  lea     rbp, [rsp-0Fh]
0x1800019c6  sub     rsp, 98h
0x1800019cd  mov     r13, r9
0x1800019d0  mov     r14, r8
0x1800019d3  mov     r12, rdx
0x1800019d6  mov     edi, ecx
0x1800019d8  xorps   xmm0, xmm0
0x1800019db  xor     eax, eax
0x1800019dd  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x1800019e1  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x1800019e5  lea     rbx, WPP_GLOBAL_Control
0x1800019ec  mov     r15d, 0FFFh
0x1800019f2  mov     esi, [rbp+47h+arg_20]
0x1800019f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800019fc  cmp     rax, rbx
0x1800019ff  jnz     loc_180001E95
0x180001a05  mov     r14d, 8
0x180001a0b  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180001a0f  call    cs:__imp_VariantClear
0x180001a15  test    sil, 30h
0x180001a19  jz      loc_180001F33
0x180001a1f  mov     eax, esi
0x180001a21  and     eax, 30h
0x180001a24  cmp     al, 30h ; '0'
0x180001a26  jz      loc_180001B2E
0x180001a2c  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180001a33  test    sil, 20h
0x180001a37  jnz     short loc_180001A65
0x180001a39  test    sil, 10h
0x180001a3d  jnz     loc_180002035
0x180001a43  cmp     rcx, rbx
0x180001a46  jnz     loc_1800022EA
0x180001a4c  mov     eax, 80070057h
0x180001a51  add     rsp, 98h
0x180001a58  pop     r15
0x180001a5a  pop     r14
0x180001a5c  pop     r13
0x180001a5e  pop     r12
0x180001a60  pop     rdi
0x180001a61  pop     rsi
0x180001a62  pop     rbx
0x180001a63  pop     rbp
0x180001a64  retn
0x180001a65  mov     eax, 28h ; '('
0x180001a6a  mov     edx, 20h ; ' '; int *
0x180001a6f  mov     [rbp+47h+var_68], rdx
0x180001a73  mov     [rbp+47h+var_70], rax
0x180001a77  test    sil, 7
0x180001a7b  jz      loc_180002044
0x180001a81  xor     ebx, ebx
0x180001a83  mov     [rbp+47h+var_80], ebx
0x180001a86  xor     dil, dil
0x180001a89  mov     byte ptr [rbp+47h+arg_20], dil
0x180001a8d  mov     r15d, esi
0x180001a90  and     r15d, 1
0x180001a94  jnz     loc_180001BC2
0x180001a9a  xor     r14d, r14d
0x180001a9d  test    sil, 4
0x180001aa1  jnz     loc_180001BC2
0x180001aa7  lea     r13, WPP_GLOBAL_Control
0x180001aae  mov     [rbp+47h+hKey], 0
0x180001ab6  test    sil, 2
0x180001aba  jz      loc_180002161
0x180001ac0  mov     [rbp+47h+hKey], 0FFFFFFFF80000002h
0x180001ac8  test    r14d, r14d
0x180001acb  jns     loc_180001C23
0x180001ad1  mov     rsi, [rbp+47h+pvarSrc]
0x180001ad5  add     r12, 30h ; '0'
0x180001ad9  cmp     word ptr [r12], 0
0x180001adf  jz      loc_180001C5F
0x180001ae5  cmp     rcx, r13
0x180001ae8  jz      short loc_180001B0C
0x180001aea  test    byte ptr [rcx+1Ch], 2
0x180001aee  jz      short loc_180001B0C
0x180001af0  mov     edx, 1Fh
0x180001af5  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180001afc  mov     rcx, [rcx+10h]
0x180001b00  call    WPP_SF_
0x180001b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b0c  cmp     rsi, r12
0x180001b0f  jz      short loc_180001B23
0x180001b11  mov     rdx, r12; struct tagVARIANT *
0x180001b14  mov     rcx, rsi; this
0x180001b17  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180001b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b23  mov     r14d, 1
0x180001b29  jmp     loc_180001C5F
0x180001b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b35  cmp     rcx, rbx
0x180001b38  jnz     loc_180001F42
0x180001b3e  cmp     edi, 1
0x180001b41  jnz     loc_180001F70
0x180001b47  xor     r9d, r9d
0x180001b4a  xorps   xmm0, xmm0
0x180001b4d  xor     eax, eax
0x180001b4f  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x180001b53  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x180001b57  mov     word ptr [rbp+47h+pvarg], ax
0x180001b5b  mov     [rsp+0D0h+var_98], rax
0x180001b60  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180001b64  mov     [rsp+0D0h+var_A8], rax
0x180001b69  lea     rax, [rbp+47h+pvarg]
0x180001b6d  mov     [rsp+0D0h+phkResult], rax
0x180001b72  mov     r8d, 3
0x180001b78  lea     rdx, qword_18002D760
0x180001b7f  xor     ecx, ecx
0x180001b81  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180001b86  test    eax, eax
0x180001b88  jns     loc_180001FBD
0x180001b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b95  cmp     rcx, rbx
0x180001b98  jnz     loc_180002007
0x180001b9e  cmp     word ptr [rbp+47h+pvarg], r15w
0x180001ba3  jz      loc_18000202B
0x180001ba9  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180001bad  call    cs:__imp_VariantClear
0x180001bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bba  and     esi, 0FFFFFFDFh
0x180001bbd  jmp     loc_180001A33
0x180001bc2  test    r13, r13
0x180001bc5  jz      loc_180002051
0x180001bcb  mov     r14d, 1
0x180001bd1  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x180001bd6  test    al, al
0x180001bd8  jnz     short loc_180001BF6
0x180001bda  mov     rcx, r13; hToken
0x180001bdd  call    cs:__imp_ImpersonateLoggedOnUser
0x180001be3  test    eax, eax
0x180001be5  jz      loc_180001CDC
0x180001beb  movzx   edi, r14b
0x180001bef  mov     byte ptr [rbp+47h+arg_20], r14b
0x180001bf3  xor     r14d, r14d
0x180001bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bfd  lea     r13, WPP_GLOBAL_Control
0x180001c04  cmp     rcx, r13
0x180001c07  jnz     loc_18000209B
0x180001c0d  test    r14d, r14d
0x180001c10  js      loc_1800020F7
0x180001c16  mov     rax, [rbp+47h+var_70]
0x180001c1a  mov     rdx, [rbp+47h+var_68]
0x180001c1e  jmp     loc_180001AAE
0x180001c23  mov     rsi, [rbp+47h+pvarSrc]
0x180001c27  mov     [rsp+0D0h+phkResult], rsi; struct ATL::CComVariant *
0x180001c2c  movzx   r9d, word ptr [r12+4]; unsigned __int16
0x180001c32  mov     r8, [rax+r12]; unsigned __int16 *
0x180001c36  mov     rdx, [rdx+r12]; unsigned __int16 *
0x180001c3a  mov     rcx, [rbp+47h+hKey]; HKEY
0x180001c3e  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x180001c43  mov     r14d, eax
0x180001c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c4d  cmp     rcx, r13
0x180001c50  jnz     loc_1800021F3
0x180001c56  test    r14d, r14d
0x180001c59  js      loc_180001AD5
0x180001c5f  xorps   xmm0, xmm0
0x180001c62  xor     eax, eax
0x180001c64  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x180001c68  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x180001c6c  cmp     rcx, r13
0x180001c6f  jnz     loc_180002221
0x180001c75  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180001c79  call    cs:__imp_VariantClear
0x180001c7f  nop
0x180001c80  mov     rcx, [rbp+47h+hKey]; hKey
0x180001c84  test    rcx, rcx
0x180001c87  jnz     short loc_180001CA2
0x180001c89  test    dil, dil
0x180001c8c  jnz     loc_180002288
0x180001c92  test    ebx, ebx
0x180001c94  jnz     loc_180002127
0x180001c9a  mov     eax, r14d
0x180001c9d  jmp     loc_180001A51
0x180001ca2  call    cs:__imp_RegCloseKey
0x180001ca8  nop
0x180001ca9  jmp     short loc_180001C89
0x180001cab  xor     ebx, ebx
0x180001cad  cmp     byte ptr [rbp+47h+pvarg+8], 1
0x180001cb1  setz    bl
0x180001cb4  lea     rcx, [rbp+47h+pvarg]; this
0x180001cb8  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180001cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cc4  cmp     ebx, 1
0x180001cc7  lea     rbx, WPP_GLOBAL_Control
0x180001cce  jnz     loc_180001BBA
0x180001cd4  and     esi, 0FFFFFFEFh
0x180001cd7  jmp     loc_180001A33
0x180001cdc  call    cs:__imp_GetLastError
0x180001ce2  mov     r14d, eax
0x180001ce5  test    eax, eax
0x180001ce7  jle     loc_180001BF6
0x180001ced  movzx   r14d, ax
0x180001cf1  or      r14d, 80070000h
0x180001cf8  jmp     loc_180001BF6
0x180001cfd  xor     edx, edx
0x180001cff  lea     rcx, [rbp+47h+hKey]
0x180001d03  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180001d08  lea     rdx, [rbp+47h+hKey]; phkResult
0x180001d0c  mov     ecx, 20019h; samDesired
0x180001d11  call    cs:__imp_RegOpenCurrentUser
0x180001d17  mov     r14d, eax
0x180001d1a  test    eax, eax
0x180001d1c  jle     short loc_180001D29
0x180001d1e  movzx   r14d, ax
0x180001d22  or      r14d, 80070000h
0x180001d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d30  cmp     rcx, r13
0x180001d33  jz      short loc_180001D5A
0x180001d35  test    byte ptr [rcx+1Ch], 2
0x180001d39  jz      short loc_180001D5A
0x180001d3b  mov     edx, 1Ah
0x180001d40  mov     r9d, r14d
0x180001d43  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180001d4a  mov     rcx, [rcx+10h]
0x180001d4e  call    WPP_SF_d
0x180001d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d5a  mov     rax, [rbp+47h+var_70]
0x180001d5e  mov     rdx, [rbp+47h+var_68]
0x180001d62  jmp     loc_180001AC8
0x180001d67  xor     edx, edx
0x180001d69  lea     rcx, [rbp+47h+hKey]
0x180001d6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180001d72  lea     rax, [rbp+47h+hKey]
0x180001d76  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180001d7b  mov     r9d, 20019h; samDesired
0x180001d81  xor     r8d, r8d; ulOptions
0x180001d84  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x180001d88  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180001d8f  call    cs:__imp_RegOpenKeyExW
0x180001d95  mov     esi, eax
0x180001d97  test    eax, eax
0x180001d99  jle     short loc_180001DA4
0x180001d9b  movzx   esi, ax
0x180001d9e  or      esi, 80070000h
0x180001da4  test    esi, esi
0x180001da6  jns     loc_1800021E6
0x180001dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180001db3  cmp     rcx, r13
0x180001db6  jz      short loc_180001DD7
0x180001db8  test    byte ptr [rcx+1Ch], 2
0x180001dbc  jz      short loc_180001DD7
0x180001dbe  mov     edx, 1Ch
0x180001dc3  mov     r9d, esi
0x180001dc6  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180001dcd  mov     rcx, [rcx+10h]
0x180001dd1  call    WPP_SF_d
0x180001dd6  nop
0x180001dd7  lea     rcx, [rbp+47h+hKey]
0x180001ddb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180001de0  nop
0x180001de1  lea     rcx, [rbp+47h+arg_20]; this
0x180001de5  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180001dea  nop
0x180001deb  test    ebx, ebx
0x180001ded  jnz     loc_1800021AC
0x180001df3  mov     eax, esi
0x180001df5  jmp     loc_180001A51
0x180001dfa  lea     rcx, [rbp+47h+arg_20]; this
0x180001dfe  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180001e03  nop
0x180001e04  test    ebx, ebx
0x180001e06  jz      loc_180001C9A
0x180001e0c  call    cs:__imp_CoRevertToSelf
0x180001e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e19  cmp     rcx, r13
0x180001e1c  jmp     loc_180002137
0x180001e21  lea     rcx, [rbp+47h+hKey]
0x180001e25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180001e2a  nop
0x180001e2b  lea     rcx, [rbp+47h+arg_20]; this
0x180001e2f  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180001e34  nop
0x180001e35  test    ebx, ebx
0x180001e37  jz      loc_180001A4C
0x180001e3d  call    cs:__imp_CoRevertToSelf
0x180001e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e4a  cmp     rcx, r13
0x180001e4d  jmp     short loc_180001E7B
0x180001e4f  lea     rcx, [rbp+47h+hKey]
0x180001e53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180001e58  nop
0x180001e59  lea     rcx, [rbp+47h+arg_20]; this
0x180001e5d  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180001e62  nop
0x180001e63  test    ebx, ebx
0x180001e65  jz      loc_180001A4C
0x180001e6b  call    cs:__imp_CoRevertToSelf
0x180001e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e78  cmp     rcx, r13
0x180001e7b  jz      loc_180001A4C
0x180001e81  test    byte ptr [rcx+1Ch], 2
0x180001e85  jz      loc_180001A4C
  ... truncated ...
```
