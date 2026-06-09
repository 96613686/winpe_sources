# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x18000cc80`
- end: `0x18000d44f`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `1999`
- prototype: `int __high(enum UST_COMPONENT_ID, const struct USERSTATE_SETTING_DESCRIPTOR *, struct ATL::CComVariant *, void *, enum USERSTATE_SETTING_SOURCES, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cb80`

## callees

- `0x18000c9a0`
- `0x18000cc80`
- `0x18001e560`
- `0x18001f060`
- `0x18002538c`
- `0x180027cb0`
- `0x180035d5c`
- `0x18004edd0`
- `0x18004f0e0`
- `0x18004f108`
- `0x18004f1ac`
- `0x18004f278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d126`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d126`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cdec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cdec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d177`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000d074`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000d074`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d420`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d3c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d420`
- `OLEAUT32!__imp_VariantClear` at `0x18000ccda`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce74`
- `OLEAUT32!__imp_VariantClear` at `0x18000ccda`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce74`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000cf9d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d01e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000cf9d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d01e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ceff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d0e9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d1a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d2a5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d323`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ceff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d0e9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d1a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d2a5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d323`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetUserStateSettingPriv(unsigned int a1, __int64 a2, struct ATL::CComVariant *a3, void *a4, ...)
{
  void *v4; // r14
  const wchar_t *v8; // r12
  int v9; // esi
  int *v10; // rdx
  __int64 v11; // r8
  int v12; // ebx
  char v13; // di
  int v14; // eax
  unsigned int v15; // r14d
  _QWORD *v16; // r10
  HKEY v17; // rcx
  const struct tagVARIANT *v18; // r13
  _QWORD *v19; // rcx
  unsigned int StoredValue; // eax
  __int64 v22; // r8
  __int64 v23; // rdx
  LPCWSTR v24; // rbx
  VARIANTARG *p_pvarg; // rdx
  HRESULT v26; // eax
  int v27; // edx
  int v28; // r8d
  const wchar_t *bstrVal; // rcx
  VARIANTARG *v30; // rdx
  int v31; // edx
  int v32; // r8d
  LSTATUS v33; // eax
  __int64 v34; // r8
  LSTATUS v35; // eax
  __int64 v36; // r8
  unsigned int v37; // esi
  int v38; // [rsp+50h] [rbp-39h] BYREF
  int v39; // [rsp+54h] [rbp-35h]
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  __int64 v41; // [rsp+60h] [rbp-29h]
  __int64 v42; // [rsp+68h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF
  __int64 v45; // [rsp+100h] [rbp+77h] BYREF
  va_list va; // [rsp+100h] [rbp+77h]
  LPCWSTR lpSubKey; // [rsp+108h] [rbp+7Fh]
  va_list va1; // [rsp+110h] [rbp+87h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v45 = va_arg(va1, _QWORD);
  lpSubKey = va_arg(va1, LPCWSTR);
  v4 = a4;
  memset(&pvarg, 0, sizeof(pvarg));
  v8 = L"<undefined>";
  v9 = v45;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v24 = L"NULL";
    if ( lpSubKey )
      v24 = lpSubKey;
    p_pvarg = &pvarg;
    if ( a3 )
      p_pvarg = (VARIANTARG *)a3;
    v26 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v26 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_dddSqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      v28,
      a1,
      *(_DWORD *)a2,
      *(_WORD *)a3,
      (__int64)bstrVal,
      (char)v4,
      v9,
      (__int64)v24);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
  }
  VariantClear(&pvarg);
  if ( (v9 & 0x30) == 0 )
    v9 |= *(_DWORD *)(a2 + 8) & 0x30;
  if ( (v9 & 0x30) == 0x30 )
  {
    if ( (unsigned int)GetSettingAuthority(a1) == 1 )
      LOBYTE(v9) = v9 & 0xEF;
    else
      LOBYTE(v9) = v9 & 0xDF;
  }
  if ( (v9 & 0x20) != 0 )
  {
    v41 = 40;
    v42 = 32;
  }
  else
  {
    if ( (v9 & 0x10) == 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return 2147942487LL;
      v23 = 22;
      goto LABEL_126;
    }
    v41 = 24;
    v42 = 16;
  }
  if ( (v9 & 7) == 0 )
    v9 = *(_DWORD *)(a2 + 8) & 7;
  v12 = 0;
  v38 = 0;
  v13 = 0;
  LOBYTE(v45) = 0;
  v14 = v9 & 1;
  v39 = v14;
  if ( (v9 & 1) == 0 )
  {
    v15 = 0;
    if ( (v9 & 4) == 0 )
    {
      v16 = WPP_GLOBAL_Control;
      goto LABEL_12;
    }
    v4 = a4;
  }
  if ( v4 )
  {
    v15 = UstCommon::CImpersonator::Impersonate((UstCommon::CImpersonator *)va, v4);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v11, v15);
      v16 = WPP_GLOBAL_Control;
    }
    v13 = v45;
  }
  else
  {
    v15 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v38, v10);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v12 = v38;
    }
    else
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v11, v15);
      v12 = v38;
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( (v15 & 0x80000000) != 0 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
      WPP_SF_D(v16[2], 25, v11, v15);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
    if ( !v12 )
      return v15;
LABEL_99:
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    return v15;
  }
  v14 = v39;
