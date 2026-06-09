# AdvertisingIdHelpers::QueryAdvertisingIdStatus(Delayed::ext_ms_win_familysafety_childaccount_l1_1_0 const &,Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,AdvertisingIdHelpers::AdvertisingIdStatus *,AdvertisingIdHelpers::AdvertisingIdDisableReason *)

- ea: `0x1800c52e4`
- end: `0x1800c57c5`
- name: `?QueryAdvertisingIdStatus@AdvertisingIdHelpers@@YAJAEBVext_ms_win_familysafety_childaccount_l1_1_0@Delayed@@AEBVapi_ms_win_core_winrt_string_l1_1_0@3@PEAW4AdvertisingIdStatus@1@PEAW4AdvertisingIdDisableReason@1@@Z`
- size: `1249`
- prototype: `int(AdvertisingIdHelpers *__hidden this, const struct Delayed::ext_ms_win_familysafety_childaccount_l1_1_0 *, const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *, enum AdvertisingIdHelpers::AdvertisingIdStatus *, enum AdvertisingIdHelpers::AdvertisingIdDisableReason *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c445c`

## callees

- `0x180008da4`
- `0x180008dc0`
- `0x180011cc4`
- `0x180011ce4`
- `0x18009f918`
- `0x1800c3870`
- `0x1800c3fd8`
- `0x1800c52e4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c54c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c55f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5716`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c54c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c55f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c55de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c55de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c54bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5514`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c55a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c54bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5514`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c55a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c53d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c543d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c55e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c56b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c56c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c570e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c53d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c543d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c55e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c56b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c56c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c570e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c53a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c566d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c577c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c53a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c566d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c577c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c561b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5740`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c561b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5740`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c5493`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c5493`

## string_xrefs

