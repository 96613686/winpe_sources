# CHistFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180004dc0`
- end: `0x1800054b4`
- name: `?Initialize@CHistFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `1780`
- prototype: `int(CHistFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004dc0`
- `0x180006140`
- `0x180011230`
- `0x18005bc78`
- `0x1800bab8c`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x180004f2b`
- `SHLWAPI!StrRetToBufW` at `0x180004f2b`
- `KERNEL32!CompareFileTime` at `0x180005332`
- `KERNEL32!CompareFileTime` at `0x180005369`
- `KERNEL32!CompareFileTime` at `0x180005429`
- `KERNEL32!CompareFileTime` at `0x180005332`
- `KERNEL32!CompareFileTime` at `0x180005369`
- `KERNEL32!CompareFileTime` at `0x180005429`
- `KERNEL32!GetLongPathNameW` at `0x1800053d5`
- `KERNEL32!GetLongPathNameW` at `0x1800053d5`
- `KERNEL32!SystemTimeToFileTime` at `0x18000521a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000531a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000521a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000531a`
- `KERNEL32!LocalAlloc` at `0x180005476`
- `KERNEL32!LocalAlloc` at `0x180005476`
- `KERNEL32!LocalFree` at `0x180005447`
- `KERNEL32!LocalFree` at `0x180005447`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180004f87`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1800053ee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180004f87`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x1800053ee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x180004e46`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x180004e46`
- `SHELL32!SHGetFolderPathW` at `0x180004e2b`
- `SHELL32!SHGetFolderPathW` at `0x180004e2b`
- `SHELL32!__imp_ILClone` at `0x180004fa4`
- `SHELL32!__imp_ILClone` at `0x180004fa4`
- `SHELL32!__imp_ILFree` at `0x180004dfe`
- `SHELL32!__imp_ILFree` at `0x180004dfe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180004e6f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180005390`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180004e6f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180005390`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180004f5a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180004f5a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000511d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000511d`

## pseudocode

```c
__int64 __fastcall CHistFolder::Initialize(LPITEMIDLIST *this, const ITEMIDLIST *a2)
{
  LPITEMIDLIST *v2; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  HRESULT v10; // r13d
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  HRESULT v14; // r12d
  LPCITEMIDLIST v15; // r12
  unsigned int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  LPITEMIDLIST v20; // rax
  _WORD *v22; // rax
  unsigned __int16 *v23; // rdx
  unsigned __int16 v24; // cx
  unsigned __int16 *v25; // rbx
  int v26; // ecx
  signed int IntervalCache; // edi
  int v28; // ecx
  CHistFolder *v29; // rcx
  const unsigned __int16 *v30; // r14
  unsigned __int16 v31; // ax
  bool v32; // zf
  __int64 v33; // rax
  int i; // edx
  unsigned int v35; // ecx
  LPITEMIDLIST v36; // rcx
  const unsigned __int16 *v37; // r15
  int j; // edi
  __int64 v39; // r14
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // rdi
  unsigned __int16 *v43; // rax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-C8h] BYREF
  void *v46; // [rsp+40h] [rbp-C0h]
  LPCITEMIDLIST pidl[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+60h] [rbp-A0h]
  __int16 v49; // [rsp+64h] [rbp-9Ch]
  __int16 v50; // [rsp+68h] [rbp-98h]
  __int16 v51; // [rsp+6Ch] [rbp-94h]
  __int16 v52; // [rsp+70h] [rbp-90h]
  __int16 v53; // [rsp+74h] [rbp-8Ch]
  __int16 v54; // [rsp+78h] [rbp-88h]
  __int16 v55; // [rsp+7Ch] [rbp-84h]
  __int16 v56; // [rsp+80h] [rbp-80h]
  __int16 v57; // [rsp+84h] [rbp-7Ch]
  __int16 v58; // [rsp+88h] [rbp-78h]
  __int16 v59; // [rsp+8Ch] [rbp-74h]
  __int16 v60; // [rsp+90h] [rbp-70h]
  __int16 v61; // [rsp+94h] [rbp-6Ch]
  __int16 v62; // [rsp+98h] [rbp-68h]
  __int16 v63; // [rsp+9Ch] [rbp-64h]
  STRRET pstr; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszBuf[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR psz2[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v2 = this - 5;
  ILFree(this[8]);
  if ( *((_DWORD *)this + 3) == 1 )
  {
    if ( SHGetFolderPathW(0, 34, 0, 0, psz2) < 0 )
      return 2147500037LL;
    PathRemoveBackslashW(psz2);
    if ( IEShimsDisableRedirection::SetEnabled )
      v9 = IEShimsDisableRedirection::SetEnabled(0, v6, v7, v8);
    else
      v9 = (unsigned int)ppv;
    pszBuf[0] = 0;
    v10 = CoInitializeEx(0, 6u);
    if ( v10 < 0 )
      v10 = CoInitializeEx(0, 4u);
    ppv = 0;
    ppidlLast = 0;
    v14 = SHBindToParent_0(a2, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v14 >= 0 )
    {
      v15 = ppidlLast;
      v46 = ppv;
      pidl[0] = ppidlLast;
      if ( IEShimsDisableRedirection::SetEnabled )
        v16 = IEShimsDisableRedirection::SetEnabled(0, v11, v12, v13);
      else
        v16 = (unsigned int)ppv;
      pszBuf[0] = 0;
      memset_0(&pstr, 0, sizeof(pstr));
      v14 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)v46 + 88LL))(
              v46,
              v15,
              0x8000,
              &pstr);
      if ( v14 >= 0 )
        v14 = StrRetToBufW(&pstr, pidl[0], pszBuf, 0x104u);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v16, v17, v18, v19);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v10 >= 0 )
      CoUninitialize();
    if ( IEShimsDisableRedirection::SetEnabled )
      IEShimsDisableRedirection::SetEnabled(v9, v11, v12, v13);
    if ( v14 < 0
      || StrCmpIW(pszBuf, psz2) && (!GetLongPathNameW(pszBuf, (LPWSTR)&pstr, 0x104u) || StrCmpIW((PCWSTR)&pstr, psz2)) )
    {
      return 2147500037LL;
    }
  }
  if ( !a2 )
    return (unsigned int)-2147024809;
  v20 = ILClone(a2);
  this[8] = v20;
  if ( !v20 )
    return (unsigned int)-2147024882;
  v22 = v2[13];
  v23 = 0;
  v24 = *v22;
  if ( *v22 )
  {
    do
    {
      v25 = v23;
      v23 = v22;
      v22 = (_WORD *)((char *)v22 + v24);
      v24 = *v22;
    }
    while ( *v22 );
  }
  else
  {
    v25 = 0;
  }
  v26 = *((_DWORD *)v2 + 13);
  if ( v26 == 1 )
  {
    v25 = v22;
  }
  else
  {
    v28 = v26 - 2;
    if ( v28 )
    {
      if ( v28 != 1 )
      {
        v2[14] = 0;
        return (unsigned int)-2147467259;
      }
    }
    else
    {
      v25 = v23;
    }
  }
  v2[14] = (LPITEMIDLIST)v25;
  if ( !v25 )
    return (unsigned int)-2147467259;
  IntervalCache = 0;
  while ( *v25 )
  {
    v29 = (CHistFolder *)v25[1];
    if ( (((_WORD)v29 - 25444) & 0xFFFA) != 0 || (_WORD)v29 == 25448 )
      goto LABEL_65;
    if ( (((_WORD)v29 - 25444) & 0xFFFA) != 0 || (v30 = v25 + 2, v25 == (unsigned __int16 *)-4LL) )
      v30 = &SrcStr;
    v31 = v25[1];
    if ( v31 != 25449 && v31 != 25444 )
    {
      if ( *((_DWORD *)v2 + 13) == 2 )
        *((_DWORD *)v2 + 13) = 3;
      CHistFolder::_CopyTSTRField(v29, (unsigned __int16 **)v2 + 8, v30);
      goto LABEL_65;
    }
    if ( *((_DWORD *)v2 + 13) == 1 )
      *((_DWORD *)v2 + 13) = 2;
    IntervalCache = CHistFolder::_LoadIntervalCache((DWORD *)v2);
    if ( IntervalCache < 0 )
      goto LABEL_65;
    v32 = v2[11] == 0;
    ppv = 0;
    ppidlLast = 0;
    if ( v32 )
      return (unsigned int)-2147467259;
    SHUnicodeToAnsi(v30, (PSTR)&pstr, 260);
    *(_OWORD *)pidl = 0;
    v33 = -1;
    do
      v32 = *((_BYTE *)&pstr.uType + ++v33) == 0;
    while ( !v32 );
    for ( i = 0; i < 16; ++i )
    {
      v35 = *((char *)&pstr + (int)v33 + i - 16) - 48;
      *(&v48 + i) = v35;
      if ( v35 > 9 )
        return (unsigned int)-2147467259;
    }
    LOWORD(pidl[0]) = v51 + 10 * (v50 + 10 * (v49 + 10 * v48));
    WORD1(pidl[0]) = v53 + 10 * v52;
    HIWORD(pidl[0]) = v55 + 10 * v54;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)pidl, (LPFILETIME)&ppv) )
      return (unsigned int)-2147467259;
    *(_OWORD *)pidl = 0;
    LOWORD(pidl[0]) = v59 + 10 * (v58 + 10 * (v57 + 10 * v56));
    WORD1(pidl[0]) = v61 + 10 * v60;
    HIWORD(pidl[0]) = v63 + 10 * v62;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)pidl, (LPFILETIME)&ppidlLast)
      || CompareFileTime((const FILETIME *)&ppv, (const FILETIME *)&ppidlLast) >= 0 )
    {
      return (unsigned int)-2147467259;
    }
    v37 = 0;
    for ( j = 0; j < *((_DWORD *)v2 + 21); ++j )
    {
      v39 = 20LL * j;
      v40 = (__int64)&v2[11][v39];
      if ( *(_WORD *)(v40 + 58) == 1
        && !CompareFileTime((const FILETIME *)v40, (const FILETIME *)&ppv)
        && !CompareFileTime((const FILETIME *)v2[11][v39 + 2].mkid.abID, (const FILETIME *)&ppidlLast) )
      {
        v37 = (USHORT *)((char *)&v2[11][v39 + 5].mkid.cb + 1);
        break;
      }
    }
    v36 = v2[7];
    if ( v36 )
    {
      LocalFree(v36);
      v2[7] = 0;
    }
    if ( v37 )
    {
      v41 = -1;
      do
        ++v41;
      while ( v37[v41] );
      v42 = (int)v41 + 1;
      v43 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v42);
      v2[7] = (LPITEMIDLIST)v43;
      if ( !v43 )
      {
        IntervalCache = -2147024882;
        goto LABEL_65;
      }
      StringCchCopyW(v43, v42, v37);
    }
    IntervalCache = 0;
LABEL_65:
    v25 = (unsigned __int16 *)((char *)v25 + *v25);
    if ( IntervalCache < 0 )
      return (unsigned int)IntervalCache;
  }
  if ( *((_DWORD *)v2 + 13) != 2 )
  {
    if ( *((_DWORD *)v2 + 13) != 3 )
      return (unsigned int)IntervalCache;
    if ( !v2[8] )
      IntervalCache = -2147467259;
  }
  if ( !v2[7] )
    return (unsigned int)-2147467259;
  return (unsigned int)IntervalCache;
}

```

## disassembly

```asm
0x180004dc0  mov     [rsp-8+arg_10], rbx
0x180004dc5  push    rbp
0x180004dc6  push    rsi
0x180004dc7  push    rdi
0x180004dc8  push    r12
0x180004dca  push    r13
0x180004dcc  push    r14
0x180004dce  push    r15
0x180004dd0  lea     rbp, [rsp-5E0h]
0x180004dd8  sub     rsp, 6E0h
0x180004ddf  mov     rax, cs:__security_cookie
0x180004de6  xor     rax, rsp
0x180004de9  mov     [rbp+610h+var_40], rax
0x180004df0  lea     rsi, [rcx-28h]
0x180004df4  mov     r15, rcx
0x180004df7  mov     rcx, [rsi+68h]; pidl
0x180004dfb  mov     r14, rdx
0x180004dfe  call    cs:__imp_ILFree
0x180004e04  xor     r12d, r12d
0x180004e07  cmp     dword ptr [r15+0Ch], 1
0x180004e0c  jnz     loc_180004F98
0x180004e12  lea     rax, [rbp+610h+psz2]
0x180004e19  xor     r9d, r9d; dwFlags
0x180004e1c  xor     r8d, r8d; hToken
0x180004e1f  mov     [rsp+710h+pszPath], rax; pszPath
0x180004e24  mov     edx, 22h ; '"'; csidl
0x180004e29  xor     ecx, ecx; hwnd
0x180004e2b  call    cs:__imp_SHGetFolderPathW
0x180004e31  test    eax, eax
0x180004e33  jns     short loc_180004E3F
0x180004e35  mov     eax, 80004005h
0x180004e3a  jmp     loc_180005043
0x180004e3f  lea     rcx, [rbp+610h+psz2]; pszPath
0x180004e46  call    cs:__imp_PathRemoveBackslashW
0x180004e4c  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180004e53  test    rax, rax
0x180004e56  jnz     loc_18000537B
0x180004e5c  mov     ebx, dword ptr [rsp+710h+ppv]
0x180004e60  mov     edx, 6; dwCoInit
0x180004e65  mov     [rbp+610h+pszBuf], r12w
0x180004e6d  xor     ecx, ecx; pvReserved
0x180004e6f  call    cs:__imp_CoInitializeEx
0x180004e75  mov     r13d, eax
0x180004e78  test    eax, eax
0x180004e7a  js      loc_180005389
0x180004e80  lea     r9, [rsp+710h+ppidlLast]; ppidlLast
0x180004e85  mov     [rsp+710h+ppv], r12
0x180004e8a  lea     r8, [rsp+710h+ppv]; ppv
0x180004e8f  mov     [rsp+710h+ppidlLast], r12
0x180004e94  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180004e9b  mov     rcx, r14; pidl
0x180004e9e  call    SHBindToParent_0
0x180004ea3  mov     r12d, eax
0x180004ea6  test    eax, eax
0x180004ea8  js      loc_180004F55
0x180004eae  mov     rax, [rsp+710h+ppv]
0x180004eb3  mov     r12, [rsp+710h+ppidlLast]
0x180004eb8  mov     [rsp+710h+var_6D0], rax
0x180004ebd  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180004ec4  mov     [rsp+710h+pidl], r12
0x180004ec9  test    rax, rax
0x180004ecc  jnz     loc_18000539E
0x180004ed2  mov     edi, dword ptr [rsp+710h+ppv]
0x180004ed6  xor     eax, eax
0x180004ed8  lea     rcx, [rbp+610h+pstr]; void *
0x180004edc  xor     edx, edx; Val
0x180004ede  mov     [rbp+610h+pszBuf], ax
0x180004ee5  mov     r8d, 110h; Size
0x180004eeb  call    memset_0
0x180004ef0  mov     rcx, [rsp+710h+var_6D0]
0x180004ef5  lea     r9, [rbp+610h+pstr]
0x180004ef9  mov     r8d, 8000h
0x180004eff  mov     rdx, r12
0x180004f02  mov     rax, [rcx]
0x180004f05  mov     rax, [rax+58h]
0x180004f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0e  mov     r12d, eax
0x180004f11  test    eax, eax
0x180004f13  js      short loc_180004F34
0x180004f15  mov     rdx, [rsp+710h+pidl]; pidl
0x180004f1a  lea     r8, [rbp+610h+pszBuf]; pszBuf
0x180004f21  mov     r9d, 104h; cchBuf
0x180004f27  lea     rcx, [rbp+610h+pstr]; pstr
0x180004f2b  call    cs:__imp_StrRetToBufW
0x180004f31  mov     r12d, eax
0x180004f34  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180004f3b  test    rax, rax
0x180004f3e  jnz     loc_1800053AC
0x180004f44  mov     rcx, [rsp+710h+ppv]
0x180004f49  mov     rax, [rcx]
0x180004f4c  mov     rax, [rax+10h]
0x180004f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f55  test    r13d, r13d
0x180004f58  js      short loc_180004F60
0x180004f5a  call    cs:__imp_CoUninitialize
0x180004f60  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180004f67  test    rax, rax
0x180004f6a  jnz     loc_1800053B8
0x180004f70  test    r12d, r12d
0x180004f73  js      loc_180004E35
0x180004f79  lea     rdx, [rbp+610h+psz2]; psz2
0x180004f80  lea     rcx, [rbp+610h+pszBuf]; psz1
0x180004f87  call    cs:__imp_StrCmpIW
0x180004f8d  test    eax, eax
0x180004f8f  jnz     loc_1800053C4
0x180004f95  xor     r12d, r12d
0x180004f98  test    r14, r14
0x180004f9b  jz      loc_18000518C
0x180004fa1  mov     rcx, r14; pidl
0x180004fa4  call    cs:__imp_ILClone
0x180004faa  mov     ecx, r12d
0x180004fad  mov     edx, 8007000Eh
0x180004fb2  test    rax, rax
0x180004fb5  mov     [r15+40h], rax
0x180004fb9  cmovz   ecx, edx
0x180004fbc  jz      loc_180005191
0x180004fc2  mov     rax, [rsi+68h]
0x180004fc6  mov     rdx, r12
0x180004fc9  movzx   ecx, word ptr [rax]
0x180004fcc  test    cx, cx
0x180004fcf  jz      loc_180005084
0x180004fd5  nop     word ptr [rax+rax+00000000h]
0x180004fe0  movzx   ecx, cx
0x180004fe3  mov     rbx, rdx
0x180004fe6  mov     rdx, rax
0x180004fe9  add     rax, rcx
0x180004fec  movzx   ecx, word ptr [rax]
0x180004fef  test    cx, cx
0x180004ff2  jnz     short loc_180004FE0
0x180004ff4  mov     ecx, [rsi+34h]
0x180004ff7  cmp     ecx, 1
0x180004ffa  jnz     short loc_18000506D
0x180004ffc  mov     rbx, rax
0x180004fff  mov     [rsi+70h], rbx
0x180005003  test    rbx, rbx
0x180005006  jz      loc_180005224
0x18000500c  mov     edi, r12d
0x18000500f  mov     edx, 0FFFAh
0x180005014  mov     r13d, 6364h
0x18000501a  mov     r8d, 6368h
0x180005020  mov     r9d, 6369h
0x180005026  cmp     word ptr [rbx], 0
0x18000502a  jnz     short loc_18000508C
0x18000502c  mov     ecx, [rsi+34h]
0x18000502f  sub     ecx, 2
0x180005032  jz      loc_18000517A
0x180005038  cmp     ecx, 1
0x18000503b  jz      loc_1800054A2
0x180005041  mov     eax, edi
0x180005043  mov     rcx, [rbp+610h+var_40]
0x18000504a  xor     rcx, rsp; StackCookie
0x18000504d  call    __security_check_cookie
0x180005052  mov     rbx, [rsp+710h+arg_10]
0x18000505a  add     rsp, 6E0h
0x180005061  pop     r15
0x180005063  pop     r14
0x180005065  pop     r13
0x180005067  pop     r12
0x180005069  pop     rdi
0x18000506a  pop     rsi
0x18000506b  pop     rbp
0x18000506c  retn
0x18000506d  sub     ecx, 2
0x180005070  jz      loc_18000526B
0x180005076  cmp     ecx, 1
0x180005079  jz      short loc_180004FFF
0x18000507b  mov     [rsi+70h], r12
0x18000507f  jmp     loc_180005224
0x180005084  mov     rbx, r12
0x180005087  jmp     loc_180004FF4
0x18000508c  movzx   ecx, word ptr [rbx+2]; this
0x180005090  movzx   eax, cx
0x180005093  sub     ax, r13w
0x180005097  test    dx, ax
0x18000509a  jnz     loc_180005258
0x1800050a0  cmp     cx, r8w
0x1800050a4  jz      loc_180005258
0x1800050aa  movzx   eax, cx
0x1800050ad  sub     ax, r13w
0x1800050b1  test    dx, ax
0x1800050b4  jnz     loc_180005401
0x1800050ba  cmp     cx, r8w
0x1800050be  jz      loc_180005401
0x1800050c4  lea     r14, [rbx+4]
0x1800050c8  test    r14, r14
0x1800050cb  jz      loc_180005401
0x1800050d1  movzx   eax, word ptr [rbx+2]
0x1800050d5  cmp     ax, r9w
0x1800050d9  jnz     loc_180005273
0x1800050df  cmp     dword ptr [rsi+34h], 1
0x1800050e3  jz      loc_18000540D
0x1800050e9  mov     rcx, rsi; this
0x1800050ec  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x1800050f1  mov     edi, eax
0x1800050f3  test    eax, eax
0x1800050f5  js      loc_180005247
0x1800050fb  cmp     qword ptr [rsi+58h], 0
0x180005100  mov     [rsp+710h+ppv], r12
0x180005105  mov     [rsp+710h+ppidlLast], r12
0x18000510a  jz      loc_180005224
0x180005110  mov     r8d, 104h; cchBuf
0x180005116  lea     rdx, [rbp+610h+pstr]; pszDst
0x18000511a  mov     rcx, r14; pwszSrc
0x18000511d  call    cs:__imp_SHUnicodeToAnsi
0x180005123  xorps   xmm0, xmm0
0x180005126  lea     rcx, [rbp+610h+pstr]
0x18000512a  movups  xmmword ptr [rsp+710h+pidl], xmm0
0x18000512f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005136  nop     word ptr [rax+rax+00000000h]
0x180005140  cmp     byte ptr [rcx+rax+1], 0
0x180005145  lea     rax, [rax+1]
0x180005149  jnz     short loc_180005140
0x18000514b  lea     r8d, [rax-10h]
0x18000514f  mov     edx, r12d
0x180005152  cmp     edx, 10h
0x180005155  jge     short loc_180005198
0x180005157  lea     eax, [r8+rdx]
0x18000515b  movsxd  rcx, eax
0x18000515e  movsxd  rax, edx
0x180005161  movsx   ecx, byte ptr [rbp+rcx+610h+pstr.uType]
0x180005166  add     ecx, 0FFFFFFD0h
0x180005169  mov     [rsp+rax*4+710h+var_6B0], ecx
0x18000516d  cmp     ecx, 9
0x180005170  ja      loc_180005224
0x180005176  inc     edx
0x180005178  jmp     short loc_180005152
0x18000517a  mov     eax, 80004005h
0x18000517f  cmp     qword ptr [rsi+38h], 0
0x180005184  cmovz   edi, eax
0x180005187  jmp     loc_180005041
0x18000518c  mov     ecx, 80070057h
0x180005191  mov     eax, ecx
0x180005193  jmp     loc_180005043
0x180005198  movzx   ecx, word ptr [rsp+710h+var_6B0]
0x18000519d  lea     rdx, [rsp+710h+ppv]; lpFileTime
0x1800051a2  movzx   eax, cx
0x1800051a5  shl     ax, 2
0x1800051a9  add     cx, ax
0x1800051ac  add     cx, cx
0x1800051af  add     cx, [rsp+710h+var_6AC]
0x1800051b4  movzx   eax, cx
0x1800051b7  shl     ax, 2
0x1800051bb  add     cx, ax
0x1800051be  add     cx, cx
0x1800051c1  add     cx, [rsp+710h+var_6A8]
0x1800051c6  movzx   eax, cx
0x1800051c9  shl     ax, 2
0x1800051cd  add     cx, ax
0x1800051d0  add     cx, cx
0x1800051d3  add     cx, [rsp+710h+var_6A4]
0x1800051d8  mov     word ptr [rsp+710h+pidl], cx
0x1800051dd  movzx   ecx, [rsp+710h+var_6A0]
0x1800051e2  movzx   eax, cx
0x1800051e5  shl     ax, 2
0x1800051e9  add     cx, ax
0x1800051ec  add     cx, cx
0x1800051ef  add     cx, [rsp+710h+var_69C]
0x1800051f4  mov     word ptr [rsp+710h+pidl+2], cx
0x1800051f9  movzx   ecx, [rsp+710h+var_698]
0x1800051fe  movzx   eax, cx
0x180005201  shl     ax, 2
0x180005205  add     cx, ax
0x180005208  add     cx, cx
0x18000520b  add     cx, [rsp+710h+var_694]
0x180005210  mov     word ptr [rsp+710h+pidl+6], cx
0x180005215  lea     rcx, [rsp+710h+pidl]; lpSystemTime
0x18000521a  call    cs:__imp_SystemTimeToFileTime
0x180005220  test    eax, eax
0x180005222  jnz     short loc_180005298
0x180005224  mov     edi, 80004005h
0x180005229  jmp     loc_180005041
0x18000522e  mov     rcx, [rsi+38h]; hMem
0x180005232  test    rcx, rcx
0x180005235  jnz     loc_180005447
0x18000523b  test    r15, r15
0x18000523e  jnz     loc_180005456
0x180005244  mov     edi, r12d
0x180005247  mov     edx, 0FFFAh
0x18000524c  mov     r8d, 6368h
0x180005252  mov     r9d, 6369h
0x180005258  movzx   eax, word ptr [rbx]
0x18000525b  add     rbx, rax
0x18000525e  test    edi, edi
0x180005260  jns     loc_180005026
0x180005266  jmp     loc_180005041
0x18000526b  mov     rbx, rdx
0x18000526e  jmp     loc_180004FFF
0x180005273  cmp     ax, r13w
0x180005277  jz      loc_1800050DF
0x18000527d  cmp     dword ptr [rsi+34h], 2
0x180005281  jnz     short loc_18000528A
0x180005283  mov     dword ptr [rsi+34h], 3
0x18000528a  lea     rdx, [rsi+40h]; unsigned __int16 **
0x18000528e  mov     r8, r14; unsigned __int16 *
0x180005291  call    ?_CopyTSTRField@CHistFolder@@IEAAJPEAPEAGPEBG@Z; CHistFolder::_CopyTSTRField(ushort * *,ushort const *)
0x180005296  jmp     short loc_180005247
0x180005298  movzx   ecx, [rbp+610h+var_690]
0x18000529c  lea     rdx, [rsp+710h+ppidlLast]; lpFileTime
0x1800052a1  movzx   eax, cx
0x1800052a4  xorps   xmm0, xmm0
  ... truncated ...
```
