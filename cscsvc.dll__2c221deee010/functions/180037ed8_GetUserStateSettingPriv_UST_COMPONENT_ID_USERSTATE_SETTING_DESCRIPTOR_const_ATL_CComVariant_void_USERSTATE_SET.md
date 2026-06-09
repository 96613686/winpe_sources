# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x180037ed8`
- end: `0x180038529`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `1617`
- prototype: `int __high(enum UST_COMPONENT_ID, const struct USERSTATE_SETTING_DESCRIPTOR *, struct ATL::CComVariant *, void *, enum USERSTATE_SETTING_SOURCES, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800865f4`

## callees

- `0x180030234`
- `0x180035dac`
- `0x180036394`
- `0x180037c3c`
- `0x180037ed8`
- `0x180038530`
- `0x18003c460`
- `0x18003c4e8`
- `0x180085dd8`
- `0x180085e50`
- `0x1800866c4`
- `0x18008674c`
- `0x1800867f0`
- `0x180087118`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038386`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038386`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003818e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003818e`
- `OLEAUT32!__imp_VariantChangeType` at `0x180037f56`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003826f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180037f56`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003826f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180038139`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800382c2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003834a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800383e5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800384bd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180038139`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800382c2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003834a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800383e5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800384bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  VARIANTARG *p_pvargDest; // rdx
  HRESULT v13; // eax
  int v14; // edx
  int v15; // r8d
  const wchar_t *bstrVal; // rcx
  int *v17; // rdx
  int v18; // ebx
  unsigned int v19; // edi
  CObjectMonitor *v20; // rcx
  LSTATUS v22; // eax
  CObjectMonitor *v23; // rcx
  ATL::CComVariant *v24; // r15
  VARIANTARG *v25; // rdx
  HRESULT v26; // eax
  const wchar_t *v27; // r9
  const WCHAR *v28; // rdi
  LSTATUS v29; // eax
  unsigned int StoredValue; // eax
  int v31; // [rsp+50h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-31h] BYREF
  __int64 v33; // [rsp+60h] [rbp-29h]
  __int64 v34; // [rsp+68h] [rbp-21h]
  VARIANTARG pvargDest; // [rsp+70h] [rbp-19h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  pvargDest.vt = 0;
  v10 = a5;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = L"NULL";
    if ( lpSubKey )
      v11 = lpSubKey;
    p_pvargDest = &pvargDest;
    if ( a3 )
      p_pvargDest = (VARIANTARG *)a3;
    v13 = VariantChangeType(&pvargDest, p_pvargDest, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v13 >= 0 )
      bstrVal = pvargDest.bstrVal;
    WPP_SF_dddSqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
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
  ATL::CComVariant::Clear((ATL::CComVariant *)&pvargDest);
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
    v33 = 40;
    v34 = 32;
  }
  else
  {
    v34 = 16;
    if ( (v10 & 0x10) == 0 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
      return 2147942487LL;
    }
    v33 = 24;
  }
  if ( (v10 & 7) == 0 )
    v10 = *(_DWORD *)(a2 + 8) & 7;
  v18 = 0;
  v31 = 0;
  LOBYTE(a5) = 0;
  if ( (v10 & 1) == 0 )
  {
    v19 = 0;
    if ( (v10 & 4) == 0 )
    {
      v20 = WPP_GLOBAL_Control;
      goto LABEL_25;
    }
  }
  if ( !a4 )
  {
    v19 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v31, v17);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v18 = v31;
      goto LABEL_36;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
    v18 = v31;
    goto LABEL_35;
  }
  v19 = UstCommon::CImpersonator::Impersonate((UstCommon::CImpersonator *)&a5, a4);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
LABEL_35:
    v20 = WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( (v19 & 0x80000000) != 0 )
  {
    if ( v20 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v20 + 2), 25, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( v18 )
    {
      CoRevertToSelf();
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    }
    return v19;
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
    v22 = RegOpenCurrentUser(0x20019u, &phkResult);
    v19 = v22;
    if ( v22 > 0 )
      v19 = (unsigned __int16)v22 | 0x80070000;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_52:
      if ( (v19 & 0x80000000) != 0 )
      {
        v24 = a3;
LABEL_54:
        if ( *(_WORD *)(a2 + 48) )
        {
          if ( v23 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)v23 + 2), 31, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
            v23 = WPP_GLOBAL_Control;
          }
          if ( v24 != (ATL::CComVariant *)(a2 + 48) )
          {
            ATL::CComVariant::InternalCopy(v24, (const struct tagVARIANT *)(a2 + 48));
            v23 = WPP_GLOBAL_Control;
          }
          v19 = 1;
        }
