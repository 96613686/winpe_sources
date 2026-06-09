# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x18000ab6c`
- end: `0x18000b1a0`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `1588`
- prototype: `int __high(enum UST_COMPONENT_ID, const struct USERSTATE_SETTING_DESCRIPTOR *, struct ATL::CComVariant *, void *, enum USERSTATE_SETTING_SOURCES, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180028678`

## callees

- `0x18000a5a0`
- `0x18000ab6c`
- `0x18000b1a8`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800140c8`
- `0x18001957c`
- `0x180027fd0`
- `0x180028048`
- `0x180028508`
- `0x18002894c`
- `0x1800289d4`
- `0x180029af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000adbd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000af1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000afb9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b0bf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b134`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000adbd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000af1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000afb9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b0bf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b134`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000ae0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000ae0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000af56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000af56`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab98`
- `OLEAUT32!__imp_VariantInit` at `0x18000b034`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab98`
- `OLEAUT32!__imp_VariantInit` at `0x18000b034`
- `OLEAUT32!__imp_VariantClear` at `0x18000ac3b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0a0`
- `OLEAUT32!__imp_VariantClear` at `0x18000ac3b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0a0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000abe6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b06b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000abe6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b06b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetUserStateSettingPriv(
        unsigned int a1,
        __int64 a2,
        struct ATL::CComVariant *a3,
        void *a4,
        int a5,
        LPCWSTR lpSubKey)
{
  int v10; // esi
  LPCWSTR v11; // rbx
  VARIANTARG *p_pvarg; // rdx
  HRESULT v13; // eax
  int v14; // edx
  int v15; // r8d
  const wchar_t *bstrVal; // rcx
  int *v17; // rdx
  int v18; // ebx
  unsigned int StoredValue; // edi
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // eax
  LSTATUS v24; // eax
  __int64 v25; // rcx
  ATL::CComVariant *v26; // r15
  const WCHAR *v27; // rdi
  LSTATUS v28; // eax
  VARIANTARG *v29; // rdx
  HRESULT v30; // eax
  const wchar_t *v31; // r9
  int v32; // [rsp+50h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-31h] BYREF
  __int64 v34; // [rsp+60h] [rbp-29h]
  __int64 v35; // [rsp+68h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF

  VariantInit(&pvarg);
  v10 = a5;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v11 = L"NULL";
    if ( lpSubKey )
      v11 = lpSubKey;
    p_pvarg = &pvarg;
    if ( a3 )
      p_pvarg = (VARIANTARG *)a3;
    v13 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v13 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_dddSqDS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v14,
      v15,
      a1,
      *(_DWORD *)a2,
      *(_WORD *)a3,
      (__int64)bstrVal,
      (char)a4,
      v10,
      (__int64)v11);
  }
  VariantClear(&pvarg);
  if ( (v10 & 0x30) == 0 )
    v10 |= *(_DWORD *)(a2 + 8) & 0x30;
  if ( (v10 & 0x30) == 0x30 )
  {
    if ( (unsigned int)GetSettingAuthority(a1) == 1 )
      LOBYTE(v10) = v10 & 0xEF;
    else
      LOBYTE(v10) = v10 & 0xDF;
  }
  if ( (v10 & 0x20) != 0 )
  {
    v34 = 40;
    v35 = 32;
  }
  else
  {
    v35 = 16;
    if ( (v10 & 0x10) == 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
      return 2147942487LL;
    }
    v34 = 24;
  }
  if ( (v10 & 7) == 0 )
    v10 = *(_DWORD *)(a2 + 8) & 7;
  v18 = 0;
  v32 = 0;
  LOBYTE(a5) = 0;
  if ( (v10 & 1) == 0 )
  {
    StoredValue = 0;
    if ( (v10 & 4) == 0 )
    {
      v20 = WPP_GLOBAL_Control;
      goto LABEL_25;
    }
  }
  if ( !a4 )
  {
    v21 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v32, v17);
    StoredValue = v21;
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
    {
      v18 = v32;
      goto LABEL_36;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v21);
    v18 = v32;
    goto LABEL_35;
  }
  v22 = UstCommon::CImpersonator::Impersonate((UstCommon::CImpersonator *)&a5, a4);
  StoredValue = v22;
  v20 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v22);
