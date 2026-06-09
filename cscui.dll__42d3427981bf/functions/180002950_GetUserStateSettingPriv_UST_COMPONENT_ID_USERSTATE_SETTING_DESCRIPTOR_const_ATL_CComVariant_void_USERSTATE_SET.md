# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x180002950`
- end: `0x180003287`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `2359`
- prototype: `int __high(enum UST_COMPONENT_ID, const struct USERSTATE_SETTING_DESCRIPTOR *, struct ATL::CComVariant *, void *, enum USERSTATE_SETTING_SOURCES, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003544`

## callees

- `0x180002950`
- `0x180003290`
- `0x180003544`
- `0x180003630`
- `0x180003650`
- `0x180007d80`
- `0x180010ff4`
- `0x18001101c`
- `0x180013d9c`
- `0x180013dfc`
- `0x18003acec`
- `0x18004b800`
- `0x18004bb70`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002e14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000319a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002e14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000319a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002d17`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002d17`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002e1f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002f47`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002ff7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800031a5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000321e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002e1f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002f47`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180002ff7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800031a5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000321e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002c38`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180002c38`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002e94`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002e94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003167`
- `OLEAUT32!__imp_VariantInit` at `0x18000297c`
- `OLEAUT32!__imp_VariantInit` at `0x180002ac2`
- `OLEAUT32!__imp_VariantInit` at `0x1800030ed`
- `OLEAUT32!__imp_VariantInit` at `0x18000297c`
- `OLEAUT32!__imp_VariantInit` at `0x180002ac2`
- `OLEAUT32!__imp_VariantInit` at `0x1800030ed`
- `OLEAUT32!__imp_VariantClear` at `0x180002a17`
- `OLEAUT32!__imp_VariantClear` at `0x180002b51`
- `OLEAUT32!__imp_VariantClear` at `0x180002b98`
- `OLEAUT32!__imp_VariantClear` at `0x180003157`
- `OLEAUT32!__imp_VariantClear` at `0x180002a17`
- `OLEAUT32!__imp_VariantClear` at `0x180002b51`
- `OLEAUT32!__imp_VariantClear` at `0x180002b98`
- `OLEAUT32!__imp_VariantClear` at `0x180003157`
- `OLEAUT32!__imp_VariantCopy` at `0x1800030c6`
- `OLEAUT32!__imp_VariantCopy` at `0x1800030c6`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800029c7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000311d`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800029c7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000311d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 GetUserStateSettingPriv(unsigned int a1, __int64 a2, VARIANTARG *a3, void *a4, ...)
{
  void *v4; // r14
  int v8; // esi
  LPCWSTR v9; // rbx
  VARIANTARG *p_pvarg; // rdx
  HRESULT v11; // eax
  int v12; // edx
  int v13; // r8d
  const wchar_t *bstrVal; // rcx
  UstCommon::CImpersonator *v15; // rcx
  unsigned int v16; // edi
  const wchar_t *v17; // r9
  BOOL v18; // ebx
  int v19; // ebx
  char v20; // di
  int v21; // r14d
  __int64 v22; // rdx
  signed int LastError; // eax
  LSTATUS v25; // eax
  UstCommon::CImpersonator *v26; // rcx
  LSTATUS v27; // eax
  unsigned int v28; // esi
  unsigned int StoredValue; // eax
  HRESULT v30; // eax
  VARIANTARG *v31; // rdx
  HRESULT v32; // eax
  const wchar_t *v33; // r9
  int v34; // [rsp+50h] [rbp-39h]
  HKEY phkResult; // [rsp+58h] [rbp-31h] BYREF
  void *ppInterface; // [rsp+60h] [rbp-29h] BYREF
  __int64 v37; // [rsp+68h] [rbp-21h]
  __int64 v38; // [rsp+70h] [rbp-19h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-11h] BYREF
  __int64 v41; // [rsp+100h] [rbp+77h] BYREF
  va_list va; // [rsp+100h] [rbp+77h]
  LPCWSTR lpSubKey; // [rsp+108h] [rbp+7Fh]
  va_list va1; // [rsp+110h] [rbp+87h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v41 = va_arg(va1, _QWORD);
  lpSubKey = va_arg(va1, LPCWSTR);
  v4 = a4;
  VariantInit(&pvarg);
  v8 = v41;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = L"NULL";
    if ( lpSubKey )
      v9 = lpSubKey;
    p_pvarg = &pvarg;
    if ( a3 )
      p_pvarg = a3;
    v11 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v11 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_dddSqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v13,
      a1,
      *(_DWORD *)a2,
      a3->vt,
      (__int64)bstrVal,
      (char)v4,
      v8,
      (__int64)v9);
  }
  VariantClear(&pvarg);
  if ( (v8 & 0x30) == 0 )
    v8 |= *(_DWORD *)(a2 + 8) & 0x30;
  if ( (v8 & 0x30) == 0x30 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, a1);
      v15 = WPP_GLOBAL_Control;
    }
    v16 = a1 - 1;
    if ( v16 && v16 - 1 >= 2 )
    {
      if ( v15 == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
        goto LABEL_34;
      WPP_SF_(*((_QWORD *)v15 + 2), 18, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
    }
    else
    {
      VariantInit(&pvarg);
      if ( (int)GetUserStateSetting(0, qword_1800663E0, 3) >= 0 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v17 = L"SA_WMI";
          if ( pvarg.bVal != 1 )
            v17 = L"SA_GP";
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, v17);
        }
        v18 = pvarg.bVal == 1;
        VariantClear(&pvarg);
        v15 = WPP_GLOBAL_Control;
        if ( v18 )
        {
          LOBYTE(v8) = v8 & 0xEF;
          goto LABEL_36;
        }
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
      }
      VariantClear(&pvarg);
    }
    v15 = WPP_GLOBAL_Control;
LABEL_34:
    LOBYTE(v8) = v8 & 0xDF;
    goto LABEL_36;
  }
  v15 = WPP_GLOBAL_Control;
LABEL_36:
  if ( (v8 & 0x20) != 0 )
  {
    v37 = 40;
    v38 = 32;
  }
  else
  {
    if ( (v8 & 0x10) == 0 )
    {
      if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v15 + 2), 22, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
      return 2147942487LL;
    }
    v37 = 24;
    v38 = 16;
  }
  if ( (v8 & 7) == 0 )
    v8 = *(_DWORD *)(a2 + 8) & 7;
  v19 = 0;
  v20 = 0;
  LOBYTE(v41) = 0;
  if ( (v8 & 1) == 0 )
  {
    v21 = 0;
    if ( (v8 & 4) == 0 )
      goto LABEL_88;
    v4 = a4;
  }
  if ( v4 )
  {
    v21 = 1;
    if ( !UstCommon::CImpersonator::_IsThreadImpersonating(v15) )
    {
      if ( ImpersonateLoggedOnUser(a4) )
      {
        v20 = 1;
        LOBYTE(v41) = 1;
        v21 = 0;
      }
      else
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_c06c96a323453971d4faaa040fed6bff_Traceguids,
          (unsigned int)v21);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
      {
        v22 = 24;
        goto LABEL_73;
      }
    }
  }
  else
  {
    v34 = 0;
    ppInterface = 0;
    v21 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
    if ( v21 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
        v34 = 1;
      else
        v21 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    }
    if ( v21 == -2147417833 )
    {
      v21 = 0;
    }
    else if ( v21 >= 0 && !v34 )
    {
      v19 = 1;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_c06c96a323453971d4faaa040fed6bff_Traceguids,
          (unsigned int)v21);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
      {
        v22 = 23;
LABEL_73:
        WPP_SF_d(*((_QWORD *)v15 + 2), v22, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, (unsigned int)v21);
        v15 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v21 < 0 )
  {
    if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v15 + 2), 25, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, (unsigned int)v21);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v20 )
    {
      if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v15 + 2), 12, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
      RevertToSelf();
    }
    if ( v19 )
    {
      CoRevertToSelf();
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
      }
    }
    return (unsigned int)v21;
  }
LABEL_88:
  phkResult = 0;
  if ( (v8 & 2) != 0 )
  {
    phkResult = HKEY_LOCAL_MACHINE;
    goto LABEL_96;
  }
  if ( (v8 & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v25 = RegOpenCurrentUser(0x20019u, &phkResult);
    v21 = v25;
    if ( v25 > 0 )
      v21 = (unsigned __int16)v25 | 0x80070000;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_c06c96a323453971d4faaa040fed6bff_Traceguids,
        (unsigned int)v21);
      v15 = WPP_GLOBAL_Control;
    }
LABEL_96:
    if ( v21 < 0 )
    {
LABEL_122:
      if ( *(_WORD *)(a2 + 48) )
      {
        if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)v15 + 2), 31, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
        if ( a3 != (VARIANTARG *)(a2 + 48) )
        {
          v30 = VariantCopy(a3, (const VARIANTARG *)(a2 + 48));
          if ( v30 < 0 )
          {
            a3->vt = 10;
            a3->lVal = v30;
            ATL::AtlThrowImpl(v30);
          }
        }
        v21 = 1;
      }
LABEL_130:
      VariantInit(&pvarg);
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v31 = &pvarg;
        if ( a3 )
          v31 = a3;
        v32 = VariantChangeType(&pvarg, v31, 0, 8u);
        v33 = L"<undefined>";
        if ( v32 >= 0 )
          LODWORD(v33) = pvarg.lVal;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_c06c96a323453971d4faaa040fed6bff_Traceguids,
          (_DWORD)v33,
          v21);
      }
      VariantClear(&pvarg);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
        }
        RevertToSelf();
      }
      if ( v19 )
      {
        CoRevertToSelf();
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
        }
      }
      return (unsigned int)v21;
    }
LABEL_118:
    StoredValue = GetStoredValue(
                    phkResult,
                    *(const unsigned __int16 **)(v38 + a2),
                    *(const unsigned __int16 **)(v37 + a2),
                    *(_WORD *)(a2 + 4),
                    (struct ATL::CComVariant *)a3);
    v21 = StoredValue;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, StoredValue);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v21 >= 0 )
      goto LABEL_130;
    goto LABEL_122;
  }
  if ( (v8 & 4) == 0 )
  {
    if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v15 + 2), 29, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, (unsigned int)v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
    if ( !v19 )
      return 2147942487LL;
    CoRevertToSelf();
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      return 2147942487LL;
    }
LABEL_155:
    WPP_SF_(*((_QWORD *)v26 + 2), 11, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
    return 2147942487LL;
  }
  if ( !lpSubKey )
  {
    if ( v15 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v15 + 2), 27, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
    if ( !v19 )
      return 2147942487LL;
    CoRevertToSelf();
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      return 2147942487LL;
    }
    goto LABEL_155;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v27 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &phkResult);
  v28 = v27;
  if ( v27 > 0 )
    v28 = (unsigned __int16)v27 | 0x80070000;
  if ( (v28 & 0x80000000) == 0 )
    goto LABEL_118;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, v28);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
  if ( v19 )
  {
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids);
    }
  }
  return v28;
}

```