LABEL_61:
        memset(&pvargDest, 0, sizeof(pvargDest));
        pvargDest.vt = 0;
        if ( v23 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 2) != 0 )
        {
          v25 = &pvargDest;
          if ( v24 )
            v25 = (VARIANTARG *)v24;
          v26 = VariantChangeType(&pvargDest, v25, 0, 8u);
          v27 = L"<undefined>";
          if ( v26 >= 0 )
            LODWORD(v27) = pvargDest.lVal;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_313c576492293c0704086ae70e07ed75_Traceguids,
            (_DWORD)v27,
            v19);
        }
        ATL::CComVariant::Clear((ATL::CComVariant *)&pvargDest);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
        if ( v18 )
        {
          CoRevertToSelf();
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
          }
        }
        return v19;
      }
LABEL_91:
      v24 = a3;
      StoredValue = GetStoredValue(
                      phkResult,
                      *(LPCWSTR *)(v34 + a2),
                      *(const unsigned __int16 **)(v33 + a2),
                      *(_WORD *)(a2 + 4),
                      a3);
      v19 = StoredValue;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_313c576492293c0704086ae70e07ed75_Traceguids, StoredValue);
        v23 = WPP_GLOBAL_Control;
      }
      if ( (v19 & 0x80000000) == 0 )
        goto LABEL_61;
      goto LABEL_54;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