LABEL_35:
    v20 = WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( (StoredValue & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(v20 + 16), 25, WPP_313c576492293c0704086ae70e07ed75_Traceguids, StoredValue);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( v18 )
    {
      CoRevertToSelf();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    }
    return StoredValue;
  }
LABEL_25:
  phkResult = 0;
  if ( (v10 & 2) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      -2147483646);
    goto LABEL_51;
  }
  if ( (v10 & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v24 = RegOpenCurrentUser(0x20019u, &phkResult);
    StoredValue = v24;
    if ( v24 > 0 )
      StoredValue = (unsigned __int16)v24 | 0x80070000;
    v25 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
    {
LABEL_52:
      if ( (StoredValue & 0x80000000) != 0 )
      {
        v26 = a3;
LABEL_77:
        if ( *(_WORD *)(a2 + 48) )
        {
          if ( (_UNKNOWN *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 2) != 0 )
            WPP_SF_(*(_QWORD *)(v25 + 16), 31, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
          if ( v26 != (ATL::CComVariant *)(a2 + 48) )
            ATL::CComVariant::InternalCopy(v26, (const struct tagVARIANT *)(a2 + 48));
          StoredValue = 1;
        }
LABEL_84:
        VariantInit(&pvarg);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v29 = &pvarg;
          if ( v26 )
            v29 = (VARIANTARG *)v26;
          v30 = VariantChangeType(&pvarg, v29, 0, 8u);
          v31 = L"<undefined>";
          if ( v30 >= 0 )
            LODWORD(v31) = pvarg.lVal;
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            32,
            (unsigned int)WPP_313c576492293c0704086ae70e07ed75_Traceguids,
            (_DWORD)v31,
            StoredValue);
        }
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
        if ( v18 )
        {
          CoRevertToSelf();
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
        }
        return StoredValue;
      }
LABEL_53:
      v26 = a3;
      StoredValue = GetStoredValue(
                      phkResult,
                      *(LPCWSTR *)(v35 + a2),
                      *(const unsigned __int16 **)(v34 + a2),
                      *(_WORD *)(a2 + 4),
                      a3);
      v25 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          30,
          WPP_313c576492293c0704086ae70e07ed75_Traceguids,
          StoredValue);
        v25 = WPP_GLOBAL_Control;
      }
      if ( (StoredValue & 0x80000000) == 0 )
        goto LABEL_84;
      goto LABEL_77;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_313c576492293c0704086ae70e07ed75_Traceguids, StoredValue);