LABEL_12:
  v17 = 0;
  hKey = 0;
  if ( (v9 & 2) != 0 )
  {
    hKey = HKEY_LOCAL_MACHINE;
    goto LABEL_14;
  }
  if ( v14 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v33 = RegOpenCurrentUser(0x20019u, &hKey);
    v15 = v33;
    if ( v33 > 0 )
      v15 = (unsigned __int16)v33 | 0x80070000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v34, v15);
      v16 = WPP_GLOBAL_Control;
    }
LABEL_14:
    if ( (v15 & 0x80000000) != 0 )
      goto LABEL_15;
    goto LABEL_28;
  }
  if ( (v9 & 4) == 0 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
    {
      WPP_SF_D(v16[2], 29, v11, v15);
      v17 = hKey;
      v16 = WPP_GLOBAL_Control;
    }
    if ( v17 )
    {
      RegCloseKey(v17);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v13 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
        WPP_SF_(v16[2], 12, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
      RevertToSelf();
    }
    if ( !v12 )
      return 2147942487LL;
    goto LABEL_43;
  }
  if ( !lpSubKey )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
    {
      WPP_SF_(v16[2], 27, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
      v17 = hKey;
    }
    if ( v17 )
      RegCloseKey(v17);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
    if ( !v12 )
      return 2147942487LL;
LABEL_43:
    CoRevertToSelf();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 2147942487LL;
    v23 = 11;
LABEL_126:
    WPP_SF_(v19[2], v23, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    return 2147942487LL;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v35 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hKey);
  v37 = v35;
  if ( v35 > 0 )
    v37 = (unsigned __int16)v35 | 0x80070000;
  if ( (v37 & 0x80000000) == 0 )
  {
LABEL_28:
    StoredValue = GetStoredValue(
                    hKey,
                    *(const unsigned __int16 **)(v42 + a2),
                    *(const unsigned __int16 **)(v41 + a2),
                    *(_WORD *)(a2 + 4),
                    a3);
    v15 = StoredValue;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v22, StoredValue);
      v16 = WPP_GLOBAL_Control;
    }
    if ( (v15 & 0x80000000) == 0 )
    {
LABEL_30:
      memset(&pvarg, 0, sizeof(pvarg));
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
      {
        v30 = &pvarg;
        if ( a3 )
          v30 = (VARIANTARG *)a3;
        if ( VariantChangeType(&pvarg, v30, 0, 8u) >= 0 )
          LODWORD(v8) = pvarg.lVal;
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, (_DWORD)v8, v15);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
      }
      VariantClear(&pvarg);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
        RevertToSelf();
      }
      if ( !v12 )
        return v15;
      goto LABEL_99;
    }
