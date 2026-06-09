# DavServerExists

- ea: `0x18000e494`
- end: `0x18000ec4c`
- name: `DavServerExists`
- size: `1976`
- prototype: `__int64 __fastcall(const WCHAR *, wchar_t *, _DWORD *)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180001600`
- `0x180002970`
- `0x180004340`

## callees

- `0x180001010`
- `0x1800028f0`
- `0x1800051a0`
- `0x180009c00`
- `0x18000d510`
- `0x18000e494`
- `0x180010a14`
- `0x180010a3c`
- `0x180010be8`
- `0x180010c28`
- `0x180010d00`
- `0x180011340`
- `0x180011e76`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000e73f`
- `msvcrt!_wcsnicmp` at `0x18000e73f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e86d`
- `KERNEL32!LocalAlloc` at `0x18000e6b3`
- `KERNEL32!LocalAlloc` at `0x18000e7c1`
- `KERNEL32!LocalAlloc` at `0x18000e857`
- `KERNEL32!LocalAlloc` at `0x18000e6b3`
- `KERNEL32!LocalAlloc` at `0x18000e7c1`
- `KERNEL32!LocalAlloc` at `0x18000e857`
- `KERNEL32!LocalFree` at `0x18000e64e`
- `KERNEL32!LocalFree` at `0x18000e65c`
- `KERNEL32!LocalFree` at `0x18000e67d`
- `KERNEL32!LocalFree` at `0x18000e64e`
- `KERNEL32!LocalFree` at `0x18000e65c`
- `KERNEL32!LocalFree` at `0x18000e67d`
- `RPCRT4!NdrClientCall3` at `0x18000ea25`
- `RPCRT4!NdrClientCall3` at `0x18000ea25`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800123e6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800123e6`
- `RPCRT4!RpcBindingFree` at `0x18000e66f`
- `RPCRT4!RpcBindingFree` at `0x18000e66f`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000e8bf`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000e8bf`

## pseudocode