LABEL_51:
    v25 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  if ( (v10 & 4) == 0 )
  {
    if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(v20 + 16), 29, WPP_313c576492293c0704086ae70e07ed75_Traceguids, StoredValue);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v18 )
      return 2147942487LL;
    goto LABEL_100;
  }
  v27 = lpSubKey;
  if ( lpSubKey )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v28 = RegOpenKeyExW(HKEY_USERS, v27, 0, 0x20019u, &phkResult);
    StoredValue = v28;
    if ( v28 > 0 )
      StoredValue = (unsigned __int16)v28 | 0x80070000;
    if ( (StoredValue & 0x80000000) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          28,
          WPP_313c576492293c0704086ae70e07ed75_Traceguids,
          StoredValue);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
      if ( v18 )
      {
        CoRevertToSelf();
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
      }
      return StoredValue;
    }
    goto LABEL_53;
  }
  if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(v20 + 16), 27, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
  if ( v18 )
  {
LABEL_100:
    CoRevertToSelf();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000ab6c  mov     [rsp-8+pvarSrc], r8
0x18000ab71  push    rbp
0x18000ab72  push    rbx
0x18000ab73  push    rsi
0x18000ab74  push    rdi
0x18000ab75  push    r12
0x18000ab77  push    r13
0x18000ab79  push    r14
0x18000ab7b  push    r15
0x18000ab7d  lea     rbp, [rsp-0Fh]
0x18000ab82  sub     rsp, 98h
0x18000ab89  mov     r13, r9
0x18000ab8c  mov     r14, r8
0x18000ab8f  mov     r12, rdx
0x18000ab92  mov     edi, ecx
0x18000ab94  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000ab98  call    cs:__imp_VariantInit
0x18000ab9e  lea     rbx, WPP_GLOBAL_Control
0x18000aba5  xor     r15d, r15d
0x18000aba8  mov     rcx, [rbp+47h+lpSubKey]
0x18000abac  mov     esi, [rbp+47h+arg_20]
0x18000abaf  mov     rax, cs:WPP_GLOBAL_Control
0x18000abb6  cmp     rax, rbx
0x18000abb9  jz      short loc_18000AC37
0x18000abbb  test    byte ptr [rax+1Ch], 2
0x18000abbf  jz      short loc_18000AC37
0x18000abc1  lea     rbx, aNull_1; "NULL"
0x18000abc8  test    rcx, rcx
0x18000abcb  cmovnz  rbx, rcx
0x18000abcf  lea     rdx, [rbp+47h+pvarg]
0x18000abd3  test    r14, r14
0x18000abd6  cmovnz  rdx, r14; pvarSrc
0x18000abda  mov     r9w, 8; vt
0x18000abdf  xor     r8d, r8d; wFlags
0x18000abe2  lea     rcx, [rbp+47h+pvarg]; pvargDest
0x18000abe6  call    cs:__imp_VariantChangeType
0x18000abec  lea     rcx, aUndefined; "<undefined>"
0x18000abf3  test    eax, eax
0x18000abf5  cmovns  rcx, qword ptr [rbp+47h+pvarg+8]
0x18000abfa  movzx   eax, word ptr [r14]
0x18000abfe  mov     [rsp+0D0h+var_88], rbx
0x18000ac03  mov     [rsp+0D0h+var_90], esi
0x18000ac07  mov     [rsp+0D0h+var_98], r13
0x18000ac0c  mov     [rsp+0D0h+var_A0], rcx
0x18000ac11  mov     [rsp+0D0h+var_A8], eax
0x18000ac15  mov     eax, [r12]
0x18000ac19  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000ac1d  mov     r9d, edi
0x18000ac20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac27  mov     rcx, [rcx+10h]
0x18000ac2b  call    WPP_SF_dddSqDS
0x18000ac30  lea     rbx, WPP_GLOBAL_Control
0x18000ac37  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000ac3b  call    cs:__imp_VariantClear
0x18000ac41  test    sil, 30h
0x18000ac45  jnz     short loc_18000AC51
0x18000ac47  mov     eax, [r12+8]
0x18000ac4c  and     eax, 30h
0x18000ac4f  or      esi, eax
0x18000ac51  mov     eax, esi
0x18000ac53  and     eax, 30h
0x18000ac56  cmp     al, 30h ; '0'
0x18000ac58  jnz     short loc_18000AC6E
0x18000ac5a  mov     ecx, edi
0x18000ac5c  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x18000ac61  cmp     eax, 1
0x18000ac64  jnz     short loc_18000AC6B
0x18000ac66  and     esi, 0FFFFFFEFh
0x18000ac69  jmp     short loc_18000AC6E
0x18000ac6b  and     esi, 0FFFFFFDFh
0x18000ac6e  test    sil, 20h
0x18000ac72  jz      short loc_18000AC86
0x18000ac74  mov     [rbp+47h+var_70], 28h ; '('
0x18000ac7c  mov     [rbp+47h+var_68], 20h ; ' '
0x18000ac84  jmp     short loc_18000ACA0
0x18000ac86  mov     eax, 10h
0x18000ac8b  mov     [rbp+47h+var_68], rax
0x18000ac8f  test    al, sil
0x18000ac92  jz      loc_18000B160
0x18000ac98  mov     [rbp+47h+var_70], 18h
0x18000aca0  test    sil, 7
0x18000aca4  jnz     short loc_18000ACAE
0x18000aca6  mov     esi, [r12+8]
0x18000acab  and     esi, 7
0x18000acae  mov     ebx, r15d
0x18000acb1  mov     [rbp+47h+var_80], ebx
0x18000acb4  mov     byte ptr [rbp+47h+arg_20], r15b
0x18000acb8  mov     r15d, esi
0x18000acbb  lea     r14, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000acc2  and     r15d, 1
0x18000acc6  jnz     short loc_18000ACFE
0x18000acc8  xor     eax, eax
0x18000acca  mov     edi, eax
0x18000accc  test    sil, 4
0x18000acd0  jnz     short loc_18000ACFE
0x18000acd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acd9  mov     [rbp+47h+phkResult], rax
0x18000acdd  mov     r13b, 2
0x18000ace0  test    r13b, sil
0x18000ace3  jz      loc_18000ADEE
0x18000ace9  mov     rdx, 0FFFFFFFF80000002h
0x18000acf0  lea     rcx, [rbp+47h+phkResult]
0x18000acf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000acf9  jmp     loc_18000AE4D
0x18000acfe  test    r13, r13
0x18000ad01  jnz     short loc_18000AD45
0x18000ad03  lea     rcx, [rbp+47h+var_80]; this
0x18000ad07  call    ?Impersonate@CComImpersonator@UstCommon@@QEAAJPEAH@Z; UstCommon::CComImpersonator::Impersonate(int *)
0x18000ad0c  mov     edi, eax
0x18000ad0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad15  lea     r13, WPP_GLOBAL_Control
0x18000ad1c  cmp     rcx, r13
0x18000ad1f  jz      short loc_18000AD40
0x18000ad21  test    byte ptr [rcx+1Ch], 2
0x18000ad25  jz      short loc_18000AD40
0x18000ad27  mov     edx, 17h
0x18000ad2c  mov     r9d, eax
0x18000ad2f  mov     r8, r14
0x18000ad32  mov     rcx, [rcx+10h]
0x18000ad36  call    WPP_SF_d
0x18000ad3b  mov     ebx, [rbp+47h+var_80]
0x18000ad3e  jmp     short loc_18000AD80
0x18000ad40  mov     ebx, [rbp+47h+var_80]
0x18000ad43  jmp     short loc_18000AD87
0x18000ad45  mov     rdx, r13; void *
0x18000ad48  lea     rcx, [rbp+47h+arg_20]; this
0x18000ad4c  call    ?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z; UstCommon::CImpersonator::Impersonate(void *)
0x18000ad51  mov     edi, eax
0x18000ad53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad5a  lea     r13, WPP_GLOBAL_Control
0x18000ad61  cmp     rcx, r13
0x18000ad64  jz      short loc_18000AD87
0x18000ad66  test    byte ptr [rcx+1Ch], 2
0x18000ad6a  jz      short loc_18000AD87
0x18000ad6c  mov     edx, 18h
0x18000ad71  mov     r9d, eax
0x18000ad74  mov     r8, r14
0x18000ad77  mov     rcx, [rcx+10h]
0x18000ad7b  call    WPP_SF_d
0x18000ad80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad87  xor     eax, eax
0x18000ad89  test    edi, edi
0x18000ad8b  jns     loc_18000ACD9
0x18000ad91  cmp     rcx, r13
0x18000ad94  jz      short loc_18000ADAF
0x18000ad96  test    byte ptr [rcx+1Ch], 2
0x18000ad9a  jz      short loc_18000ADAF
0x18000ad9c  lea     edx, [rax+19h]
0x18000ad9f  mov     r9d, edi
0x18000ada2  mov     r8, r14
0x18000ada5  mov     rcx, [rcx+10h]
0x18000ada9  call    WPP_SF_d
0x18000adae  nop
0x18000adaf  lea     rcx, [rbp+47h+arg_20]; this
0x18000adb3  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000adb8  nop
0x18000adb9  test    ebx, ebx
0x18000adbb  jz      short loc_18000ADE7
0x18000adbd  call    cs:__imp_CoRevertToSelf
0x18000adc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adca  cmp     rcx, r13
0x18000adcd  jz      short loc_18000ADE7
0x18000adcf  test    byte ptr [rcx+1Ch], 2
0x18000add3  jz      short loc_18000ADE7
0x18000add5  mov     edx, 0Bh
0x18000adda  mov     r8, r14
0x18000addd  mov     rcx, [rcx+10h]
0x18000ade1  call    WPP_SF_
0x18000ade6  nop
0x18000ade7  mov     eax, edi
0x18000ade9  jmp     loc_18000B18C
0x18000adee  test    r15d, r15d
0x18000adf1  jz      loc_18000AEC7
0x18000adf7  xor     edx, edx
0x18000adf9  lea     rcx, [rbp+47h+phkResult]
0x18000adfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ae02  lea     rdx, [rbp+47h+phkResult]; phkResult
0x18000ae06  mov     ecx, 20019h; samDesired
0x18000ae0b  call    cs:__imp_RegOpenCurrentUser
0x18000ae11  mov     edi, eax
0x18000ae13  test    eax, eax
0x18000ae15  jle     short loc_18000AE20
0x18000ae17  movzx   edi, ax
0x18000ae1a  or      edi, 80070000h
0x18000ae20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae27  lea     rax, WPP_GLOBAL_Control
0x18000ae2e  cmp     rcx, rax
0x18000ae31  jz      short loc_18000AE54
0x18000ae33  test    [rcx+1Ch], r13b
0x18000ae37  jz      short loc_18000AE54
0x18000ae39  mov     edx, 1Ah
0x18000ae3e  mov     r9d, edi
0x18000ae41  mov     r8, r14
0x18000ae44  mov     rcx, [rcx+10h]
0x18000ae48  call    WPP_SF_d
0x18000ae4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae54  test    edi, edi
0x18000ae56  js      loc_18000AFE8
0x18000ae5c  mov     r15, [rbp+47h+pvarSrc]
0x18000ae60  mov     [rsp+0D0h+var_B0], r15; struct ATL::CComVariant *
0x18000ae65  movzx   r9d, word ptr [r12+4]; unsigned __int16
0x18000ae6b  mov     r8, [rbp+47h+var_70]
0x18000ae6f  mov     r8, [r8+r12]; unsigned __int16 *
0x18000ae73  mov     rdx, [rbp+47h+var_68]
0x18000ae77  mov     rdx, [rdx+r12]; lpSubKey
0x18000ae7b  mov     rcx, [rbp+47h+phkResult]; hKey
0x18000ae7f  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18000ae84  mov     edi, eax
0x18000ae86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae8d  lea     rax, WPP_GLOBAL_Control
0x18000ae94  cmp     rcx, rax
0x18000ae97  jz      short loc_18000AEBA
0x18000ae99  test    [rcx+1Ch], r13b
0x18000ae9d  jz      short loc_18000AEBA
0x18000ae9f  mov     edx, 1Eh
0x18000aea4  mov     r9d, edi
0x18000aea7  mov     r8, r14
0x18000aeaa  mov     rcx, [rcx+10h]
0x18000aeae  call    WPP_SF_d
0x18000aeb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeba  test    edi, edi
0x18000aebc  jns     loc_18000B030
0x18000aec2  jmp     loc_18000AFEC
0x18000aec7  test    sil, 4
0x18000aecb  jz      loc_18000B0F5
0x18000aed1  mov     rdi, [rbp+47h+lpSubKey]
0x18000aed5  test    rdi, rdi
0x18000aed8  jnz     short loc_18000AF2F
0x18000aeda  lea     rdi, WPP_GLOBAL_Control
0x18000aee1  cmp     rcx, rdi
0x18000aee4  jz      short loc_18000AEFE
0x18000aee6  test    [rcx+1Ch], r13b
0x18000aeea  jz      short loc_18000AEFE
0x18000aeec  mov     edx, 1Bh
0x18000aef1  mov     r8, r14
0x18000aef4  mov     rcx, [rcx+10h]
0x18000aef8  call    WPP_SF_
0x18000aefd  nop
0x18000aefe  lea     rcx, [rbp+47h+phkResult]
0x18000af02  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000af07  nop
0x18000af08  lea     rcx, [rbp+47h+arg_20]; this
0x18000af0c  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000af11  nop
0x18000af12  test    ebx, ebx
0x18000af14  jz      loc_18000B15E
0x18000af1a  call    cs:__imp_CoRevertToSelf
0x18000af20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af27  cmp     rcx, rdi
0x18000af2a  jmp     loc_18000B144
0x18000af2f  xor     edx, edx
0x18000af31  lea     rcx, [rbp+47h+phkResult]
0x18000af35  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000af3a  lea     rax, [rbp+47h+phkResult]
0x18000af3e  mov     [rsp+0D0h+var_B0], rax; phkResult
0x18000af43  mov     r9d, 20019h; samDesired
0x18000af49  xor     r8d, r8d; ulOptions
0x18000af4c  mov     rdx, rdi; lpSubKey
0x18000af4f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000af56  call    cs:__imp_RegOpenKeyExW
0x18000af5c  mov     edi, eax
0x18000af5e  test    eax, eax
0x18000af60  jle     short loc_18000AF6B
0x18000af62  movzx   edi, ax
0x18000af65  or      edi, 80070000h
0x18000af6b  test    edi, edi
0x18000af6d  jns     loc_18000AE5C
0x18000af73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af7a  lea     r15, WPP_GLOBAL_Control
0x18000af81  cmp     rcx, r15
0x18000af84  jz      short loc_18000AFA1
0x18000af86  test    [rcx+1Ch], r13b
0x18000af8a  jz      short loc_18000AFA1
0x18000af8c  mov     edx, 1Ch
0x18000af91  mov     r9d, edi
0x18000af94  mov     r8, r14
0x18000af97  mov     rcx, [rcx+10h]
0x18000af9b  call    WPP_SF_d
0x18000afa0  nop
0x18000afa1  lea     rcx, [rbp+47h+phkResult]
0x18000afa5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000afaa  nop
0x18000afab  lea     rcx, [rbp+47h+arg_20]; this
0x18000afaf  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000afb4  nop
0x18000afb5  test    ebx, ebx
0x18000afb7  jz      short loc_18000AFE3
0x18000afb9  call    cs:__imp_CoRevertToSelf
0x18000afbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afc6  cmp     rcx, r15
0x18000afc9  jz      short loc_18000AFE3
0x18000afcb  test    [rcx+1Ch], r13b
0x18000afcf  jz      short loc_18000AFE3
0x18000afd1  mov     edx, 0Bh
0x18000afd6  mov     r8, r14
0x18000afd9  mov     rcx, [rcx+10h]
0x18000afdd  call    WPP_SF_
0x18000afe2  nop
0x18000afe3  jmp     loc_18000ADE7
0x18000afe8  mov     r15, [rbp+47h+pvarSrc]
  ... truncated ...
```