LABEL_15:
    v18 = (const struct tagVARIANT *)(a2 + 48);
    if ( v18->vt )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
      {
        WPP_SF_(v16[2], 31, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      if ( a3 != (struct ATL::CComVariant *)v18 )
      {
        ATL::CComVariant::InternalCopy(a3, v18);
        v16 = WPP_GLOBAL_Control;
      }
      v15 = 1;
    }
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v36, v37);
  if ( hKey )
    RegCloseKey(hKey);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)va);
  if ( v12 )
  {
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  }
  return v37;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp-8+arg_18], r9
0x18000cc85  push    rbp
0x18000cc86  push    rbx
0x18000cc87  push    rsi
0x18000cc88  push    rdi
0x18000cc89  push    r12
0x18000cc8b  push    r13
0x18000cc8d  push    r14
0x18000cc8f  push    r15
0x18000cc91  lea     rbp, [rsp-0Fh]
0x18000cc96  sub     rsp, 98h
0x18000cc9d  mov     r14, r9
0x18000cca0  mov     r15, r8
0x18000cca3  mov     r13, rdx
0x18000cca6  mov     edi, ecx
0x18000cca8  xorps   xmm0, xmm0
0x18000ccab  xor     eax, eax
0x18000ccad  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18000ccb1  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18000ccb5  lea     rbx, WPP_GLOBAL_Control
0x18000ccbc  lea     r12, aUndefined; "<undefined>"
0x18000ccc3  mov     esi, dword ptr [rbp+47h+arg_20]
0x18000ccc6  mov     rax, cs:WPP_GLOBAL_Control
0x18000cccd  cmp     rax, rbx
0x18000ccd0  jnz     loc_18000D1C5
0x18000ccd6  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000ccda  call    cs:__imp_VariantClear
0x18000cce0  test    sil, 30h
0x18000cce4  jz      loc_18000D1D4
0x18000ccea  mov     eax, esi
0x18000ccec  and     eax, 30h
0x18000ccef  cmp     al, 30h ; '0'
0x18000ccf1  jz      loc_18000CE8D
0x18000ccf7  test    sil, 20h
0x18000ccfb  jz      loc_18000CDCB
0x18000cd01  mov     [rbp+47h+var_70], 28h ; '('
0x18000cd09  mov     [rbp+47h+var_68], 20h ; ' '
0x18000cd11  test    sil, 7
0x18000cd15  jz      loc_18000D1E2
0x18000cd1b  xor     ebx, ebx
0x18000cd1d  mov     [rbp+47h+var_80], ebx
0x18000cd20  xor     dil, dil
0x18000cd23  mov     byte ptr [rbp+47h+arg_20], dil
0x18000cd27  mov     eax, esi
0x18000cd29  and     eax, 1
0x18000cd2c  mov     [rbp+47h+var_7C], eax
0x18000cd2f  jnz     loc_18000CF29
0x18000cd35  xor     r14d, r14d
0x18000cd38  test    sil, 4
0x18000cd3c  jnz     loc_18000D1EE
0x18000cd42  mov     r10, cs:WPP_GLOBAL_Control
0x18000cd49  xor     ecx, ecx; hKey
0x18000cd4b  mov     [rbp+47h+hKey], rcx
0x18000cd4f  test    sil, 2
0x18000cd53  jz      loc_18000CEBA
0x18000cd59  mov     [rbp+47h+hKey], 0FFFFFFFF80000002h
0x18000cd61  lea     rsi, WPP_GLOBAL_Control
0x18000cd68  test    r14d, r14d
0x18000cd6b  jns     loc_18000CE1B
0x18000cd71  add     r13, 30h ; '0'
0x18000cd75  cmp     word ptr [r13+0], 0
0x18000cd7b  jz      loc_18000CE5A
0x18000cd81  cmp     r10, rsi
0x18000cd84  jz      short loc_18000CDA9
0x18000cd86  test    byte ptr [r10+1Ch], 2
0x18000cd8b  jz      short loc_18000CDA9
0x18000cd8d  mov     edx, 1Fh
0x18000cd92  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000cd99  mov     rcx, [r10+10h]
0x18000cd9d  call    WPP_SF_
0x18000cda2  mov     r10, cs:WPP_GLOBAL_Control
0x18000cda9  cmp     r15, r13
0x18000cdac  jz      short loc_18000CDC0
0x18000cdae  mov     rdx, r13; struct tagVARIANT *
0x18000cdb1  mov     rcx, r15; this
0x18000cdb4  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18000cdb9  mov     r10, cs:WPP_GLOBAL_Control
0x18000cdc0  mov     r14d, 1
0x18000cdc6  jmp     loc_18000CE5A
0x18000cdcb  test    sil, 10h
0x18000cdcf  jnz     loc_18000CEA5
0x18000cdd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cddc  cmp     rcx, rbx
0x18000cddf  jnz     loc_18000D42B
0x18000cde5  mov     eax, 80070057h
0x18000cdea  jmp     short loc_18000CE07
0x18000cdec  call    cs:__imp_RegCloseKey
0x18000cdf2  nop
0x18000cdf3  test    dil, dil
0x18000cdf6  jnz     loc_18000D3A1
0x18000cdfc  test    ebx, ebx
0x18000cdfe  jnz     loc_18000D2A5
0x18000ce04  mov     eax, r14d
0x18000ce07  add     rsp, 98h
0x18000ce0e  pop     r15
0x18000ce10  pop     r14
0x18000ce12  pop     r13
0x18000ce14  pop     r12
0x18000ce16  pop     rdi
0x18000ce17  pop     rsi
0x18000ce18  pop     rbx
0x18000ce19  pop     rbp
0x18000ce1a  retn
0x18000ce1b  mov     [rsp+0D0h+phkResult], r15; struct ATL::CComVariant *
0x18000ce20  movzx   r9d, word ptr [r13+4]; unsigned __int16
0x18000ce25  mov     r8, [rbp+47h+var_70]
0x18000ce29  mov     r8, [r8+r13]; unsigned __int16 *
0x18000ce2d  mov     rdx, [rbp+47h+var_68]
0x18000ce31  mov     rdx, [rdx+r13]; unsigned __int16 *
0x18000ce35  mov     rcx, [rbp+47h+hKey]; HKEY
0x18000ce39  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18000ce3e  mov     r14d, eax
0x18000ce41  mov     r10, cs:WPP_GLOBAL_Control
0x18000ce48  cmp     r10, rsi
0x18000ce4b  jnz     loc_18000D369
0x18000ce51  test    r14d, r14d
0x18000ce54  js      loc_18000CD71
0x18000ce5a  xorps   xmm0, xmm0
0x18000ce5d  xor     eax, eax
0x18000ce5f  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18000ce63  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18000ce67  cmp     r10, rsi
0x18000ce6a  jnz     loc_18000D391
0x18000ce70  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000ce74  call    cs:__imp_VariantClear
0x18000ce7a  nop
0x18000ce7b  mov     rcx, [rbp+47h+hKey]; hKey
0x18000ce7f  test    rcx, rcx
0x18000ce82  jz      loc_18000CDF3
0x18000ce88  jmp     loc_18000CDEC
0x18000ce8d  mov     ecx, edi
0x18000ce8f  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x18000ce94  cmp     eax, 1
0x18000ce97  jz      loc_18000CF6D
0x18000ce9d  and     esi, 0FFFFFFDFh
0x18000cea0  jmp     loc_18000CCF7
0x18000cea5  mov     [rbp+47h+var_70], 18h
0x18000cead  mov     [rbp+47h+var_68], 10h
0x18000ceb5  jmp     loc_18000CD11
0x18000ceba  test    eax, eax
0x18000cebc  jnz     loc_18000D060
0x18000cec2  test    sil, 4
0x18000cec6  jnz     loc_18000D2DF
0x18000cecc  lea     rsi, WPP_GLOBAL_Control
0x18000ced3  cmp     r10, rsi
0x18000ced6  jnz     loc_18000D3D3
0x18000cedc  test    rcx, rcx
0x18000cedf  jz      short loc_18000CEEE
0x18000cee1  call    cs:__imp_RegCloseKey
0x18000cee7  mov     r10, cs:WPP_GLOBAL_Control
0x18000ceee  test    dil, dil
0x18000cef1  jnz     loc_18000D3FF
0x18000cef7  test    ebx, ebx
0x18000cef9  jz      loc_18000CDE5
0x18000ceff  call    cs:__imp_CoRevertToSelf
0x18000cf05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf0c  cmp     rcx, rsi
0x18000cf0f  jz      loc_18000CDE5
0x18000cf15  test    byte ptr [rcx+1Ch], 2
0x18000cf19  jz      loc_18000CDE5
0x18000cf1f  mov     edx, 0Bh
0x18000cf24  jmp     loc_18000D43A
0x18000cf29  test    r14, r14
0x18000cf2c  jz      loc_18000D1F7
0x18000cf32  mov     rdx, r14; void *
0x18000cf35  lea     rcx, [rbp+47h+arg_20]; this
0x18000cf39  call    ?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z; UstCommon::CImpersonator::Impersonate(void *)
0x18000cf3e  mov     r14d, eax
0x18000cf41  mov     r10, cs:WPP_GLOBAL_Control
0x18000cf48  lea     rax, WPP_GLOBAL_Control
0x18000cf4f  cmp     r10, rax
0x18000cf52  jnz     loc_18000D24C
0x18000cf58  movzx   edi, byte ptr [rbp+47h+arg_20]
0x18000cf5c  test    r14d, r14d
0x18000cf5f  js      loc_18000D27B
0x18000cf65  mov     eax, [rbp+47h+var_7C]
0x18000cf68  jmp     loc_18000CD49
0x18000cf6d  and     esi, 0FFFFFFEFh
0x18000cf70  jmp     loc_18000CCF7
0x18000cf75  lea     rbx, aNull; "NULL"
0x18000cf7c  cmp     [rbp+47h+lpSubKey], 0
0x18000cf81  cmovnz  rbx, [rbp+47h+lpSubKey]
0x18000cf86  lea     rdx, [rbp+47h+pvarg]
0x18000cf8a  test    r15, r15
0x18000cf8d  cmovnz  rdx, r15; pvarSrc
0x18000cf91  mov     r9w, 8; vt
0x18000cf96  xor     r8d, r8d; wFlags
0x18000cf99  lea     rcx, [rbp+47h+pvarg]; pvargDest
0x18000cf9d  call    cs:__imp_VariantChangeType
0x18000cfa3  mov     rcx, r12
0x18000cfa6  test    eax, eax
0x18000cfa8  cmovns  rcx, qword ptr [rbp+47h+pvarg+8]
0x18000cfad  movzx   eax, word ptr [r15]
0x18000cfb1  mov     [rsp+0D0h+var_88], rbx
0x18000cfb6  mov     [rsp+0D0h+var_90], esi
0x18000cfba  mov     [rsp+0D0h+var_98], r14
0x18000cfbf  mov     [rsp+0D0h+var_A0], rcx
0x18000cfc4  mov     [rsp+0D0h+var_A8], eax
0x18000cfc8  mov     eax, [r13+0]
0x18000cfcc  mov     dword ptr [rsp+0D0h+phkResult], eax
0x18000cfd0  mov     r9d, edi
0x18000cfd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfda  mov     rcx, [rcx+10h]
0x18000cfde  call    WPP_SF_dddSqDS
0x18000cfe3  mov     eax, 0FFFh
0x18000cfe8  lea     rbx, WPP_GLOBAL_Control
0x18000cfef  cmp     word ptr [rbp+47h+pvarg], ax
0x18000cff3  jnz     loc_18000CCD6
0x18000cff9  mov     eax, 8
0x18000cffe  mov     word ptr [rbp+47h+pvarg], ax
0x18000d002  jmp     loc_18000CCD6
0x18000d007  lea     rdx, [rbp+47h+pvarg]
0x18000d00b  test    r15, r15
0x18000d00e  cmovnz  rdx, r15; pvarSrc
0x18000d012  mov     r9w, 8; vt
0x18000d017  xor     r8d, r8d; wFlags
0x18000d01a  lea     rcx, [rbp+47h+pvarg]; pvargDest
0x18000d01e  call    cs:__imp_VariantChangeType
0x18000d024  test    eax, eax
0x18000d026  cmovns  r12, qword ptr [rbp+47h+pvarg+8]
0x18000d02b  mov     dword ptr [rsp+0D0h+phkResult], r14d
0x18000d030  mov     r9, r12
0x18000d033  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d03a  mov     rcx, [rcx+10h]
0x18000d03e  call    WPP_SF_SD
0x18000d043  mov     eax, 0FFFh
0x18000d048  cmp     word ptr [rbp+47h+pvarg], ax
0x18000d04c  jnz     loc_18000CE70
0x18000d052  mov     eax, 8
0x18000d057  mov     word ptr [rbp+47h+pvarg], ax
0x18000d05b  jmp     loc_18000CE70
0x18000d060  xor     edx, edx
0x18000d062  lea     rcx, [rbp+47h+hKey]
0x18000d066  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000d06b  lea     rdx, [rbp+47h+hKey]; phkResult
0x18000d06f  mov     ecx, 20019h; samDesired
0x18000d074  call    cs:__imp_RegOpenCurrentUser
0x18000d07a  mov     r14d, eax
0x18000d07d  test    eax, eax
0x18000d07f  jle     short loc_18000D08C
0x18000d081  movzx   r14d, ax
0x18000d085  or      r14d, 80070000h
0x18000d08c  mov     r10, cs:WPP_GLOBAL_Control
0x18000d093  lea     rsi, WPP_GLOBAL_Control
0x18000d09a  cmp     r10, rsi
0x18000d09d  jz      loc_18000CD68
0x18000d0a3  test    byte ptr [r10+1Ch], 2
0x18000d0a8  jz      loc_18000CD68
0x18000d0ae  mov     edx, 1Ah
0x18000d0b3  mov     r9d, r14d
0x18000d0b6  mov     rcx, [r10+10h]
0x18000d0ba  call    WPP_SF_D
0x18000d0bf  mov     r10, cs:WPP_GLOBAL_Control
0x18000d0c6  jmp     loc_18000CD68
0x18000d0cb  test    rcx, rcx
0x18000d0ce  jz      short loc_18000D0D7
0x18000d0d0  call    cs:__imp_RegCloseKey
0x18000d0d6  nop
0x18000d0d7  lea     rcx, [rbp+47h+arg_20]; this
0x18000d0db  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000d0e0  nop
0x18000d0e1  test    ebx, ebx
0x18000d0e3  jz      loc_18000CDE5
0x18000d0e9  call    cs:__imp_CoRevertToSelf
0x18000d0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0f6  cmp     rcx, rdi
0x18000d0f9  jmp     loc_18000CF0F
0x18000d0fe  xor     edx, edx
0x18000d100  lea     rcx, [rbp+47h+hKey]
0x18000d104  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000d109  lea     rax, [rbp+47h+hKey]
0x18000d10d  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000d112  mov     r9d, 20019h; samDesired
0x18000d118  xor     r8d, r8d; ulOptions
0x18000d11b  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18000d11f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000d126  call    cs:__imp_RegOpenKeyExW
0x18000d12c  mov     esi, eax
0x18000d12e  test    eax, eax
0x18000d130  jle     short loc_18000D13B
0x18000d132  movzx   esi, ax
0x18000d135  or      esi, 80070000h
0x18000d13b  test    esi, esi
0x18000d13d  jns     loc_18000D35D
0x18000d143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d14a  lea     rdi, WPP_GLOBAL_Control
0x18000d151  cmp     rcx, rdi
0x18000d154  jz      short loc_18000D16E
0x18000d156  test    byte ptr [rcx+1Ch], 2
0x18000d15a  jz      short loc_18000D16E
0x18000d15c  mov     edx, 1Ch
0x18000d161  mov     r9d, esi
0x18000d164  mov     rcx, [rcx+10h]
0x18000d168  call    WPP_SF_D
0x18000d16d  nop
0x18000d16e  mov     rcx, [rbp+47h+hKey]; hKey
0x18000d172  test    rcx, rcx
0x18000d175  jz      short loc_18000D17E
0x18000d177  call    cs:__imp_RegCloseKey
0x18000d17d  nop
  ... truncated ...
```