LABEL_51:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  if ( (v10 & 4) == 0 )
  {
    if ( v20 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)v20 + 2), 29, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v18 )
      return 2147942487LL;
    goto LABEL_100;
  }
  v28 = lpSubKey;
  if ( lpSubKey )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v29 = RegOpenKeyExW(HKEY_USERS, v28, 0, 0x20019u, &phkResult);
    v19 = v29;
    if ( v29 > 0 )
      v19 = (unsigned __int16)v29 | 0x80070000;
    if ( (v19 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
      if ( v18 )
      {
        CoRevertToSelf();
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
        }
      }
      return v19;
    }
    goto LABEL_91;
  }
  if ( v20 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)v20 + 2), 27, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
  if ( v18 )
  {
LABEL_100:
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180037ed8  mov     [rsp-8+pvarSrc], r8
0x180037edd  push    rbp
0x180037ede  push    rbx
0x180037edf  push    rsi
0x180037ee0  push    rdi
0x180037ee1  push    r12
0x180037ee3  push    r13
0x180037ee5  push    r14
0x180037ee7  push    r15
0x180037ee9  lea     rbp, [rsp-0Fh]
0x180037eee  sub     rsp, 98h
0x180037ef5  mov     r13, r9
0x180037ef8  mov     r14, r8
0x180037efb  mov     r12, rdx
0x180037efe  mov     edi, ecx
0x180037f00  xorps   xmm0, xmm0
0x180037f03  xor     eax, eax
0x180037f05  movups  xmmword ptr [rbp+47h+pvargDest], xmm0
0x180037f09  mov     qword ptr [rbp+47h+pvargDest+10h], rax
0x180037f0d  mov     word ptr [rbp+47h+pvargDest], ax
0x180037f11  lea     rbx, WPP_GLOBAL_Control
0x180037f18  mov     rcx, [rbp+47h+lpSubKey]
0x180037f1c  mov     esi, [rbp+47h+arg_20]
0x180037f1f  mov     rax, cs:WPP_GLOBAL_Control
0x180037f26  cmp     rax, rbx
0x180037f29  jz      short loc_180037FA7
0x180037f2b  test    byte ptr [rax+1Ch], 2
0x180037f2f  jz      short loc_180037FA7
0x180037f31  lea     rbx, aNull_0; "NULL"
0x180037f38  test    rcx, rcx
0x180037f3b  cmovnz  rbx, rcx
0x180037f3f  lea     rdx, [rbp+47h+pvargDest]
0x180037f43  test    r8, r8
0x180037f46  cmovnz  rdx, r8; pvarSrc
0x180037f4a  mov     r9w, 8; vt
0x180037f4f  xor     r8d, r8d; wFlags
0x180037f52  lea     rcx, [rbp+47h+pvargDest]; pvargDest
0x180037f56  call    cs:__imp_VariantChangeType
0x180037f5c  lea     rcx, aUndefined; "<undefined>"
0x180037f63  test    eax, eax
0x180037f65  cmovns  rcx, qword ptr [rbp+47h+pvargDest+8]
0x180037f6a  movzx   eax, word ptr [r14]
0x180037f6e  mov     [rsp+0D0h+var_88], rbx
0x180037f73  mov     [rsp+0D0h+var_90], esi
0x180037f77  mov     [rsp+0D0h+var_98], r13
0x180037f7c  mov     [rsp+0D0h+var_A0], rcx
0x180037f81  mov     [rsp+0D0h+var_A8], eax
0x180037f85  mov     eax, [r12]
0x180037f89  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180037f8d  mov     r9d, edi
0x180037f90  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f97  mov     rcx, [rcx+10h]
0x180037f9b  call    WPP_SF_dddSqDS
0x180037fa0  lea     rbx, WPP_GLOBAL_Control
0x180037fa7  lea     rcx, [rbp+47h+pvargDest]; this
0x180037fab  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180037fb0  test    sil, 30h
0x180037fb4  jnz     short loc_180037FC0
0x180037fb6  mov     eax, [r12+8]
0x180037fbb  and     eax, 30h
0x180037fbe  or      esi, eax
0x180037fc0  mov     eax, esi
0x180037fc2  and     eax, 30h
0x180037fc5  cmp     al, 30h ; '0'
0x180037fc7  jnz     short loc_180037FDD
0x180037fc9  mov     ecx, edi
0x180037fcb  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x180037fd0  cmp     eax, 1
0x180037fd3  jnz     short loc_180037FDA
0x180037fd5  and     esi, 0FFFFFFEFh
0x180037fd8  jmp     short loc_180037FDD
0x180037fda  and     esi, 0FFFFFFDFh
0x180037fdd  test    sil, 20h
0x180037fe1  jz      short loc_180037FF5
0x180037fe3  mov     [rbp+47h+var_70], 28h ; '('
0x180037feb  mov     [rbp+47h+var_68], 20h ; ' '
0x180037ff3  jmp     short loc_18003800F
0x180037ff5  mov     eax, 10h
0x180037ffa  mov     [rbp+47h+var_68], rax
0x180037ffe  test    al, sil
0x180038001  jz      loc_1800384E9
0x180038007  mov     [rbp+47h+var_70], 18h
0x18003800f  test    sil, 7
0x180038013  jnz     short loc_18003801D
0x180038015  mov     esi, [r12+8]
0x18003801a  and     esi, 7
0x18003801d  xor     ebx, ebx
0x18003801f  mov     [rbp+47h+var_80], ebx
0x180038022  mov     byte ptr [rbp+47h+arg_20], bl
0x180038025  mov     r15d, esi
0x180038028  lea     r14, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18003802f  and     r15d, 1
0x180038033  jnz     short loc_180038072
0x180038035  xor     edi, edi
0x180038037  test    sil, 4
0x18003803b  jnz     short loc_180038072
0x18003803d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038044  xor     r13d, r13d
0x180038047  mov     [rbp+47h+phkResult], r13
0x18003804b  mov     al, 2
0x18003804d  test    al, sil
0x180038050  jz      loc_180038171
0x180038056  mov     rdx, 0FFFFFFFF80000002h
0x18003805d  lea     rcx, [rbp+47h+phkResult]
0x180038061  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038066  lea     rsi, WPP_GLOBAL_Control
0x18003806d  jmp     loc_1800381D0
0x180038072  test    r13, r13
0x180038075  jnz     short loc_1800380B8
0x180038077  lea     rcx, [rbp+47h+var_80]; this
0x18003807b  call    ?Impersonate@CComImpersonator@UstCommon@@QEAAJPEAH@Z; UstCommon::CComImpersonator::Impersonate(int *)
0x180038080  mov     edi, eax
0x180038082  mov     rcx, cs:WPP_GLOBAL_Control
0x180038089  lea     rax, WPP_GLOBAL_Control
0x180038090  cmp     rcx, rax
0x180038093  jz      short loc_1800380B3
0x180038095  test    byte ptr [rcx+1Ch], 2
0x180038099  jz      short loc_1800380B3
0x18003809b  lea     edx, [r13+17h]
0x18003809f  mov     r9d, edi
0x1800380a2  mov     r8, r14
0x1800380a5  mov     rcx, [rcx+10h]
0x1800380a9  call    WPP_SF_d
0x1800380ae  mov     ebx, [rbp+47h+var_80]
0x1800380b1  jmp     short loc_1800380F3
0x1800380b3  mov     ebx, [rbp+47h+var_80]
0x1800380b6  jmp     short loc_180038101
0x1800380b8  mov     rdx, r13; void *
0x1800380bb  lea     rcx, [rbp+47h+arg_20]; this
0x1800380bf  call    ?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z; UstCommon::CImpersonator::Impersonate(void *)
0x1800380c4  mov     edi, eax
0x1800380c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380cd  lea     rax, WPP_GLOBAL_Control
0x1800380d4  cmp     rcx, rax
0x1800380d7  jz      short loc_180038101
0x1800380d9  test    byte ptr [rcx+1Ch], 2
0x1800380dd  jz      short loc_180038101
0x1800380df  mov     edx, 18h
0x1800380e4  mov     r9d, edi
0x1800380e7  mov     r8, r14
0x1800380ea  mov     rcx, [rcx+10h]
0x1800380ee  call    WPP_SF_d
0x1800380f3  lea     rax, WPP_GLOBAL_Control
0x1800380fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038101  xor     r13d, r13d
0x180038104  test    edi, edi
0x180038106  jns     loc_180038047
0x18003810c  cmp     rcx, rax
0x18003810f  jz      short loc_18003812B
0x180038111  test    byte ptr [rcx+1Ch], 2
0x180038115  jz      short loc_18003812B
0x180038117  lea     edx, [r13+19h]
0x18003811b  mov     r9d, edi
0x18003811e  mov     r8, r14
0x180038121  mov     rcx, [rcx+10h]
0x180038125  call    WPP_SF_d
0x18003812a  nop
0x18003812b  lea     rcx, [rbp+47h+arg_20]; this
0x18003812f  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180038134  nop
0x180038135  test    ebx, ebx
0x180038137  jz      short loc_18003816A
0x180038139  call    cs:__imp_CoRevertToSelf
0x18003813f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038146  lea     rsi, WPP_GLOBAL_Control
0x18003814d  cmp     rcx, rsi
0x180038150  jz      short loc_18003816A
0x180038152  test    byte ptr [rcx+1Ch], 2
0x180038156  jz      short loc_18003816A
0x180038158  mov     edx, 0Bh
0x18003815d  mov     r8, r14
0x180038160  mov     rcx, [rcx+10h]
0x180038164  call    WPP_SF_
0x180038169  nop
0x18003816a  mov     eax, edi
0x18003816c  jmp     loc_180038515
0x180038171  test    r15d, r15d
0x180038174  jz      loc_1800382F8
0x18003817a  xor     edx, edx
0x18003817c  lea     rcx, [rbp+47h+phkResult]
0x180038180  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038185  lea     rdx, [rbp+47h+phkResult]; phkResult
0x180038189  mov     ecx, 20019h; samDesired
0x18003818e  call    cs:__imp_RegOpenCurrentUser
0x180038194  mov     edi, eax
0x180038196  test    eax, eax
0x180038198  jle     short loc_1800381A3
0x18003819a  movzx   edi, ax
0x18003819d  or      edi, 80070000h
0x1800381a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381aa  lea     rsi, WPP_GLOBAL_Control
0x1800381b1  cmp     rcx, rsi
0x1800381b4  jz      short loc_1800381D7
0x1800381b6  test    byte ptr [rcx+1Ch], 2
0x1800381ba  jz      short loc_1800381D7
0x1800381bc  mov     edx, 1Ah
0x1800381c1  mov     r9d, edi
0x1800381c4  mov     r8, r14
0x1800381c7  mov     rcx, [rcx+10h]
0x1800381cb  call    WPP_SF_d
0x1800381d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381d7  test    edi, edi
0x1800381d9  jns     loc_18003841B
0x1800381df  mov     r15, [rbp+47h+pvarSrc]
0x1800381e3  lea     rsi, [r12+30h]
0x1800381e8  cmp     [rsi], r13w
0x1800381ec  jz      short loc_180038234
0x1800381ee  lea     rax, WPP_GLOBAL_Control
0x1800381f5  cmp     rcx, rax
0x1800381f8  jz      short loc_180038218
0x1800381fa  test    byte ptr [rcx+1Ch], 2
0x1800381fe  jz      short loc_180038218
0x180038200  mov     edx, 1Fh
0x180038205  mov     r8, r14
0x180038208  mov     rcx, [rcx+10h]
0x18003820c  call    WPP_SF_
0x180038211  mov     rcx, cs:WPP_GLOBAL_Control
0x180038218  cmp     r15, rsi
0x18003821b  jz      short loc_18003822F
0x18003821d  mov     rdx, rsi; struct tagVARIANT *
0x180038220  mov     rcx, r15; this
0x180038223  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180038228  mov     rcx, cs:WPP_GLOBAL_Control
0x18003822f  mov     edi, 1
0x180038234  xorps   xmm0, xmm0
0x180038237  xor     eax, eax
0x180038239  movups  xmmword ptr [rbp+47h+pvargDest], xmm0
0x18003823d  mov     qword ptr [rbp+47h+pvargDest+10h], rax
0x180038241  mov     word ptr [rbp+47h+pvargDest], r13w
0x180038246  lea     rax, WPP_GLOBAL_Control
0x18003824d  cmp     rcx, rax
0x180038250  jz      short loc_1800382A0
0x180038252  test    byte ptr [rcx+1Ch], 2
0x180038256  jz      short loc_1800382A0
0x180038258  lea     rdx, [rbp+47h+pvargDest]
0x18003825c  test    r15, r15
0x18003825f  cmovnz  rdx, r15; pvarSrc
0x180038263  mov     r9w, 8; vt
0x180038268  xor     r8d, r8d; wFlags
0x18003826b  lea     rcx, [rbp+47h+pvargDest]; pvargDest
0x18003826f  call    cs:__imp_VariantChangeType
0x180038275  test    eax, eax
0x180038277  lea     r9, aUndefined; "<undefined>"
0x18003827e  cmovns  r9, qword ptr [rbp+47h+pvargDest+8]
0x180038283  mov     edx, 20h ; ' '
0x180038288  mov     dword ptr [rsp+0D0h+var_B0], edi
0x18003828c  mov     r8, r14
0x18003828f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038296  mov     rcx, [rcx+10h]
0x18003829a  call    WPP_SF_Sd
0x18003829f  nop
0x1800382a0  lea     rcx, [rbp+47h+pvargDest]; this
0x1800382a4  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800382a9  nop
0x1800382aa  lea     rcx, [rbp+47h+phkResult]
0x1800382ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800382b3  nop
0x1800382b4  lea     rcx, [rbp+47h+arg_20]; this
0x1800382b8  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x1800382bd  nop
0x1800382be  test    ebx, ebx
0x1800382c0  jz      short loc_1800382F3
0x1800382c2  call    cs:__imp_CoRevertToSelf
0x1800382c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382cf  lea     rax, WPP_GLOBAL_Control
0x1800382d6  cmp     rcx, rax
0x1800382d9  jz      short loc_1800382F3
0x1800382db  test    byte ptr [rcx+1Ch], 2
0x1800382df  jz      short loc_1800382F3
0x1800382e1  mov     edx, 0Bh
0x1800382e6  mov     r8, r14
0x1800382e9  mov     rcx, [rcx+10h]
0x1800382ed  call    WPP_SF_
0x1800382f2  nop
0x1800382f3  jmp     loc_18003816A
0x1800382f8  test    sil, 4
0x1800382fc  jz      loc_18003847F
0x180038302  mov     rdi, [rbp+47h+lpSubKey]
0x180038306  test    rdi, rdi
0x180038309  jnz     short loc_18003835F
0x18003830b  lea     rdi, WPP_GLOBAL_Control
0x180038312  cmp     rcx, rdi
0x180038315  jz      short loc_18003832E
0x180038317  test    [rcx+1Ch], al
0x18003831a  jz      short loc_18003832E
0x18003831c  mov     edx, 1Bh
0x180038321  mov     r8, r14
0x180038324  mov     rcx, [rcx+10h]
0x180038328  call    WPP_SF_
0x18003832d  nop
0x18003832e  lea     rcx, [rbp+47h+phkResult]
0x180038332  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038337  nop
0x180038338  lea     rcx, [rbp+47h+arg_20]; this
0x18003833c  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180038341  nop
0x180038342  test    ebx, ebx
0x180038344  jz      loc_1800384E7
0x18003834a  call    cs:__imp_CoRevertToSelf
0x180038350  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