```c
__int64 __fastcall DavServerExists(const WCHAR *a1, wchar_t *a2, _DWORD *a3)
{
  const WCHAR *Pointer; // rbx
  _WORD *v6; // r15
  _WORD *v7; // r14
  _QWORD *v8; // rcx
  const WCHAR *v9; // rsi
  const WCHAR *v10; // r12
  unsigned __int64 v11; // rax
  wchar_t *v12; // r12
  char v13; // si
  _DWORD *v14; // rax
  const char *v15; // r9
  SIZE_T v17; // r14
  wchar_t *v18; // rax
  DWORD LastError; // eax
  const WCHAR *v20; // rdx
  size_t v21; // rdx
  const wchar_t *v22; // r14
  _WORD *v23; // rax
  DWORD v24; // eax
  __int64 v25; // rdx
  wchar_t *i; // rcx
  wchar_t v27; // ax
  _DWORD *v28; // rax
  int v29; // r12d
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  unsigned int v33; // eax
  char v34; // r14
  CLIENT_CALL_RETURN v35; // r8
  size_t v36; // rax
  __int64 v37; // rcx
  _DWORD *v38; // rsi
  __int64 v39; // [rsp+40h] [rbp-2E8h]
  char v40[7]; // [rsp+51h] [rbp-2D7h] BYREF
  _DWORD *v41; // [rsp+58h] [rbp-2D0h]
  char v42; // [rsp+60h] [rbp-2C8h]
  wchar_t *v43; // [rsp+68h] [rbp-2C0h]
  int v44; // [rsp+70h] [rbp-2B8h]
  DWORD Size; // [rsp+74h] [rbp-2B4h] BYREF
  size_t v46; // [rsp+78h] [rbp-2B0h]
  size_t v47; // [rsp+80h] [rbp-2A8h]
  _WORD *v48; // [rsp+88h] [rbp-2A0h]
  _DWORD *v49; // [rsp+90h] [rbp-298h]
  _WORD *v50; // [rsp+98h] [rbp-290h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+A0h] [rbp-288h] BYREF
  LPCWSTR UncPath; // [rsp+A8h] [rbp-280h]
  size_t pcchLength; // [rsp+B0h] [rbp-278h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+B8h] [rbp-270h]
  _DWORD *v55; // [rsp+C0h] [rbp-268h]
  wchar_t *v56; // [rsp+C8h] [rbp-260h]
  WCHAR Url[264]; // [rsp+D0h] [rbp-258h] BYREF

  v41 = a3;
  pszDest = a2;
  UncPath = a1;
  v56 = a2;
  v55 = a3;
  LODWORD(Pointer) = 0;
  Binding = 0;
  v46 = 0;
  pcchLength = 0;
  v6 = 0;
  v49 = 0;
  memset_0(Url, 0, 0x208u);
  Size = 260;
  v7 = 0;
  v48 = 0;
  v50 = 0;
  *a3 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a1);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = a1 + 2;
  v10 = v9;
  while ( *v9 != 92 && *v9 )
    ++v9;
  if ( v9 < v10 || (v11 = v9 - v10, v11 > 0x104) )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_(v8[2], 206, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v12 = 0;
    v13 = 0;
    goto LABEL_17;
  }
  if ( v11 + 1 > 0x105 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_(v8[2], 207, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v12 = 0;
LABEL_15:
    v13 = 0;
LABEL_16:
    v7 = 0;
LABEL_17:
    v14 = v41;
    goto LABEL_18;
  }
  v17 = 2 * (v11 + 1);
  v18 = (wchar_t *)LocalAlloc(0x40u, v17);
  v43 = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
      v8 = WPP_GLOBAL_Control;
    }
    LODWORD(Pointer) = 1222;
    v12 = v43;
    goto LABEL_39;
  }
  v20 = v10;
  v12 = v18;
  memcpy_0(v18, v20, v17 - 2);
  v12[v17 / 2 - 1] = 0;
  if ( *v9 == 92 )
  {
    v22 = v9 + 11;
    if ( _wcsnicmp(v9 + 1, L"DavWWWRoot", 0xAu) )
      v22 = v9;
    if ( StringCchLengthW(v22, v21, &pcchLength) < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      goto LABEL_15;
    }
    v46 = pcchLength;
    if ( pcchLength )
    {
      v23 = LocalAlloc(0x40u, 2 * pcchLength + 2);
      v6 = v23;
      v49 = v23;
      if ( !v23 )
      {
        v24 = GetLastError();
        LODWORD(Pointer) = v24;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v25 = 210;
LABEL_52:
        WPP_SF_d(v8[2], v25, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v24);
        v8 = WPP_GLOBAL_Control;
LABEL_39:
        v13 = 0;
        goto LABEL_16;
      }
      for ( i = v23; ; ++i )
      {
        v27 = *v22;
        if ( !*v22 )
          break;
        if ( v27 == 92 )
          v27 = 47;
        *i = v27;
        ++v22;
      }
      *i = 0;
    }
    else
    {
      v46 = 1;
      v28 = LocalAlloc(0x40u, 4u);
      v6 = v28;
      v49 = v28;
      if ( !v28 )
      {
        v24 = GetLastError();
        LODWORD(Pointer) = v24;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v25 = 211;
        goto LABEL_52;
      }
      *v28 = 47;
    }
  }
  v29 = 0;
  if ( DavGetHTTPFromUNCPath(UncPath, Url, &Size) )
  {
    v7 = 0;
  }
  else
  {
    DavClntQueryWinInetCookies((__int64)Url, &v50);
    v7 = v50;
    v48 = v50;
    if ( v50 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          212,
          (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
          (_DWORD)v50,
          (__int64)Url);
      v32 = -1;
      do
        ++v32;
      while ( v7[v32] );
      v29 = v32 + 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, Url);
    }
  }
  v33 = DavBindTheRpcHandle(&Binding, v30, v31);
  if ( v33 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v33);
      v8 = WPP_GLOBAL_Control;
    }
    LODWORD(Pointer) = 1222;
    v12 = v43;
    v13 = 0;
    goto LABEL_17;
  }
  v42 = 1;
  v34 = 1;
  v40[0] = 0;
LABEL_82:
  UncPath = 0;
  LODWORD(v39) = v29;
  Pointer = (const WCHAR *)NdrClientCall3(
                             (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                             3u,
                             0,
                             Binding,
                             v43,
                             v6,
                             v40,
                             v48,
                             v39).Pointer;
  UncPath = Pointer;
  v44 = (int)Pointer;
  if ( (_DWORD)Pointer && v34 )
  {
    v36 = v46;
    v34 = 0;
    while ( 1 )
    {
      v47 = v36;
      if ( !v36 )
        goto LABEL_91;
      if ( v6[v36] )
        break;
      --v36;
    }
    while ( v36 && v6[v36] == 47 )
      v47 = --v36;
LABEL_91:
    while ( 1 )
    {
      v37 = v36;
      if ( !v36 )
        break;
      if ( v6[v37] == 47 )
      {
        v6[v37] = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_D)(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            215,
            (CLIENT_CALL_RETURN)v35.Simple,
            (unsigned int)Pointer);
        goto LABEL_82;
      }
      v47 = --v36;
    }
  }
  v38 = v41;
  if ( v40[0] )
    *v41 = 1;
  if ( (_DWORD)Pointer )
  {
    if ( (_DWORD)Pointer == 12175 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      *v38 = 0;
      LODWORD(Pointer) = 1790;
      v44 = 1790;
      SetLastError(0x6FEu);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
          (unsigned int)Pointer);
      SetLastError((DWORD)Pointer);
      *v38 = 0;
    }
  }
  v8 = WPP_GLOBAL_Control;
  v7 = v48;
  v12 = v43;
  v14 = v41;
  v13 = 1;
LABEL_18:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
  {
    v15 = "TRUE";
    if ( !*v14 )
      v15 = "FALSE";
    WPP_SF_s(v8[2], 219, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v15);
  }
  if ( v12 )
  {
    if ( pszDest )
      StringCchCopyW(pszDest, 0x105u, v12);
    LocalFree(v12);
  }
  if ( v6 )
    LocalFree(v6);
  if ( v13 )
    RpcBindingFree(&Binding);
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000e494  push    rbx
0x18000e496  push    rsi
0x18000e497  push    rdi
0x18000e498  push    r12
0x18000e49a  push    r13
0x18000e49c  push    r14
0x18000e49e  push    r15
0x18000e4a0  sub     rsp, 2F0h
0x18000e4a7  mov     rax, cs:__security_cookie
0x18000e4ae  xor     rax, rsp
0x18000e4b1  mov     [rsp+328h+var_48], rax
0x18000e4b9  mov     r12, r8
0x18000e4bc  mov     [rsp+328h+var_2D0], r8
0x18000e4c1  mov     [rsp+328h+pszDest], rdx
0x18000e4c9  mov     rsi, rcx
0x18000e4cc  mov     [rsp+328h+UncPath], rcx
0x18000e4d4  mov     [rsp+328h+var_260], rdx
0x18000e4dc  mov     [rsp+328h+var_268], r8
0x18000e4e4  xor     edi, edi
0x18000e4e6  mov     ebx, edi
0x18000e4e8  mov     [rsp+328h+Binding], rdi
0x18000e4f0  mov     eax, edi
0x18000e4f2  mov     [rsp+328h+var_2B0], rax
0x18000e4f7  mov     [rsp+328h+pcchLength], rax
0x18000e4ff  mov     r15d, edi
0x18000e502  mov     [rsp+328h+var_298], rdi
0x18000e50a  xor     edx, edx; Val
0x18000e50c  mov     r8d, 208h; Size
0x18000e512  lea     rcx, [rsp+328h+Url]; void *
0x18000e51a  call    memset_0
0x18000e51f  mov     [rsp+328h+Size], 104h
0x18000e527  mov     r14d, edi
0x18000e52a  mov     [rsp+328h+var_2A0], rdi
0x18000e532  mov     [rsp+328h+var_290], rdi
0x18000e53a  mov     [r12], edi
0x18000e53e  lea     r13, WPP_GLOBAL_Control
0x18000e545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e54c  cmp     rcx, r13
0x18000e54f  jz      short loc_18000E576
0x18000e551  test    byte ptr [rcx+1Ch], 20h
0x18000e555  jz      short loc_18000E576
0x18000e557  mov     edx, 0CDh
0x18000e55c  mov     r9, rsi
0x18000e55f  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e566  mov     rcx, [rcx+10h]
0x18000e56a  call    WPP_SF_S
0x18000e56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e576  add     rsi, 4
0x18000e57a  mov     r12, rsi
0x18000e57d  jmp     short loc_18000E588
0x18000e57f  test    ax, ax
0x18000e582  jz      short loc_18000E591
0x18000e584  add     rsi, 2
0x18000e588  movzx   eax, word ptr [rsi]
0x18000e58b  cmp     ax, 5Ch ; '\'
0x18000e58f  jnz     short loc_18000E57F
0x18000e591  cmp     rsi, r12
0x18000e594  jb      loc_18000EC1A
0x18000e59a  mov     rax, rsi
0x18000e59d  sub     rax, r12
0x18000e5a0  sar     rax, 1
0x18000e5a3  cmp     rax, 104h
0x18000e5a9  ja      loc_18000EC1A
0x18000e5af  lea     r14, [rax+1]
0x18000e5b3  cmp     r14, 105h
0x18000e5ba  jbe     loc_18000E6A8
0x18000e5c0  cmp     rcx, r13
0x18000e5c3  jz      short loc_18000E5E7
0x18000e5c5  test    byte ptr [rcx+1Ch], 1
0x18000e5c9  jz      short loc_18000E5E7
0x18000e5cb  mov     edx, 0CFh
0x18000e5d0  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e5d7  mov     rcx, [rcx+10h]
0x18000e5db  call    WPP_SF_
0x18000e5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e7  mov     r12, rdi
0x18000e5ea  mov     sil, bl
0x18000e5ed  mov     r14, rdi
0x18000e5f0  mov     rax, [rsp+328h+var_2D0]
0x18000e5f5  cmp     rcx, r13
0x18000e5f8  jz      short loc_18000E629
0x18000e5fa  test    byte ptr [rcx+1Ch], 2
0x18000e5fe  jz      short loc_18000E629
0x18000e600  lea     rdx, aFalse; "FALSE"
0x18000e607  lea     r9, aTrue; "TRUE"
0x18000e60e  cmp     [rax], edi
0x18000e610  cmovz   r9, rdx
0x18000e614  mov     edx, 0DBh
0x18000e619  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e620  mov     rcx, [rcx+10h]
0x18000e624  call    WPP_SF_s
0x18000e629  test    r12, r12
0x18000e62c  jz      short loc_18000E654
0x18000e62e  mov     rax, [rsp+328h+pszDest]
0x18000e636  test    rax, rax
0x18000e639  jz      short loc_18000E64B
0x18000e63b  mov     r8, r12; pszSrc
0x18000e63e  mov     edx, 105h; cchDest
0x18000e643  mov     rcx, rax; pszDest
0x18000e646  call    StringCchCopyW
0x18000e64b  mov     rcx, r12; hMem
0x18000e64e  call    cs:__imp_LocalFree
0x18000e654  test    r15, r15
0x18000e657  jz      short loc_18000E662
0x18000e659  mov     rcx, r15; hMem
0x18000e65c  call    cs:__imp_LocalFree
0x18000e662  test    sil, sil
0x18000e665  jz      short loc_18000E675
0x18000e667  lea     rcx, [rsp+328h+Binding]; Binding
0x18000e66f  call    cs:__imp_RpcBindingFree
0x18000e675  test    r14, r14
0x18000e678  jz      short loc_18000E683
0x18000e67a  mov     rcx, r14; hMem
0x18000e67d  call    cs:__imp_LocalFree
0x18000e683  mov     eax, ebx
0x18000e685  mov     rcx, [rsp+328h+var_48]
0x18000e68d  xor     rcx, rsp; StackCookie
0x18000e690  call    __security_check_cookie
0x18000e695  add     rsp, 2F0h
0x18000e69c  pop     r15
0x18000e69e  pop     r14
0x18000e6a0  pop     r13
0x18000e6a2  pop     r12
0x18000e6a4  pop     rdi
0x18000e6a5  pop     rsi
0x18000e6a6  pop     rbx
0x18000e6a7  retn
0x18000e6a8  add     r14, r14
0x18000e6ab  mov     rdx, r14; uBytes
0x18000e6ae  mov     ecx, 40h ; '@'; uFlags
0x18000e6b3  call    cs:__imp_LocalAlloc
0x18000e6b9  mov     [rsp+328h+var_2C0], rax
0x18000e6be  test    rax, rax
0x18000e6c1  jnz     short loc_18000E70C
0x18000e6c3  call    cs:__imp_GetLastError
0x18000e6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d0  cmp     rcx, r13
0x18000e6d3  jz      short loc_18000E6FA
0x18000e6d5  test    byte ptr [rcx+1Ch], 1
0x18000e6d9  jz      short loc_18000E6FA
0x18000e6db  mov     edx, 0D0h
0x18000e6e0  mov     r9d, eax
0x18000e6e3  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e6ea  mov     rcx, [rcx+10h]
0x18000e6ee  call    WPP_SF_d
0x18000e6f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6fa  mov     ebx, 4C6h
0x18000e6ff  mov     r12, [rsp+328h+var_2C0]
0x18000e704  mov     sil, dil
0x18000e707  jmp     loc_18000E5ED
0x18000e70c  lea     r8, [r14-2]; Size
0x18000e710  mov     rdx, r12; Src
0x18000e713  mov     r12, rax
0x18000e716  mov     rcx, rax; void *
0x18000e719  call    memcpy_0
0x18000e71e  mov     [r14+r12-2], di
0x18000e724  cmp     word ptr [rsi], 5Ch ; '\'
0x18000e728  jnz     loc_18000E8A2
0x18000e72e  lea     rcx, [rsi+2]; String1
0x18000e732  mov     r8d, 0Ah; MaxCount
0x18000e738  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x18000e73f  call    cs:__imp__wcsnicmp
0x18000e745  lea     r14, [rsi+16h]
0x18000e749  test    eax, eax
0x18000e74b  cmovnz  r14, rsi
0x18000e74f  lea     r8, [rsp+328h+pcchLength]; pcchLength
0x18000e757  mov     rcx, r14; psz
0x18000e75a  call    StringCchLengthW
0x18000e75f  test    eax, eax
0x18000e761  jns     short loc_18000E79E
0x18000e763  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e76a  cmp     rcx, r13
0x18000e76d  jz      loc_18000E5EA
0x18000e773  test    byte ptr [rcx+1Ch], 1
0x18000e777  jz      loc_18000E5EA
0x18000e77d  mov     edx, 0D1h
0x18000e782  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e789  mov     rcx, [rcx+10h]
0x18000e78d  call    WPP_SF_
0x18000e792  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e799  jmp     loc_18000E5EA
0x18000e79e  mov     rbx, [rsp+328h+pcchLength]
0x18000e7a6  mov     [rsp+328h+var_2B0], rbx
0x18000e7ab  mov     ecx, 40h ; '@'; uFlags
0x18000e7b0  test    rbx, rbx
0x18000e7b3  jz      loc_18000E849
0x18000e7b9  lea     rdx, ds:2[rbx*2]; uBytes
0x18000e7c1  call    cs:__imp_LocalAlloc
0x18000e7c7  mov     r15, rax
0x18000e7ca  mov     [rsp+328h+var_298], rax
0x18000e7d2  test    rax, rax
0x18000e7d5  jnz     short loc_18000E81D
0x18000e7d7  call    cs:__imp_GetLastError
0x18000e7dd  mov     ebx, eax
0x18000e7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7e6  cmp     rcx, r13
0x18000e7e9  jz      loc_18000E704
0x18000e7ef  test    byte ptr [rcx+1Ch], 1
0x18000e7f3  jz      loc_18000E704
0x18000e7f9  mov     edx, 0D2h
0x18000e7fe  mov     r9d, eax
0x18000e801  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e808  mov     rcx, [rcx+10h]
0x18000e80c  call    WPP_SF_d
0x18000e811  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e818  jmp     loc_18000E704
0x18000e81d  mov     rcx, rax
0x18000e820  mov     esi, 2Fh ; '/'
0x18000e825  movzx   eax, word ptr [r14]
0x18000e829  test    ax, ax
0x18000e82c  jz      short loc_18000E844
0x18000e82e  cmp     ax, 5Ch ; '\'
0x18000e832  jnz     short loc_18000E837
0x18000e834  movzx   eax, si
0x18000e837  mov     [rcx], ax
0x18000e83a  add     rcx, 2
0x18000e83e  add     r14, 2
0x18000e842  jmp     short loc_18000E825
0x18000e844  mov     [rcx], di
0x18000e847  jmp     short loc_18000E8A7
0x18000e849  mov     [rsp+328h+var_2B0], 1
0x18000e852  mov     edx, 4; uBytes
0x18000e857  call    cs:__imp_LocalAlloc
0x18000e85d  mov     r15, rax
0x18000e860  mov     [rsp+328h+var_298], rax
0x18000e868  test    rax, rax
0x18000e86b  jnz     short loc_18000E899
0x18000e86d  call    cs:__imp_GetLastError
0x18000e873  mov     ebx, eax
0x18000e875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e87c  cmp     rcx, r13
0x18000e87f  jz      loc_18000E704
0x18000e885  test    byte ptr [rcx+1Ch], 1
0x18000e889  jz      loc_18000E704
0x18000e88f  mov     edx, 0D3h
0x18000e894  jmp     loc_18000E7FE
0x18000e899  mov     esi, 2Fh ; '/'
0x18000e89e  mov     [rax], esi
0x18000e8a0  jmp     short loc_18000E8A7
0x18000e8a2  mov     esi, 2Fh ; '/'
0x18000e8a7  mov     r12d, edi
0x18000e8aa  lea     r8, [rsp+328h+Size]; lpSize
0x18000e8af  lea     rdx, [rsp+328h+Url]; Url
0x18000e8b7  mov     rcx, [rsp+328h+UncPath]; UncPath
0x18000e8bf  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000e8c5  test    eax, eax
0x18000e8c7  jnz     loc_18000E973
0x18000e8cd  lea     rdx, [rsp+328h+var_290]
0x18000e8d5  lea     rcx, [rsp+328h+Url]
0x18000e8dd  call    DavClntQueryWinInetCookies
0x18000e8e2  mov     r14, [rsp+328h+var_290]
0x18000e8ea  mov     [rsp+328h+var_2A0], r14
0x18000e8f2  test    r14, r14
0x18000e8f5  jz      short loc_18000E942
0x18000e8f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8fe  cmp     rcx, r13
0x18000e901  jz      short loc_18000E92E
0x18000e903  test    byte ptr [rcx+1Ch], 2
0x18000e907  jz      short loc_18000E92E
0x18000e909  mov     edx, 0D4h
0x18000e90e  lea     rax, [rsp+328h+Url]
0x18000e916  mov     [rsp+328h+var_308], rax
0x18000e91b  mov     r9, r14
0x18000e91e  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e925  mov     rcx, [rcx+10h]
0x18000e929  call    WPP_SF_SS
0x18000e92e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e932  inc     rax
0x18000e935  cmp     [r14+rax*2], di
0x18000e93a  jnz     short loc_18000E932
0x18000e93c  lea     r12d, [rax+1]
0x18000e940  jmp     short loc_18000E976
0x18000e942  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e949  cmp     rcx, r13
0x18000e94c  jz      short loc_18000E976
0x18000e94e  test    byte ptr [rcx+1Ch], 2
0x18000e952  jz      short loc_18000E976
0x18000e954  mov     edx, 0D5h
0x18000e959  lea     r9, [rsp+328h+Url]
0x18000e961  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e968  mov     rcx, [rcx+10h]
0x18000e96c  call    WPP_SF_S
0x18000e971  jmp     short loc_18000E976
0x18000e973  mov     r14, rdi
0x18000e976  lea     rcx, [rsp+328h+Binding]
0x18000e97e  call    DavBindTheRpcHandle
0x18000e983  test    eax, eax
0x18000e985  jz      short loc_18000E9CA
0x18000e987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e98e  cmp     rcx, r13
0x18000e991  jz      short loc_18000E9B8
0x18000e993  test    byte ptr [rcx+1Ch], 1
0x18000e997  jz      short loc_18000E9B8
0x18000e999  mov     edx, 0D6h
0x18000e99e  mov     r9d, eax
0x18000e9a1  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e9a8  mov     rcx, [rcx+10h]
0x18000e9ac  call    WPP_SF_d
0x18000e9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b8  mov     ebx, 4C6h
  ... truncated ...
```
