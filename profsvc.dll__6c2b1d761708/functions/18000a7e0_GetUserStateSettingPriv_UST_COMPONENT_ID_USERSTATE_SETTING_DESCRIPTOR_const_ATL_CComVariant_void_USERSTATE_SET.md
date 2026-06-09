# GetUserStateSettingPriv(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x18000a7e0`
- end: `0x18000afa5`
- name: `?GetUserStateSettingPriv@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `1989`
- prototype: `__int64 __fastcall(unsigned int, const struct tagVARIANT *, struct tagVARIANT *, void *, int, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a6e0`

## callees

- `0x18000a4f0`
- `0x18000a7e0`
- `0x1800130d0`
- `0x180022490`
- `0x180027b0c`
- `0x180029a40`
- `0x1800362dc`
- `0x180051b34`
- `0x1800520e0`
- `0x18005242c`
- `0x18005245c`
- `0x180052510`
- `0x1800525e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ac8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ac8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a954`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a954`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acda`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000abcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000abcd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000af12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000af70`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000af12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000af70`
- `OLEAUT32!__imp_VariantClear` at `0x18000a83a`
- `OLEAUT32!__imp_VariantClear` at `0x18000a9e7`
- `OLEAUT32!__imp_VariantClear` at `0x18000a83a`
- `OLEAUT32!__imp_VariantClear` at `0x18000a9e7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000aa77`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ac47`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ad12`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000adf6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ae73`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000aa77`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ac47`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ad12`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000adf6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ae73`

## pseudocode

```c
__int64 __fastcall GetUserStateSettingPriv(
        unsigned int a1,
        const struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        void *a4,
        int a5,
        LPCWSTR lpSubKey)
{
  const wchar_t *v10; // r15
  int v11; // esi
  int *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  char v16; // di
  int v17; // eax
  unsigned int v18; // r14d
  _QWORD *v19; // r10
  HKEY v20; // rcx
  const struct tagVARIANT *v21; // rsi
  const struct tagVARIANT *v22; // rsi
  _QWORD *v23; // rcx
  unsigned int StoredValue; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int v29; // eax
  LPCWSTR v30; // rbx
  int v31; // eax
  int v32; // edx
  int v33; // r8d
  const wchar_t *bstrVal; // rcx
  int v35; // edx
  int v36; // r8d
  LSTATUS v37; // eax
  __int64 v38; // r8
  LSTATUS v39; // eax
  __int64 v40; // r8
  unsigned int v41; // esi
  unsigned int v42; // eax
  __int64 v43; // r9
  __int64 v44; // r9
  int v45; // [rsp+50h] [rbp-39h] BYREF
  int v46; // [rsp+54h] [rbp-35h]
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  __int64 v48; // [rsp+60h] [rbp-29h]
  __int64 v49; // [rsp+68h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v10 = L"<undefined>";
  v11 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v30 = L"NULL";
    if ( lpSubKey )
      v30 = lpSubKey;
    v31 = ATL::CComVariant::ChangeType((ATL::CComVariant *)&pvarg, (unsigned __int16)a2, a3);
    bstrVal = L"<undefined>";
    if ( v31 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_dddSqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      v33,
      a1,
      *(_DWORD *)&a2->vt,
      a3->vt,
      (__int64)bstrVal,
      (char)a4,
      v11,
      (__int64)v30);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
  }
  VariantClear(&pvarg);
  if ( (v11 & 0x30) == 0 )
    v11 |= a2->lVal & 0x30;
  if ( (v11 & 0x30) == 0x30 )
  {
    if ( (unsigned int)GetSettingAuthority(a1) == 1 )
      LOBYTE(v11) = v11 & 0xEF;
    else
      LOBYTE(v11) = v11 & 0xDF;
  }
  if ( (v11 & 0x20) != 0 )
  {
    v48 = 40;
    v49 = 32;
  }
  else
  {
    if ( (v11 & 0x10) == 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return 2147942487LL;
      v28 = 22;
      goto LABEL_121;
    }
    v48 = 24;
    v49 = 16;
  }
  if ( (v11 & 7) == 0 )
    v11 = a2->lVal & 7;
  v15 = 0;
  v45 = 0;
  v16 = 0;
  LOBYTE(a5) = 0;
  v17 = v11 & 1;
  v46 = v17;
  if ( (v11 & 1) != 0 || (v18 = 0, (v11 & 4) != 0) )
  {
    if ( a4 )
    {
      v29 = UstCommon::CImpersonator::Impersonate((UstCommon::CImpersonator *)&a5, a4);
      v18 = v29;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v13, v29);
        v19 = WPP_GLOBAL_Control;
      }
      v16 = a5;
    }
    else
    {
      v42 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v45, v12);
      v18 = v42;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v15 = v45;
      }
      else
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v13, v42);
        v15 = v45;
        v19 = WPP_GLOBAL_Control;
      }
    }
    if ( (v18 & 0x80000000) != 0 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
        WPP_SF_D(v19[2], 25, v13, v18);
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
      if ( !v15 )
        return v18;
LABEL_95:
      CoRevertToSelf();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v43);
      return v18;
    }
    v17 = v46;
  }
  else
  {
    v19 = WPP_GLOBAL_Control;
  }
  v20 = 0;
  hKey = 0;
  if ( (v11 & 2) != 0 )
  {
    hKey = HKEY_LOCAL_MACHINE;
    goto LABEL_14;
  }
  if ( v17 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v37 = RegOpenCurrentUser(0x20019u, &hKey);
    v18 = v37;
    if ( v37 > 0 )
      v18 = (unsigned __int16)v37 | 0x80070000;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v38, v18);
      v19 = WPP_GLOBAL_Control;
    }
LABEL_14:
    if ( (v18 & 0x80000000) != 0 )
    {
      v21 = a2;
      goto LABEL_16;
    }
LABEL_29:
    v21 = a2;
    StoredValue = GetStoredValue(
                    hKey,
                    *(const unsigned __int16 **)((char *)&a2->vt + v49),
                    *(WCHAR **)((char *)&a2->vt + v48),
                    a2->wReserved2,
                    a3);
    v18 = StoredValue;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v26, StoredValue);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (v18 & 0x80000000) == 0 )
    {
LABEL_31:
      memset(&pvarg, 0, sizeof(pvarg));
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
      {
        if ( (int)ATL::CComVariant::ChangeType((ATL::CComVariant *)&pvarg, (unsigned __int16)v12, a3) >= 0 )
          LODWORD(v10) = pvarg.lVal;
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, (_DWORD)v10, v18);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
      }
      VariantClear(&pvarg);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v27);
        RevertToSelf();
      }
      if ( !v15 )
        return v18;
      goto LABEL_95;
    }
LABEL_16:
    v22 = v21 + 2;
    if ( v22->vt )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
      {
        WPP_SF_(v19[2], 31, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v14);
        v19 = WPP_GLOBAL_Control;
      }
      if ( a3 != v22 )
      {
        ATL::CComVariant::InternalCopy((ATL::CComVariant *)a3, v22);
        v19 = WPP_GLOBAL_Control;
      }
      v18 = 1;
    }
    goto LABEL_31;
  }
  if ( (v11 & 4) == 0 )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
    {
      WPP_SF_D(v19[2], 29, v13, v18);
      v20 = hKey;
      v19 = WPP_GLOBAL_Control;
    }
    if ( v20 )
    {
      RegCloseKey(v20);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v16 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
        WPP_SF_(v19[2], 12, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v14);
      RevertToSelf();
    }
    if ( !v15 )
      return 2147942487LL;
    goto LABEL_44;
  }
  if ( !lpSubKey )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
    {
      WPP_SF_(v19[2], 27, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v14);
      v20 = hKey;
    }
    if ( v20 )
      RegCloseKey(v20);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v15 )
      return 2147942487LL;
LABEL_44:
    CoRevertToSelf();
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 2147942487LL;
    v28 = 11;
LABEL_121:
    WPP_SF_(v23[2], v28, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v14);
    return 2147942487LL;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v39 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hKey);
  v41 = v39;
  if ( v39 > 0 )
    v41 = (unsigned __int16)v39 | 0x80070000;
  if ( (v41 & 0x80000000) == 0 )
    goto LABEL_29;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v40, v41);
  if ( hKey )
    RegCloseKey(hKey);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
  if ( v15 )
  {
    CoRevertToSelf();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v44);
  }
  return v41;
}

```

## disassembly

```asm
0x18000a7e0  mov     [rsp-8+arg_8], rdx
0x18000a7e5  push    rbp
0x18000a7e6  push    rbx
0x18000a7e7  push    rsi
0x18000a7e8  push    rdi
0x18000a7e9  push    r12
0x18000a7eb  push    r13
0x18000a7ed  push    r14
0x18000a7ef  push    r15
0x18000a7f1  lea     rbp, [rsp-0Fh]
0x18000a7f6  sub     rsp, 98h
0x18000a7fd  mov     r13, r9
0x18000a800  mov     r12, r8
0x18000a803  mov     r14, rdx
0x18000a806  mov     edi, ecx
0x18000a808  xorps   xmm0, xmm0
0x18000a80b  xor     eax, eax
0x18000a80d  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18000a811  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18000a815  lea     rbx, WPP_GLOBAL_Control
0x18000a81c  lea     r15, aUndefined; "<undefined>"
0x18000a823  mov     esi, [rbp+47h+arg_20]
0x18000a826  mov     rax, cs:WPP_GLOBAL_Control
0x18000a82d  cmp     rax, rbx
0x18000a830  jnz     loc_18000AD2D
0x18000a836  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000a83a  call    cs:__imp_VariantClear
0x18000a841  nop     dword ptr [rax+rax+00h]
0x18000a846  test    sil, 30h
0x18000a84a  jz      loc_18000AD3C
0x18000a850  mov     eax, esi
0x18000a852  and     eax, 30h
0x18000a855  cmp     al, 30h ; '0'
0x18000a857  jz      loc_18000AA06
0x18000a85d  test    sil, 20h
0x18000a861  jz      loc_18000A933
0x18000a867  mov     [rbp+47h+var_70], 28h ; '('
0x18000a86f  mov     [rbp+47h+var_68], 20h ; ' '
0x18000a877  test    sil, 7
0x18000a87b  jz      loc_18000AD4A
0x18000a881  xor     ebx, ebx
0x18000a883  mov     [rbp+47h+var_80], ebx
0x18000a886  xor     dil, dil
0x18000a889  mov     byte ptr [rbp+47h+arg_20], dil
0x18000a88d  mov     eax, esi
0x18000a88f  and     eax, 1
0x18000a892  mov     [rbp+47h+var_7C], eax
0x18000a895  jnz     loc_18000AAA7
0x18000a89b  xor     r14d, r14d
0x18000a89e  test    sil, 4
0x18000a8a2  jnz     loc_18000AAA7
0x18000a8a8  mov     r10, cs:WPP_GLOBAL_Control
0x18000a8af  lea     r13, WPP_GLOBAL_Control
0x18000a8b6  xor     ecx, ecx; hKey
0x18000a8b8  mov     [rbp+47h+hKey], rcx
0x18000a8bc  test    sil, 2
0x18000a8c0  jz      loc_18000AA33
0x18000a8c6  mov     [rbp+47h+hKey], 0FFFFFFFF80000002h
0x18000a8ce  test    r14d, r14d
0x18000a8d1  jns     loc_18000A98A
0x18000a8d7  mov     rsi, [rbp+47h+arg_8]
0x18000a8db  add     rsi, 30h ; '0'
0x18000a8df  cmp     word ptr [rsi], 0
0x18000a8e3  jz      loc_18000A9CD
0x18000a8e9  cmp     r10, r13
0x18000a8ec  jz      short loc_18000A911
0x18000a8ee  test    byte ptr [r10+1Ch], 2
0x18000a8f3  jz      short loc_18000A911
0x18000a8f5  mov     edx, 1Fh
0x18000a8fa  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000a901  mov     rcx, [r10+10h]
0x18000a905  call    WPP_SF_
0x18000a90a  mov     r10, cs:WPP_GLOBAL_Control
0x18000a911  cmp     r12, rsi
0x18000a914  jz      short loc_18000A928
0x18000a916  mov     rdx, rsi; struct tagVARIANT *
0x18000a919  mov     rcx, r12; this
0x18000a91c  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18000a921  mov     r10, cs:WPP_GLOBAL_Control
0x18000a928  mov     r14d, 1
0x18000a92e  jmp     loc_18000A9CD
0x18000a933  test    sil, 10h
0x18000a937  jnz     loc_18000AA1E
0x18000a93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a944  cmp     rcx, rbx
0x18000a947  jnz     loc_18000AF81
0x18000a94d  mov     eax, 80070057h
0x18000a952  jmp     short loc_18000A975
0x18000a954  call    cs:__imp_RegCloseKey
0x18000a95b  nop     dword ptr [rax+rax+00h]
0x18000a960  nop
0x18000a961  test    dil, dil
0x18000a964  jnz     loc_18000AEEB
0x18000a96a  test    ebx, ebx
0x18000a96c  jnz     loc_18000ADF6
0x18000a972  mov     eax, r14d
0x18000a975  add     rsp, 98h
0x18000a97c  pop     r15
0x18000a97e  pop     r14
0x18000a980  pop     r13
0x18000a982  pop     r12
0x18000a984  pop     rdi
0x18000a985  pop     rsi
0x18000a986  pop     rbx
0x18000a987  pop     rbp
0x18000a988  retn
0x18000a98a  mov     [rsp+0D0h+phkResult], r12; struct ATL::CComVariant *
0x18000a98f  mov     rsi, [rbp+47h+arg_8]
0x18000a993  movzx   r9d, word ptr [rsi+4]; unsigned __int16
0x18000a998  mov     r8, [rbp+47h+var_70]
0x18000a99c  mov     r8, [r8+rsi]; unsigned __int16 *
0x18000a9a0  mov     rdx, [rbp+47h+var_68]
0x18000a9a4  mov     rdx, [rdx+rsi]; unsigned __int16 *
0x18000a9a8  mov     rcx, [rbp+47h+hKey]; HKEY
0x18000a9ac  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18000a9b1  mov     r14d, eax
0x18000a9b4  mov     r10, cs:WPP_GLOBAL_Control
0x18000a9bb  cmp     r10, r13
0x18000a9be  jnz     loc_18000AEB3
0x18000a9c4  test    r14d, r14d
0x18000a9c7  js      loc_18000A8DB
0x18000a9cd  xorps   xmm0, xmm0
0x18000a9d0  xor     eax, eax
0x18000a9d2  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18000a9d6  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18000a9da  cmp     r10, r13
0x18000a9dd  jnz     loc_18000AEDB
0x18000a9e3  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000a9e7  call    cs:__imp_VariantClear
0x18000a9ee  nop     dword ptr [rax+rax+00h]
0x18000a9f3  nop
0x18000a9f4  mov     rcx, [rbp+47h+hKey]; hKey
0x18000a9f8  test    rcx, rcx
0x18000a9fb  jz      loc_18000A961
0x18000aa01  jmp     loc_18000A954
0x18000aa06  mov     ecx, edi
0x18000aa08  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x18000aa0d  cmp     eax, 1
0x18000aa10  jz      loc_18000AAEB
0x18000aa16  and     esi, 0FFFFFFDFh
0x18000aa19  jmp     loc_18000A85D
0x18000aa1e  mov     [rbp+47h+var_70], 18h
0x18000aa26  mov     [rbp+47h+var_68], 10h
0x18000aa2e  jmp     loc_18000A877
0x18000aa33  test    eax, eax
0x18000aa35  jnz     loc_18000ABB9
0x18000aa3b  test    sil, 4
0x18000aa3f  jnz     loc_18000AE36
0x18000aa45  cmp     r10, r13
0x18000aa48  jnz     loc_18000AF23
0x18000aa4e  test    rcx, rcx
0x18000aa51  jz      short loc_18000AA66
0x18000aa53  call    cs:__imp_RegCloseKey
0x18000aa5a  nop     dword ptr [rax+rax+00h]
0x18000aa5f  mov     r10, cs:WPP_GLOBAL_Control
0x18000aa66  test    dil, dil
0x18000aa69  jnz     loc_18000AF4F
0x18000aa6f  test    ebx, ebx
0x18000aa71  jz      loc_18000A94D
0x18000aa77  call    cs:__imp_CoRevertToSelf
0x18000aa7e  nop     dword ptr [rax+rax+00h]
0x18000aa83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa8a  cmp     rcx, r13
0x18000aa8d  jz      loc_18000A94D
0x18000aa93  test    byte ptr [rcx+1Ch], 2
0x18000aa97  jz      loc_18000A94D
0x18000aa9d  mov     edx, 0Bh
0x18000aaa2  jmp     loc_18000AF90
0x18000aaa7  test    r13, r13
0x18000aaaa  jz      loc_18000AD56
0x18000aab0  mov     rdx, r13; void *
0x18000aab3  lea     rcx, [rbp+47h+arg_20]; this
0x18000aab7  call    ?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z; UstCommon::CImpersonator::Impersonate(void *)
0x18000aabc  mov     r14d, eax
0x18000aabf  mov     r10, cs:WPP_GLOBAL_Control
0x18000aac6  lea     r13, WPP_GLOBAL_Control
0x18000aacd  cmp     r10, r13
0x18000aad0  jnz     loc_18000ADA4
0x18000aad6  movzx   edi, byte ptr [rbp+47h+arg_20]
0x18000aada  test    r14d, r14d
0x18000aadd  js      loc_18000ADCC
0x18000aae3  mov     eax, [rbp+47h+var_7C]
0x18000aae6  jmp     loc_18000A8B6
0x18000aaeb  and     esi, 0FFFFFFEFh
0x18000aaee  jmp     loc_18000A85D
0x18000aaf3  lea     rbx, aNull; "NULL"
0x18000aafa  cmp     [rbp+47h+lpSubKey], 0
0x18000aaff  cmovnz  rbx, [rbp+47h+lpSubKey]
0x18000ab04  lea     rcx, [rbp+47h+pvarg]; this
0x18000ab08  call    ?ChangeType@CComVariant@ATL@@QEAAJGPEBUtagVARIANT@@@Z; ATL::CComVariant::ChangeType(ushort,tagVARIANT const *)
0x18000ab0d  mov     rcx, r15
0x18000ab10  test    eax, eax
0x18000ab12  cmovns  rcx, qword ptr [rbp+47h+pvarg+8]
0x18000ab17  movzx   eax, word ptr [r12]
0x18000ab1c  mov     [rsp+0D0h+var_88], rbx
0x18000ab21  mov     [rsp+0D0h+var_90], esi
0x18000ab25  mov     [rsp+0D0h+var_98], r13
0x18000ab2a  mov     [rsp+0D0h+var_A0], rcx
0x18000ab2f  mov     [rsp+0D0h+var_A8], eax
0x18000ab33  mov     eax, [r14]
0x18000ab36  mov     dword ptr [rsp+0D0h+phkResult], eax
0x18000ab3a  mov     r9d, edi
0x18000ab3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab44  mov     rcx, [rcx+10h]
0x18000ab48  call    WPP_SF_dddSqDS
0x18000ab4d  mov     eax, 0FFFh
0x18000ab52  lea     rbx, WPP_GLOBAL_Control
0x18000ab59  cmp     word ptr [rbp+47h+pvarg], ax
0x18000ab5d  jnz     loc_18000A836
0x18000ab63  mov     eax, 8
0x18000ab68  mov     word ptr [rbp+47h+pvarg], ax
0x18000ab6c  jmp     loc_18000A836
0x18000ab71  mov     r8, r12; struct tagVARIANT *
0x18000ab74  lea     rcx, [rbp+47h+pvarg]; this
0x18000ab78  call    ?ChangeType@CComVariant@ATL@@QEAAJGPEBUtagVARIANT@@@Z; ATL::CComVariant::ChangeType(ushort,tagVARIANT const *)
0x18000ab7d  test    eax, eax
0x18000ab7f  cmovns  r15, qword ptr [rbp+47h+pvarg+8]
0x18000ab84  mov     dword ptr [rsp+0D0h+phkResult], r14d
0x18000ab89  mov     r9, r15
0x18000ab8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab93  mov     rcx, [rcx+10h]
0x18000ab97  call    WPP_SF_SD
0x18000ab9c  mov     eax, 0FFFh
0x18000aba1  cmp     word ptr [rbp+47h+pvarg], ax
0x18000aba5  jnz     loc_18000A9E3
0x18000abab  mov     eax, 8
0x18000abb0  mov     word ptr [rbp+47h+pvarg], ax
0x18000abb4  jmp     loc_18000A9E3
0x18000abb9  xor     edx, edx
0x18000abbb  lea     rcx, [rbp+47h+hKey]
0x18000abbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000abc4  lea     rdx, [rbp+47h+hKey]; phkResult
0x18000abc8  mov     ecx, 20019h; samDesired
0x18000abcd  call    cs:__imp_RegOpenCurrentUser
0x18000abd4  nop     dword ptr [rax+rax+00h]
0x18000abd9  mov     r14d, eax
0x18000abdc  test    eax, eax
0x18000abde  jle     short loc_18000ABEB
0x18000abe0  movzx   r14d, ax
0x18000abe4  or      r14d, 80070000h
0x18000abeb  mov     r10, cs:WPP_GLOBAL_Control
0x18000abf2  cmp     r10, r13
0x18000abf5  jz      loc_18000A8CE
0x18000abfb  test    byte ptr [r10+1Ch], 2
0x18000ac00  jz      loc_18000A8CE
0x18000ac06  mov     edx, 1Ah
0x18000ac0b  mov     r9d, r14d
0x18000ac0e  mov     rcx, [r10+10h]
0x18000ac12  call    WPP_SF_D
0x18000ac17  mov     r10, cs:WPP_GLOBAL_Control
0x18000ac1e  jmp     loc_18000A8CE
0x18000ac23  test    rcx, rcx
0x18000ac26  jz      short loc_18000AC35
0x18000ac28  call    cs:__imp_RegCloseKey
0x18000ac2f  nop     dword ptr [rax+rax+00h]
0x18000ac34  nop
0x18000ac35  lea     rcx, [rbp+47h+arg_20]; this
0x18000ac39  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000ac3e  nop
0x18000ac3f  test    ebx, ebx
0x18000ac41  jz      loc_18000A94D
0x18000ac47  call    cs:__imp_CoRevertToSelf
0x18000ac4e  nop     dword ptr [rax+rax+00h]
0x18000ac53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac5a  cmp     rcx, r13
0x18000ac5d  jmp     loc_18000AA8D
0x18000ac62  xor     edx, edx
0x18000ac64  lea     rcx, [rbp+47h+hKey]
0x18000ac68  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ac6d  lea     rax, [rbp+47h+hKey]
0x18000ac71  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000ac76  mov     r9d, 20019h; samDesired
0x18000ac7c  xor     r8d, r8d; ulOptions
0x18000ac7f  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18000ac83  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000ac8a  call    cs:__imp_RegOpenKeyExW
0x18000ac91  nop     dword ptr [rax+rax+00h]
0x18000ac96  mov     esi, eax
0x18000ac98  test    eax, eax
0x18000ac9a  jle     short loc_18000ACA5
0x18000ac9c  movzx   esi, ax
0x18000ac9f  or      esi, 80070000h
0x18000aca5  test    esi, esi
0x18000aca7  jns     loc_18000A98A
0x18000acad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acb4  cmp     rcx, r13
0x18000acb7  jz      short loc_18000ACD1
0x18000acb9  test    byte ptr [rcx+1Ch], 2
0x18000acbd  jz      short loc_18000ACD1
0x18000acbf  mov     edx, 1Ch
0x18000acc4  mov     r9d, esi
0x18000acc7  mov     rcx, [rcx+10h]
0x18000accb  call    WPP_SF_D
0x18000acd0  nop
0x18000acd1  mov     rcx, [rbp+47h+hKey]; hKey
0x18000acd5  test    rcx, rcx
0x18000acd8  jz      short loc_18000ACE7
0x18000acda  call    cs:__imp_RegCloseKey
0x18000ace1  nop     dword ptr [rax+rax+00h]
0x18000ace6  nop
  ... truncated ...
```