## disassembly

```asm
0x180002950  mov     [rsp-8+hToken], r9
0x180002955  push    rbp
0x180002956  push    rbx
0x180002957  push    rsi
0x180002958  push    rdi
0x180002959  push    r12
0x18000295b  push    r13
0x18000295d  push    r14
0x18000295f  push    r15
0x180002961  lea     rbp, [rsp-0Fh]
0x180002966  sub     rsp, 98h
0x18000296d  mov     r14, r9
0x180002970  mov     r13, r8
0x180002973  mov     r12, rdx
0x180002976  mov     edi, ecx
0x180002978  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000297c  call    cs:__imp_VariantInit
0x180002982  nop
0x180002983  lea     r15, WPP_GLOBAL_Control
0x18000298a  mov     esi, dword ptr [rbp+47h+arg_20]
0x18000298d  mov     rax, cs:WPP_GLOBAL_Control
0x180002994  cmp     rax, r15
0x180002997  jz      short loc_180002A13
0x180002999  test    byte ptr [rax+1Ch], 2
0x18000299d  jz      short loc_180002A13
0x18000299f  lea     rbx, aNull_0; "NULL"
0x1800029a6  cmp     [rbp+47h+lpSubKey], 0
0x1800029ab  cmovnz  rbx, [rbp+47h+lpSubKey]
0x1800029b0  lea     rdx, [rbp+47h+pvarg]
0x1800029b4  test    r13, r13
0x1800029b7  cmovnz  rdx, r13; pvarSrc
0x1800029bb  mov     r9w, 8; vt
0x1800029c0  xor     r8d, r8d; wFlags
0x1800029c3  lea     rcx, [rbp+47h+pvarg]; pvargDest
0x1800029c7  call    cs:__imp_VariantChangeType
0x1800029cd  lea     rcx, aUndefined; "<undefined>"
0x1800029d4  test    eax, eax
0x1800029d6  cmovns  rcx, qword ptr [rbp+47h+pvarg+8]
0x1800029db  movzx   eax, word ptr [r13+0]
0x1800029e0  mov     [rsp+0D0h+var_88], rbx
0x1800029e5  mov     [rsp+0D0h+var_90], esi
0x1800029e9  mov     [rsp+0D0h+var_98], r14
0x1800029ee  mov     [rsp+0D0h+var_A0], rcx
0x1800029f3  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800029f7  mov     eax, [r12]
0x1800029fb  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800029ff  mov     r9d, edi
0x180002a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a09  mov     rcx, [rcx+10h]
0x180002a0d  call    WPP_SF_dddSqDS
0x180002a12  nop
0x180002a13  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180002a17  call    cs:__imp_VariantClear
0x180002a1d  test    sil, 30h
0x180002a21  jnz     short loc_180002A2D
0x180002a23  mov     eax, [r12+8]
0x180002a28  and     eax, 30h
0x180002a2b  or      esi, eax
0x180002a2d  mov     eax, esi
0x180002a2f  and     eax, 30h
0x180002a32  mov     edx, 1
0x180002a37  cmp     al, 30h ; '0'
0x180002a39  jnz     loc_180002BAF
0x180002a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a46  cmp     rcx, r15
0x180002a49  jz      short loc_180002A75
0x180002a4b  test    byte ptr [rcx+1Ch], 2
0x180002a4f  jz      short loc_180002A75
0x180002a51  mov     edx, 11h
0x180002a56  mov     r9d, edi
0x180002a59  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002a60  mov     rcx, [rcx+10h]
0x180002a64  call    WPP_SF_d
0x180002a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a70  mov     edx, 1
0x180002a75  sub     edi, 1
0x180002a78  jz      short loc_180002ABC
0x180002a7a  sub     edi, 1
0x180002a7d  jz      short loc_180002AB8
0x180002a7f  cmp     edi, 1
0x180002a82  jz      short loc_180002AB1
0x180002a84  cmp     rcx, r15
0x180002a87  jz      loc_180002BAA
0x180002a8d  test    byte ptr [rcx+1Ch], 2
0x180002a91  jz      loc_180002BAA
0x180002a97  mov     edx, 12h
0x180002a9c  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002aa3  mov     rcx, [rcx+10h]
0x180002aa7  call    WPP_SF_
0x180002aac  jmp     loc_180002B9E
0x180002ab1  mov     ebx, 2
0x180002ab6  jmp     short loc_180002ABE
0x180002ab8  mov     ebx, edx
0x180002aba  jmp     short loc_180002ABE
0x180002abc  xor     ebx, ebx
0x180002abe  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180002ac2  call    cs:__imp_VariantInit
0x180002ac8  nop
0x180002ac9  mov     [rsp+0D0h+var_98], 0
0x180002ad2  mov     dword ptr [rsp+0D0h+var_A0], 0
0x180002ada  mov     [rsp+0D0h+var_A8], 0
0x180002ae3  lea     rax, [rbp+47h+pvarg]
0x180002ae7  mov     [rsp+0D0h+var_B0], rax
0x180002aec  mov     r9d, ebx
0x180002aef  mov     r8d, 3
0x180002af5  lea     rdx, qword_1800663E0
0x180002afc  xor     ecx, ecx
0x180002afe  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180002b03  test    eax, eax
0x180002b05  js      short loc_180002B6C
0x180002b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b0e  cmp     rcx, r15
0x180002b11  jz      short loc_180002B44
0x180002b13  test    byte ptr [rcx+1Ch], 2
0x180002b17  jz      short loc_180002B44
0x180002b19  lea     r9, aSaWmi; "SA_WMI"
0x180002b20  lea     rax, aSaGp; "SA_GP"
0x180002b27  cmp     byte ptr [rbp+47h+pvarg+8], 1
0x180002b2b  cmovnz  r9, rax
0x180002b2f  mov     edx, 13h
0x180002b34  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002b3b  mov     rcx, [rcx+10h]
0x180002b3f  call    WPP_SF_S
0x180002b44  xor     ebx, ebx
0x180002b46  cmp     byte ptr [rbp+47h+pvarg+8], 1
0x180002b4a  setz    bl
0x180002b4d  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180002b51  call    cs:__imp_VariantClear
0x180002b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b5e  mov     edx, 1
0x180002b63  cmp     ebx, edx
0x180002b65  jnz     short loc_180002BAA
0x180002b67  and     esi, 0FFFFFFEFh
0x180002b6a  jmp     short loc_180002BB6
0x180002b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b73  cmp     rcx, r15
0x180002b76  jz      short loc_180002B94
0x180002b78  test    byte ptr [rcx+1Ch], 2
0x180002b7c  jz      short loc_180002B94
0x180002b7e  mov     edx, 14h
0x180002b83  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002b8a  mov     rcx, [rcx+10h]
0x180002b8e  call    WPP_SF_
0x180002b93  nop
0x180002b94  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180002b98  call    cs:__imp_VariantClear
0x180002b9e  mov     edx, 1
0x180002ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002baa  and     esi, 0FFFFFFDFh
0x180002bad  jmp     short loc_180002BB6
0x180002baf  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180002bb6  test    sil, 20h
0x180002bba  jz      short loc_180002BCE
0x180002bbc  mov     [rbp+47h+var_68], 28h ; '('
0x180002bc4  mov     [rbp+47h+var_60], 20h ; ' '
0x180002bcc  jmp     short loc_180002BE8
0x180002bce  test    sil, 10h
0x180002bd2  jz      loc_18000324E
0x180002bd8  mov     [rbp+47h+var_68], 18h
0x180002be0  mov     [rbp+47h+var_60], 10h
0x180002be8  test    sil, 7
0x180002bec  jnz     short loc_180002BF6
0x180002bee  mov     esi, [r12+8]
0x180002bf3  and     esi, 7
0x180002bf6  xor     ebx, ebx
0x180002bf8  mov     [rbp+47h+var_7C], ebx
0x180002bfb  xor     dil, dil
0x180002bfe  mov     byte ptr [rbp+47h+arg_20], dil
0x180002c02  mov     r15d, esi
0x180002c05  and     r15d, 1
0x180002c09  jnz     short loc_180002C1C
0x180002c0b  xor     r14d, r14d
0x180002c0e  test    sil, 4
0x180002c12  jz      loc_180002E5C
0x180002c18  mov     r14, [rbp+47h+hToken]
0x180002c1c  test    r14, r14
0x180002c1f  jnz     loc_180002D07
0x180002c25  mov     [rbp+47h+var_80], r14d
0x180002c29  mov     [rbp+47h+ppInterface], r14
0x180002c2d  lea     rdx, [rbp+47h+ppInterface]; ppInterface
0x180002c31  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180002c38  call    cs:__imp_CoGetCallContext
0x180002c3e  mov     r14d, eax
0x180002c41  test    eax, eax
0x180002c43  js      short loc_180002C85
0x180002c45  mov     rcx, [rbp+47h+ppInterface]
0x180002c49  mov     rax, [rcx]
0x180002c4c  mov     rax, [rax+30h]
0x180002c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c55  test    eax, eax
0x180002c57  jnz     short loc_180002C6E
0x180002c59  mov     rcx, [rbp+47h+ppInterface]
0x180002c5d  mov     rax, [rcx]
0x180002c60  mov     rax, [rax+20h]
0x180002c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c69  mov     r14d, eax
0x180002c6c  jmp     short loc_180002C75
0x180002c6e  mov     [rbp+47h+var_80], 1
0x180002c75  mov     rcx, [rbp+47h+ppInterface]
0x180002c79  mov     rax, [rcx]
0x180002c7c  mov     rax, [rax+10h]
0x180002c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c85  cmp     r14d, 80010117h
0x180002c8c  jnz     short loc_180002C93
0x180002c8e  xor     r14d, r14d
0x180002c91  jmp     short loc_180002CA7
0x180002c93  test    r14d, r14d
0x180002c96  js      short loc_180002CA7
0x180002c98  cmp     [rbp+47h+var_80], 0
0x180002c9c  mov     eax, 1
0x180002ca1  cmovz   ebx, eax
0x180002ca4  mov     [rbp+47h+var_7C], ebx
0x180002ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cae  lea     rax, WPP_GLOBAL_Control
0x180002cb5  cmp     rcx, rax
0x180002cb8  jz      loc_180002DB5
0x180002cbe  test    byte ptr [rcx+1Ch], 2
0x180002cc2  jz      short loc_180002CEA
0x180002cc4  mov     edx, 0Ah
0x180002cc9  mov     r9d, r14d
0x180002ccc  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002cd3  mov     rcx, [rcx+10h]
0x180002cd7  call    WPP_SF_d
0x180002cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ce3  lea     rax, WPP_GLOBAL_Control
0x180002cea  cmp     rcx, rax
0x180002ced  jz      loc_180002DB5
0x180002cf3  test    byte ptr [rcx+1Ch], 2
0x180002cf7  jz      loc_180002DB5
0x180002cfd  mov     edx, 17h
0x180002d02  jmp     loc_180002D94
0x180002d07  mov     r14d, edx
0x180002d0a  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x180002d0f  test    al, al
0x180002d11  jnz     short loc_180002D45
0x180002d13  mov     rcx, [rbp+47h+hToken]; hToken
0x180002d17  call    cs:__imp_ImpersonateLoggedOnUser
0x180002d1d  test    eax, eax
0x180002d1f  jz      short loc_180002D2D
0x180002d21  mov     dil, 1
0x180002d24  mov     byte ptr [rbp+47h+arg_20], dil
0x180002d28  xor     r14d, r14d
0x180002d2b  jmp     short loc_180002D45
0x180002d2d  call    cs:__imp_GetLastError
0x180002d33  mov     r14d, eax
0x180002d36  test    eax, eax
0x180002d38  jle     short loc_180002D45
0x180002d3a  movzx   r14d, ax
0x180002d3e  or      r14d, 80070000h
0x180002d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d4c  lea     rax, WPP_GLOBAL_Control
0x180002d53  cmp     rcx, rax
0x180002d56  jz      short loc_180002DB5
0x180002d58  test    byte ptr [rcx+1Ch], 2
0x180002d5c  jz      short loc_180002D84
0x180002d5e  mov     edx, 0Dh
0x180002d63  mov     r9d, r14d
0x180002d66  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002d6d  mov     rcx, [rcx+10h]
0x180002d71  call    WPP_SF_d
0x180002d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d7d  lea     rax, WPP_GLOBAL_Control
0x180002d84  cmp     rcx, rax
0x180002d87  jz      short loc_180002DB5
0x180002d89  test    byte ptr [rcx+1Ch], 2
0x180002d8d  jz      short loc_180002DB5
0x180002d8f  mov     edx, 18h
0x180002d94  mov     r9d, r14d
0x180002d97  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002d9e  mov     rcx, [rcx+10h]
0x180002da2  call    WPP_SF_d
0x180002da7  lea     rax, WPP_GLOBAL_Control
0x180002dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180002db5  test    r14d, r14d
0x180002db8  jns     loc_180002E5C
0x180002dbe  cmp     rcx, rax
0x180002dc1  jz      short loc_180002DEF
0x180002dc3  test    byte ptr [rcx+1Ch], 2
0x180002dc7  jz      short loc_180002DEF
0x180002dc9  mov     edx, 19h
0x180002dce  mov     r9d, r14d
0x180002dd1  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002dd8  mov     rcx, [rcx+10h]
0x180002ddc  call    WPP_SF_d
0x180002de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002de8  lea     rax, WPP_GLOBAL_Control
0x180002def  test    dil, dil
0x180002df2  jz      short loc_180002E1B
0x180002df4  cmp     rcx, rax
0x180002df7  jz      short loc_180002E14
0x180002df9  test    byte ptr [rcx+1Ch], 2
0x180002dfd  jz      short loc_180002E14
0x180002dff  mov     edx, 0Ch
0x180002e04  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x180002e0b  mov     rcx, [rcx+10h]
0x180002e0f  call    WPP_SF_
0x180002e14  call    cs:__imp_RevertToSelf
0x180002e1a  nop
0x180002e1b  test    ebx, ebx
0x180002e1d  jz      short loc_180002E54
  ... truncated ...
```