- `0x1800c53e8`: `onecore\base\appcompat\programs\devicecensus\dlls\privacysettingspriv.cpp`
- `0x1800c54e2`: `onecore\base\appcompat\programs\devicecensus\dlls\privacysettingspriv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AdvertisingIdHelpers::QueryAdvertisingIdStatus(
        AdvertisingIdHelpers *this,
        const struct Delayed::ext_ms_win_familysafety_childaccount_l1_1_0 *a2,
        const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *a3,
        enum AdvertisingIdHelpers::AdvertisingIdStatus *a4)
{
  const struct Delayed::ext_ms_win_familysafety_childaccount_l1_1_0 *v4; // r12
  AdvertisingIdHelpers *v5; // r13
  int v6; // edi
  int v7; // r15d
  LSTATUS v8; // eax
  bool *v9; // rdx
  int ValueW; // ebx
  bool v11; // r14
  __int64 v12; // rdx
  int v14; // r14d
  BOOL v15; // eax
  const char *v16; // r9
  LPWSTR v17; // r13
  _QWORD *v18; // r14
  HKEY v19; // r12
  DWORD LastError; // ebx
  void *v21; // rcx
  void *v22; // rcx
  HKEY v23; // rdi
  DWORD v24; // ebx
  LSTATUS v25; // eax
  int v26; // eax
  HKEY v27; // rdi
  DWORD v28; // ebx
  LSTATUS v29; // eax
  bool v30; // cc
  int phkResult; // [rsp+20h] [rbp-A9h]
  _BYTE v32[4]; // [rsp+40h] [rbp-89h] BYREF
  int v33; // [rsp+44h] [rbp-85h] BYREF
  BOOL pvData; // [rsp+48h] [rbp-81h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-7Dh] BYREF
  HKEY hkey; // [rsp+50h] [rbp-79h] BYREF
  DWORD v37; // [rsp+58h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-69h] BYREF
  HKEY v39; // [rsp+68h] [rbp-61h] BYREF
  void *Block; // [rsp+70h] [rbp-59h] BYREF
  HKEY *p_hkey; // [rsp+78h] [rbp-51h]
  LPWSTR StringSid; // [rsp+80h] [rbp-49h] BYREF
  char v43; // [rsp+88h] [rbp-41h]
  const struct Delayed::ext_ms_win_familysafety_childaccount_l1_1_0 *v44; // [rsp+90h] [rbp-39h]
  AdvertisingIdHelpers *v45; // [rsp+98h] [rbp-31h]
  const struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *v46; // [rsp+A0h] [rbp-29h]
  enum AdvertisingIdHelpers::AdvertisingIdStatus *v47; // [rsp+A8h] [rbp-21h]
  _QWORD v48[4]; // [rsp+B0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v47 = a4;
  v46 = a3;
  v4 = a2;
  v44 = a2;
  v5 = this;
  v45 = this;
  v6 = 0;
  v39 = 0;
  hKey = 0;
  v7 = 1;
  v33 = 1;
  v37 = 0;
  v32[0] = 0;
  pvData = 0;
  pcbData = 0;
  hkey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo", 0, 0x20119u, &hkey);
  ValueW = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
      goto LABEL_5;
LABEL_17:
    v11 = pvData;
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_19;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"DisabledByGroupPolicy", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
  {
    ValueW = 0;
    pvData = 0;
  }
  if ( !ValueW )
    goto LABEL_17;
LABEL_5:
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( hkey )
    RegCloseKey(hkey);
  v11 = 0;
  if ( ValueW < 0 )
  {
    v12 = 1007;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\privacysettingspriv.cpp",
      (const char *)(unsigned int)ValueW,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v39 )
      RegCloseKey(v39);
    return (unsigned int)ValueW;
  }
LABEL_19:
  if ( v11 )
  {
    v14 = 2;
    goto LABEL_61;
  }
  pcbData = 0;
  if ( *((_QWORD *)v5 + 2) && *((_QWORD *)v4 + 2) )
  {
    hkey = 0;
    wil::GetTokenInformation<_TOKEN_USER>(&Block, (__int64)v9);
    p_hkey = &hkey;
    StringSid = 0;
    v43 = 1;
    v15 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
    pvData = v15;
    if ( v43 )
    {
      v17 = StringSid;
      v18 = p_hkey;
      v19 = *p_hkey;
      if ( *p_hkey )
      {
        LastError = GetLastError();
        LocalFree(v19);
        SetLastError(LastError);
        v15 = pvData;
      }
      *v18 = v17;
      v4 = v44;
      v5 = v45;
    }
    if ( !v15 )
    {
      ValueW = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x367,
                 (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\privacysettingspriv.cpp",
                 v16);
      v21 = Block;
      Block = 0;
      if ( v21 )
        operator delete(v21);
      if ( hkey )
        LocalFree(hkey);
      if ( ValueW >= 0 )
        goto LABEL_33;
LABEL_40:
      v12 = 1016;
      goto LABEL_11;
    }
    Delayed::HStringReference::HStringReference((Delayed::HStringReference *)v48, v4, (const unsigned __int16 *)hkey);
    ValueW = (*((__int64 (__fastcall **)(_QWORD, DWORD *))v5 + 2))(v48[0], &pcbData);
    v22 = Block;
    Block = 0;
    if ( ValueW < 0 )
    {
      if ( v22 )
        operator delete(v22);
      if ( hkey )
        LocalFree(hkey);
      goto LABEL_40;
    }
    if ( v22 )
      operator delete(v22);
    if ( hkey )
      LocalFree(hkey);
    if ( pcbData )
    {
LABEL_47:
      v14 = 2;
      v7 = 2;
      goto LABEL_61;
    }
  }
LABEL_33:
  ValueW = AdvertisingIdHelpers::impl::CheckMsaChildAccount((AdvertisingIdHelpers::impl *)v32, v9);
  if ( ValueW < 0 )
  {
    v12 = 1024;
    goto LABEL_11;
  }
  if ( v32[0] )
    goto LABEL_47;
  v14 = 1;
  v23 = hKey;
  if ( hKey )
  {
    v24 = GetLastError();
    RegCloseKey(v23);
    SetLastError(v24);
  }
  hKey = 0;
  v25 = RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
          0,
          0x20119u,
          &hKey);
  v6 = v25;
  if ( v25 > 0 )
    v6 = (unsigned __int16)v25 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( v6 != -2147024894 )
      goto LABEL_60;
  }
  else
  {
    v37 = 4;
    v6 = RegGetValueW(hKey, 0, L"Enabled", 0x10u, 0, &v33, &v37);
    if ( v6 != 2 )
    {
      v26 = v33;
      if ( v33 != -1 )
      {
        if ( v6 )
        {
          if ( v6 <= 0 )
            goto LABEL_60;
          v6 = (unsigned __int16)v6;
          goto LABEL_59;
        }
LABEL_80:
        if ( v26 )
        {
          v14 = 1;
          goto LABEL_83;
        }
LABEL_81:
        v14 = 0;
LABEL_83:
        v6 = 0;
        v7 = 0;
LABEL_61:
        *(_DWORD *)v46 = v14;
        if ( v47 )
          *(_DWORD *)v47 = v7;
        goto LABEL_63;
      }
    }
  }
  v33 = 0;
  v27 = v39;
  if ( v39 )
  {
    v28 = GetLastError();
    RegCloseKey(v27);
    SetLastError(v28);
  }
  v39 = 0;
  v29 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
          0,
          0x20119u,
          &v39);
  v6 = v29;
  if ( !v29 )
  {
    v37 = 4;
    v29 = RegGetValueW(v39, 0, L"Enabled", 0x10u, 0, &v33, &v37);
    v6 = v29;
    if ( v29 == 2 )
    {
      v33 = 0;
      goto LABEL_81;
    }
    v30 = v29 <= 0;
    if ( v29 )
      goto LABEL_75;
LABEL_79:
    v26 = v33;
    goto LABEL_80;
  }
  if ( v29 == 2 )
    goto LABEL_79;
  v30 = v29 <= 0;
LABEL_75:
  if ( !v30 )
  {
    v6 = (unsigned __int16)v29;
LABEL_59:
    v6 |= 0x80070000;
  }
LABEL_60:
  v7 = 0;
  if ( v6 >= 0 )
    goto LABEL_61;
LABEL_63:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v39 )
    RegCloseKey(v39);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c52e4  push    rbp
0x1800c52e6  push    rbx
0x1800c52e7  push    rsi
0x1800c52e8  push    rdi
0x1800c52e9  push    r12
0x1800c52eb  push    r13
0x1800c52ed  push    r14
0x1800c52ef  push    r15
0x1800c52f1  lea     rbp, [rsp-1Fh]
0x1800c52f6  sub     rsp, 0E8h
0x1800c52fd  mov     rax, cs:__security_cookie
0x1800c5304  xor     rax, rsp
0x1800c5307  mov     [rbp+57h+var_50], rax
0x1800c530b  mov     [rbp+57h+var_78], r9
0x1800c530f  mov     [rbp+57h+var_80], r8
0x1800c5313  mov     r12, rdx
0x1800c5316  mov     [rbp+57h+var_90], rdx
0x1800c531a  mov     r13, rcx
0x1800c531d  mov     [rbp+57h+var_88], rcx
0x1800c5321  xor     edi, edi
0x1800c5323  mov     [rbp+57h+var_B8], rdi
0x1800c5327  mov     [rbp+57h+hKey], rdi
0x1800c532b  lea     r15d, [rdi+1]
0x1800c532f  mov     [rsp+120h+var_DC], r15d
0x1800c5334  mov     [rbp+57h+var_C8], edi
0x1800c5337  mov     [rsp+120h+var_E0], dil
0x1800c533c  mov     [rsp+120h+var_D8], edi
0x1800c5340  mov     [rbp+57h+var_D4], edi
0x1800c5343  mov     [rbp+57h+hkey], rdi
0x1800c5347  lea     rax, [rbp+57h+hkey]
0x1800c534b  mov     [rsp+120h+phkResult], rax; phkResult
0x1800c5350  mov     r9d, 20119h; samDesired
0x1800c5356  xor     r8d, r8d; ulOptions
0x1800c5359  lea     rdx, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows"...
0x1800c5360  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5367  call    cs:__imp_RegOpenKeyExW
0x1800c536d  mov     ebx, eax
0x1800c536f  test    eax, eax
0x1800c5371  jnz     loc_1800C5422
0x1800c5377  mov     [rbp+57h+var_D4], 4
0x1800c537e  lea     rax, [rbp+57h+var_D4]
0x1800c5382  mov     [rsp+120h+pcbData], rax; pcbData
0x1800c5387  lea     rax, [rsp+120h+var_D8]
0x1800c538c  mov     [rsp+120h+pvData], rax; pvData
0x1800c5391  mov     [rsp+120h+phkResult], rdi; int
0x1800c5396  lea     r9d, [rdi+10h]; dwFlags
0x1800c539a  lea     r8, aDisabledbygrou; "DisabledByGroupPolicy"
0x1800c53a1  xor     edx, edx; lpSubKey
0x1800c53a3  mov     rcx, [rbp+57h+hkey]; hkey
0x1800c53a7  call    cs:__imp_RegGetValueW
0x1800c53ad  mov     ebx, eax
0x1800c53af  lea     esi, [rdi+2]
0x1800c53b2  cmp     eax, esi
0x1800c53b4  jnz     short loc_1800C53BC
0x1800c53b6  mov     ebx, edi
0x1800c53b8  mov     [rsp+120h+var_D8], edi
0x1800c53bc  test    ebx, ebx
0x1800c53be  jz      short loc_1800C542B
0x1800c53c0  test    ebx, ebx
0x1800c53c2  jle     short loc_1800C53CD
0x1800c53c4  movzx   ebx, bx
0x1800c53c7  or      ebx, 80070000h
0x1800c53cd  mov     rcx, [rbp+57h+hkey]; hKey
0x1800c53d1  test    rcx, rcx
0x1800c53d4  jz      short loc_1800C53DC
0x1800c53d6  call    cs:__imp_RegCloseKey
0x1800c53dc  mov     r14b, dil
0x1800c53df  test    ebx, ebx
0x1800c53e1  jns     short loc_1800C5443
0x1800c53e3  mov     edx, 3EFh; void *
0x1800c53e8  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c53ef  mov     r9d, ebx; char *
0x1800c53f2  mov     rcx, [rbp+5Fh]; this
0x1800c53f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c53fb  nop
0x1800c53fc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c5400  test    rcx, rcx
0x1800c5403  jz      short loc_1800C540C
0x1800c5405  call    cs:__imp_RegCloseKey
0x1800c540b  nop
0x1800c540c  mov     rcx, [rbp+57h+var_B8]; hKey
0x1800c5410  test    rcx, rcx
0x1800c5413  jz      short loc_1800C541B
0x1800c5415  call    cs:__imp_RegCloseKey
0x1800c541b  mov     eax, ebx
0x1800c541d  jmp     loc_1800C56CD
0x1800c5422  mov     esi, 2
0x1800c5427  cmp     eax, esi
0x1800c5429  jnz     short loc_1800C53C0
0x1800c542b  cmp     [rsp+120h+var_D8], r15d
0x1800c5430  setz    r14b
0x1800c5434  mov     rcx, [rbp+57h+hkey]; hKey
0x1800c5438  test    rcx, rcx
0x1800c543b  jz      short loc_1800C5443
0x1800c543d  call    cs:__imp_RegCloseKey
0x1800c5443  xor     ebx, ebx
0x1800c5445  test    r14b, r14b
0x1800c5448  jz      short loc_1800C5452
0x1800c544a  mov     r14d, esi
0x1800c544d  jmp     loc_1800C5699
0x1800c5452  mov     [rbp+57h+var_D4], ebx
0x1800c5455  cmp     [r13+10h], rbx
0x1800c5459  jz      loc_1800C55B4
0x1800c545f  cmp     [r12+10h], rbx
0x1800c5464  jz      loc_1800C55B4
0x1800c546a  mov     [rbp+57h+hkey], rbx
0x1800c546e  lea     rcx, [rbp+57h+Block]
0x1800c5472  call    ??$GetTokenInformation@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x1800c5477  nop
0x1800c5478  lea     rax, [rbp+57h+hkey]
0x1800c547c  mov     [rbp+57h+var_A8], rax
0x1800c5480  mov     [rbp+57h+StringSid], rbx
0x1800c5484  mov     [rbp+57h+var_98], r15b
0x1800c5488  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800c548c  mov     rcx, [rbp+57h+Block]
0x1800c5490  mov     rcx, [rcx]; Sid
0x1800c5493  call    cs:__imp_ConvertSidToStringSidW
0x1800c5499  mov     [rsp+120h+var_D8], eax
0x1800c549d  cmp     [rbp+57h+var_98], bl
0x1800c54a0  jz      short loc_1800C54DA
0x1800c54a2  mov     r13, [rbp+57h+StringSid]
0x1800c54a6  mov     r14, [rbp+57h+var_A8]
0x1800c54aa  mov     r12, [r14]
0x1800c54ad  test    r12, r12
0x1800c54b0  jz      short loc_1800C54CF
0x1800c54b2  call    cs:__imp_GetLastError
0x1800c54b8  mov     ebx, eax
0x1800c54ba  mov     rcx, r12; hMem
0x1800c54bd  call    cs:__imp_LocalFree
0x1800c54c3  mov     ecx, ebx; dwErrCode
0x1800c54c5  call    cs:__imp_SetLastError
0x1800c54cb  mov     eax, [rsp+120h+var_D8]
0x1800c54cf  mov     [r14], r13
0x1800c54d2  mov     r12, [rbp+57h+var_90]
0x1800c54d6  mov     r13, [rbp+57h+var_88]
0x1800c54da  test    eax, eax
0x1800c54dc  jnz     short loc_1800C553C
0x1800c54de  mov     rcx, [rbp+5Fh]; this
0x1800c54e2  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c54e9  mov     edx, 367h; void *
0x1800c54ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c54f3  mov     ebx, eax
0x1800c54f5  mov     rcx, [rbp+57h+Block]; Block
0x1800c54f9  xor     r12d, r12d
0x1800c54fc  mov     [rbp+57h+Block], r12
0x1800c5500  test    rcx, rcx
0x1800c5503  jz      short loc_1800C550B
0x1800c5505  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c550a  nop
0x1800c550b  mov     rcx, [rbp+57h+hkey]; hMem
0x1800c550f  test    rcx, rcx
0x1800c5512  jz      short loc_1800C551A
0x1800c5514  call    cs:__imp_LocalFree
0x1800c551a  test    ebx, ebx
0x1800c551c  js      short loc_1800C5588
0x1800c551e  lea     rcx, [rsp+120h+var_E0]; this
0x1800c5523  call    ?CheckMsaChildAccount@impl@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::impl::CheckMsaChildAccount(bool *)
0x1800c5528  mov     ebx, eax
0x1800c552a  test    eax, eax
0x1800c552c  jns     loc_1800C55CB
0x1800c5532  mov     edx, 400h
0x1800c5537  jmp     loc_1800C53E8
0x1800c553c  mov     r8, [rbp+57h+hkey]; unsigned __int16 *
0x1800c5540  mov     rdx, r12; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800c5543  lea     rcx, [rbp+57h+var_70]; this
0x1800c5547  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800c554c  lea     rdx, [rbp+57h+var_D4]
0x1800c5550  mov     rcx, [rbp+57h+var_70]
0x1800c5554  mov     rax, [r13+10h]
0x1800c5558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c555d  mov     ebx, eax
0x1800c555f  xor     r12d, r12d
0x1800c5562  mov     rcx, [rbp+57h+Block]; Block
0x1800c5566  mov     [rbp+57h+Block], r12
0x1800c556a  test    eax, eax
0x1800c556c  jns     short loc_1800C5592
0x1800c556e  test    rcx, rcx
0x1800c5571  jz      short loc_1800C5579
0x1800c5573  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c5578  nop
0x1800c5579  mov     rcx, [rbp+57h+hkey]; hMem
0x1800c557d  test    rcx, rcx
0x1800c5580  jz      short loc_1800C5588
0x1800c5582  call    cs:__imp_LocalFree
0x1800c5588  mov     edx, 3F8h
0x1800c558d  jmp     loc_1800C53E8
0x1800c5592  test    rcx, rcx
0x1800c5595  jz      short loc_1800C559D
0x1800c5597  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c559c  nop
0x1800c559d  mov     rcx, [rbp+57h+hkey]; hMem
0x1800c55a1  test    rcx, rcx
0x1800c55a4  jz      short loc_1800C55AC
0x1800c55a6  call    cs:__imp_LocalFree
0x1800c55ac  cmp     [rbp+57h+var_D4], r12d
0x1800c55b0  jnz     short loc_1800C55C0
0x1800c55b2  jmp     short loc_1800C55B7
0x1800c55b4  xor     r12d, r12d
0x1800c55b7  test    r12b, r12b
0x1800c55ba  jz      loc_1800C551E
0x1800c55c0  mov     r14d, esi
0x1800c55c3  mov     r15d, esi
0x1800c55c6  jmp     loc_1800C5699
0x1800c55cb  cmp     [rsp+120h+var_E0], r12b
0x1800c55d0  jnz     short loc_1800C55C0
0x1800c55d2  mov     r14d, r15d
0x1800c55d5  mov     rdi, [rbp+57h+hKey]
0x1800c55d9  test    rdi, rdi
0x1800c55dc  jz      short loc_1800C55F7
0x1800c55de  call    cs:__imp_GetLastError
0x1800c55e4  mov     ebx, eax
0x1800c55e6  mov     rcx, rdi; hKey
0x1800c55e9  call    cs:__imp_RegCloseKey
0x1800c55ef  mov     ecx, ebx; dwErrCode
0x1800c55f1  call    cs:__imp_SetLastError
0x1800c55f7  mov     [rbp+57h+hKey], r12
0x1800c55fb  lea     rax, [rbp+57h+hKey]
0x1800c55ff  mov     [rsp+120h+phkResult], rax; phkResult
0x1800c5604  mov     r9d, 20119h; samDesired
0x1800c560a  xor     r8d, r8d; ulOptions
0x1800c560d  lea     rdx, aSoftwareMicros_64; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c5614  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c561b  call    cs:__imp_RegOpenKeyExW
0x1800c5621  mov     edi, eax
0x1800c5623  mov     r13d, 80070000h
0x1800c5629  test    eax, eax
0x1800c562b  jle     short loc_1800C5633
0x1800c562d  movzx   edi, ax
0x1800c5630  or      edi, r13d
0x1800c5633  test    edi, edi
0x1800c5635  js      loc_1800C56ED
0x1800c563b  mov     [rbp+57h+var_C8], 4
0x1800c5642  lea     rax, [rbp+57h+var_C8]
0x1800c5646  mov     [rsp+120h+pcbData], rax; pcbData
0x1800c564b  lea     rax, [rsp+120h+var_DC]
0x1800c5650  mov     [rsp+120h+pvData], rax; pvData
0x1800c5655  mov     [rsp+120h+phkResult], r12; pdwType
0x1800c565a  mov     r9d, 10h; dwFlags
0x1800c5660  lea     r8, aEnabled_1; "Enabled"
0x1800c5667  xor     edx, edx; lpSubKey
0x1800c5669  mov     rcx, [rbp+57h+hKey]; hkey
0x1800c566d  call    cs:__imp_RegGetValueW
0x1800c5673  mov     edi, eax
0x1800c5675  cmp     eax, esi
0x1800c5677  jz      short loc_1800C56F5
0x1800c5679  mov     eax, [rsp+120h+var_DC]
0x1800c567d  cmp     eax, 0FFFFFFFFh
0x1800c5680  jz      short loc_1800C56F5
0x1800c5682  test    edi, edi
0x1800c5684  jz      loc_1800C57AD
0x1800c568a  jle     short loc_1800C5692
0x1800c568c  movzx   edi, di
0x1800c568f  or      edi, r13d
0x1800c5692  mov     r15d, r12d
0x1800c5695  test    edi, edi
0x1800c5697  js      short loc_1800C56AC
0x1800c5699  mov     rax, [rbp+57h+var_80]
0x1800c569d  mov     [rax], r14d
0x1800c56a0  mov     rax, [rbp+57h+var_78]
0x1800c56a4  test    rax, rax
0x1800c56a7  jz      short loc_1800C56AC
0x1800c56a9  mov     [rax], r15d
0x1800c56ac  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c56b0  test    rcx, rcx
0x1800c56b3  jz      short loc_1800C56BC
0x1800c56b5  call    cs:__imp_RegCloseKey
0x1800c56bb  nop
0x1800c56bc  mov     rcx, [rbp+57h+var_B8]; hKey
0x1800c56c0  test    rcx, rcx
0x1800c56c3  jz      short loc_1800C56CB
0x1800c56c5  call    cs:__imp_RegCloseKey
0x1800c56cb  mov     eax, edi
0x1800c56cd  mov     rcx, [rbp+57h+var_50]
0x1800c56d1  xor     rcx, rsp; StackCookie
0x1800c56d4  call    __security_check_cookie
0x1800c56d9  add     rsp, 0E8h
0x1800c56e0  pop     r15
0x1800c56e2  pop     r14
0x1800c56e4  pop     r13
0x1800c56e6  pop     r12
0x1800c56e8  pop     rdi
0x1800c56e9  pop     rsi
0x1800c56ea  pop     rbx
0x1800c56eb  pop     rbp
0x1800c56ec  retn
0x1800c56ed  cmp     edi, 80070002h
0x1800c56f3  jnz     short loc_1800C5692
0x1800c56f5  mov     [rsp+120h+var_DC], r12d
0x1800c56fa  mov     rdi, [rbp+57h+var_B8]
0x1800c56fe  test    rdi, rdi
0x1800c5701  jz      short loc_1800C571C
0x1800c5703  call    cs:__imp_GetLastError
0x1800c5709  mov     ebx, eax
0x1800c570b  mov     rcx, rdi; hKey
0x1800c570e  call    cs:__imp_RegCloseKey
0x1800c5714  mov     ecx, ebx; dwErrCode
0x1800c5716  call    cs:__imp_SetLastError
0x1800c571c  mov     [rbp+57h+var_B8], r12
0x1800c5720  lea     rax, [rbp+57h+var_B8]
0x1800c5724  mov     [rsp+120h+phkResult], rax; phkResult
  ... truncated ...
```
