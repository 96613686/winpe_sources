# CHistFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18000bdb0`
- end: `0x18000c518`
- name: `?Initialize@CHistFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `1896`
- prototype: `int(CHistFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bdb0`
- `0x18000d260`
- `0x1800144d0`
- `0x18005f84c`
- `0x1800c18bc`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x18000bf33`
- `SHLWAPI!StrRetToBufW` at `0x18000bf33`
- `KERNEL32!CompareFileTime` at `0x18000c35e`
- `KERNEL32!CompareFileTime` at `0x18000c3a3`
- `KERNEL32!CompareFileTime` at `0x18000c47b`
- `KERNEL32!CompareFileTime` at `0x18000c35e`
- `KERNEL32!CompareFileTime` at `0x18000c3a3`
- `KERNEL32!CompareFileTime` at `0x18000c47b`
- `KERNEL32!GetLongPathNameW` at `0x18000c41b`
- `KERNEL32!GetLongPathNameW` at `0x18000c41b`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c23a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c340`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c23a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c340`
- `KERNEL32!LocalAlloc` at `0x18000c4d4`
- `KERNEL32!LocalAlloc` at `0x18000c4d4`
- `KERNEL32!LocalFree` at `0x18000c49f`
- `KERNEL32!LocalFree` at `0x18000c49f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000bf9b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000c43a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000bf9b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000c43a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x18000be42`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x18000be42`
- `SHELL32!SHGetFolderPathW` at `0x18000be21`
- `SHELL32!SHGetFolderPathW` at `0x18000be21`
- `SHELL32!__imp_ILClone` at `0x18000bfbe`
- `SHELL32!__imp_ILClone` at `0x18000bfbe`
- `SHELL32!__imp_ILFree` at `0x18000bdee`
- `SHELL32!__imp_ILFree` at `0x18000bdee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000be71`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000c3d0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000be71`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000c3d0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18000bf68`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18000bf68`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000c13e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000c13e`

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
      v30 = &Default;
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
0x18000bdb0  mov     [rsp-8+arg_10], rbx
0x18000bdb5  push    rbp
0x18000bdb6  push    rsi
0x18000bdb7  push    rdi
0x18000bdb8  push    r12
0x18000bdba  push    r13
0x18000bdbc  push    r14
0x18000bdbe  push    r15
0x18000bdc0  lea     rbp, [rsp-5E0h]
0x18000bdc8  sub     rsp, 6E0h
0x18000bdcf  mov     rax, cs:__security_cookie
0x18000bdd6  xor     rax, rsp
0x18000bdd9  mov     [rbp+610h+var_40], rax
0x18000bde0  lea     rsi, [rcx-28h]
0x18000bde4  mov     r15, rcx
0x18000bde7  mov     rcx, [rsi+68h]; pidl
0x18000bdeb  mov     r14, rdx
0x18000bdee  call    cs:__imp_ILFree
0x18000bdf5  nop     dword ptr [rax+rax+00h]
0x18000bdfa  xor     r12d, r12d
0x18000bdfd  cmp     dword ptr [r15+0Ch], 1
0x18000be02  jnz     loc_18000BFB2
0x18000be08  lea     rax, [rbp+610h+psz2]
0x18000be0f  xor     r9d, r9d; dwFlags
0x18000be12  xor     r8d, r8d; hToken
0x18000be15  mov     [rsp+710h+pszPath], rax; pszPath
0x18000be1a  mov     edx, 22h ; '"'; csidl
0x18000be1f  xor     ecx, ecx; hwnd
0x18000be21  call    cs:__imp_SHGetFolderPathW
0x18000be28  nop     dword ptr [rax+rax+00h]
0x18000be2d  test    eax, eax
0x18000be2f  jns     short loc_18000BE3B
0x18000be31  mov     eax, 80004005h
0x18000be36  jmp     loc_18000C063
0x18000be3b  lea     rcx, [rbp+610h+psz2]; pszPath
0x18000be42  call    cs:__imp_PathRemoveBackslashW
0x18000be49  nop     dword ptr [rax+rax+00h]
0x18000be4e  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000be55  test    rax, rax
0x18000be58  jnz     loc_18000C3BB
0x18000be5e  mov     ebx, dword ptr [rsp+710h+ppv]
0x18000be62  mov     edx, 6; dwCoInit
0x18000be67  mov     [rbp+610h+pszBuf], r12w
0x18000be6f  xor     ecx, ecx; pvReserved
0x18000be71  call    cs:__imp_CoInitializeEx
0x18000be78  nop     dword ptr [rax+rax+00h]
0x18000be7d  mov     r13d, eax
0x18000be80  test    eax, eax
0x18000be82  js      loc_18000C3C9
0x18000be88  lea     r9, [rsp+710h+ppidlLast]; ppidlLast
0x18000be8d  mov     [rsp+710h+ppv], r12
0x18000be92  lea     r8, [rsp+710h+ppv]; ppv
0x18000be97  mov     [rsp+710h+ppidlLast], r12
0x18000be9c  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000bea3  mov     rcx, r14; pidl
0x18000bea6  call    SHBindToParent_0
0x18000beab  mov     r12d, eax
0x18000beae  test    eax, eax
0x18000beb0  js      loc_18000BF63
0x18000beb6  mov     rax, [rsp+710h+ppv]
0x18000bebb  mov     r12, [rsp+710h+ppidlLast]
0x18000bec0  mov     [rsp+710h+var_6D0], rax
0x18000bec5  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000becc  mov     [rsp+710h+pidl], r12
0x18000bed1  test    rax, rax
0x18000bed4  jnz     loc_18000C3E4
0x18000beda  mov     edi, dword ptr [rsp+710h+ppv]
0x18000bede  xor     eax, eax
0x18000bee0  lea     rcx, [rbp+610h+pstr]; void *
0x18000bee4  xor     edx, edx; Val
0x18000bee6  mov     [rbp+610h+pszBuf], ax
0x18000beed  mov     r8d, 110h; Size
0x18000bef3  call    memset_0
0x18000bef8  mov     rcx, [rsp+710h+var_6D0]
0x18000befd  lea     r9, [rbp+610h+pstr]
0x18000bf01  mov     r8d, 8000h
0x18000bf07  mov     rdx, r12
0x18000bf0a  mov     rax, [rcx]
0x18000bf0d  mov     rax, [rax+58h]
0x18000bf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf16  mov     r12d, eax
0x18000bf19  test    eax, eax
0x18000bf1b  js      short loc_18000BF42
0x18000bf1d  mov     rdx, [rsp+710h+pidl]; pidl
0x18000bf22  lea     r8, [rbp+610h+pszBuf]; pszBuf
0x18000bf29  mov     r9d, 104h; cchBuf
0x18000bf2f  lea     rcx, [rbp+610h+pstr]; pstr
0x18000bf33  call    cs:__imp_StrRetToBufW
0x18000bf3a  nop     dword ptr [rax+rax+00h]
0x18000bf3f  mov     r12d, eax
0x18000bf42  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000bf49  test    rax, rax
0x18000bf4c  jnz     loc_18000C3F2
0x18000bf52  mov     rcx, [rsp+710h+ppv]
0x18000bf57  mov     rax, [rcx]
0x18000bf5a  mov     rax, [rax+10h]
0x18000bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf63  test    r13d, r13d
0x18000bf66  js      short loc_18000BF74
0x18000bf68  call    cs:__imp_CoUninitialize
0x18000bf6f  nop     dword ptr [rax+rax+00h]
0x18000bf74  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000bf7b  test    rax, rax
0x18000bf7e  jnz     loc_18000C3FE
0x18000bf84  test    r12d, r12d
0x18000bf87  js      loc_18000BE31
0x18000bf8d  lea     rdx, [rbp+610h+psz2]; psz2
0x18000bf94  lea     rcx, [rbp+610h+pszBuf]; psz1
0x18000bf9b  call    cs:__imp_StrCmpIW
0x18000bfa2  nop     dword ptr [rax+rax+00h]
0x18000bfa7  test    eax, eax
0x18000bfa9  jnz     loc_18000C40A
0x18000bfaf  xor     r12d, r12d
0x18000bfb2  test    r14, r14
0x18000bfb5  jz      loc_18000C1AC
0x18000bfbb  mov     rcx, r14; pidl
0x18000bfbe  call    cs:__imp_ILClone
0x18000bfc5  nop     dword ptr [rax+rax+00h]
0x18000bfca  mov     ecx, r12d
0x18000bfcd  mov     edx, 8007000Eh
0x18000bfd2  test    rax, rax
0x18000bfd5  mov     [r15+40h], rax
0x18000bfd9  cmovz   ecx, edx
0x18000bfdc  jz      loc_18000C1B1
0x18000bfe2  mov     rax, [rsi+68h]
0x18000bfe6  mov     rdx, r12
0x18000bfe9  movzx   ecx, word ptr [rax]
0x18000bfec  test    cx, cx
0x18000bfef  jz      loc_18000C0A5
0x18000bff5  nop     word ptr [rax+rax+00000000h]
0x18000c000  movzx   ecx, cx
0x18000c003  mov     rbx, rdx
0x18000c006  mov     rdx, rax
0x18000c009  add     rax, rcx
0x18000c00c  movzx   ecx, word ptr [rax]
0x18000c00f  test    cx, cx
0x18000c012  jnz     short loc_18000C000
0x18000c014  mov     ecx, [rsi+34h]
0x18000c017  cmp     ecx, 1
0x18000c01a  jnz     short loc_18000C08E
0x18000c01c  mov     rbx, rax
0x18000c01f  mov     [rsi+70h], rbx
0x18000c023  test    rbx, rbx
0x18000c026  jz      loc_18000C24A
0x18000c02c  mov     edi, r12d
0x18000c02f  mov     edx, 0FFFAh
0x18000c034  mov     r13d, 6364h
0x18000c03a  mov     r8d, 6368h
0x18000c040  mov     r9d, 6369h
0x18000c046  cmp     word ptr [rbx], 0
0x18000c04a  jnz     short loc_18000C0AD
0x18000c04c  mov     ecx, [rsi+34h]
0x18000c04f  sub     ecx, 2
0x18000c052  jz      loc_18000C19A
0x18000c058  cmp     ecx, 1
0x18000c05b  jz      loc_18000C506
0x18000c061  mov     eax, edi
0x18000c063  mov     rcx, [rbp+610h+var_40]
0x18000c06a  xor     rcx, rsp; StackCookie
0x18000c06d  call    __security_check_cookie
0x18000c072  mov     rbx, [rsp+710h+arg_10]
0x18000c07a  add     rsp, 6E0h
0x18000c081  pop     r15
0x18000c083  pop     r14
0x18000c085  pop     r13
0x18000c087  pop     r12
0x18000c089  pop     rdi
0x18000c08a  pop     rsi
0x18000c08b  pop     rbp
0x18000c08c  retn
0x18000c08e  sub     ecx, 2
0x18000c091  jz      loc_18000C291
0x18000c097  cmp     ecx, 1
0x18000c09a  jz      short loc_18000C01F
0x18000c09c  mov     [rsi+70h], r12
0x18000c0a0  jmp     loc_18000C24A
0x18000c0a5  mov     rbx, r12
0x18000c0a8  jmp     loc_18000C014
0x18000c0ad  movzx   ecx, word ptr [rbx+2]; this
0x18000c0b1  movzx   eax, cx
0x18000c0b4  sub     ax, r13w
0x18000c0b8  test    dx, ax
0x18000c0bb  jnz     loc_18000C27E
0x18000c0c1  cmp     cx, r8w
0x18000c0c5  jz      loc_18000C27E
0x18000c0cb  movzx   eax, cx
0x18000c0ce  sub     ax, r13w
0x18000c0d2  test    dx, ax
0x18000c0d5  jnz     loc_18000C453
0x18000c0db  cmp     cx, r8w
0x18000c0df  jz      loc_18000C453
0x18000c0e5  lea     r14, [rbx+4]
0x18000c0e9  test    r14, r14
0x18000c0ec  jz      loc_18000C453
0x18000c0f2  movzx   eax, word ptr [rbx+2]
0x18000c0f6  cmp     ax, r9w
0x18000c0fa  jnz     loc_18000C299
0x18000c100  cmp     dword ptr [rsi+34h], 1
0x18000c104  jz      loc_18000C45F
0x18000c10a  mov     rcx, rsi; this
0x18000c10d  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x18000c112  mov     edi, eax
0x18000c114  test    eax, eax
0x18000c116  js      loc_18000C26D
0x18000c11c  cmp     qword ptr [rsi+58h], 0
0x18000c121  mov     [rsp+710h+ppv], r12
0x18000c126  mov     [rsp+710h+ppidlLast], r12
0x18000c12b  jz      loc_18000C24A
0x18000c131  mov     r8d, 104h; cchBuf
0x18000c137  lea     rdx, [rbp+610h+pstr]; pszDst
0x18000c13b  mov     rcx, r14; pwszSrc
0x18000c13e  call    cs:__imp_SHUnicodeToAnsi
0x18000c145  nop     dword ptr [rax+rax+00h]
0x18000c14a  xorps   xmm0, xmm0
0x18000c14d  lea     rcx, [rbp+610h+pstr]
0x18000c151  movups  xmmword ptr [rsp+710h+pidl], xmm0
0x18000c156  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c15d  nop     dword ptr [rax]
0x18000c160  cmp     byte ptr [rcx+rax+1], 0
0x18000c165  lea     rax, [rax+1]
0x18000c169  jnz     short loc_18000C160
0x18000c16b  lea     r8d, [rax-10h]
0x18000c16f  mov     edx, r12d
0x18000c172  cmp     edx, 10h
0x18000c175  jge     short loc_18000C1B8
0x18000c177  lea     eax, [r8+rdx]
0x18000c17b  movsxd  rcx, eax
0x18000c17e  movsxd  rax, edx
0x18000c181  movsx   ecx, byte ptr [rbp+rcx+610h+pstr.uType]
0x18000c186  add     ecx, 0FFFFFFD0h
0x18000c189  mov     [rsp+rax*4+710h+var_6B0], ecx
0x18000c18d  cmp     ecx, 9
0x18000c190  ja      loc_18000C24A
0x18000c196  inc     edx
0x18000c198  jmp     short loc_18000C172
0x18000c19a  mov     eax, 80004005h
0x18000c19f  cmp     qword ptr [rsi+38h], 0
0x18000c1a4  cmovz   edi, eax
0x18000c1a7  jmp     loc_18000C061
0x18000c1ac  mov     ecx, 80070057h
0x18000c1b1  mov     eax, ecx
0x18000c1b3  jmp     loc_18000C063
0x18000c1b8  movzx   ecx, word ptr [rsp+710h+var_6B0]
0x18000c1bd  lea     rdx, [rsp+710h+ppv]; lpFileTime
0x18000c1c2  movzx   eax, cx
0x18000c1c5  shl     ax, 2
0x18000c1c9  add     cx, ax
0x18000c1cc  add     cx, cx
0x18000c1cf  add     cx, [rsp+710h+var_6AC]
0x18000c1d4  movzx   eax, cx
0x18000c1d7  shl     ax, 2
0x18000c1db  add     cx, ax
0x18000c1de  add     cx, cx
0x18000c1e1  add     cx, [rsp+710h+var_6A8]
0x18000c1e6  movzx   eax, cx
0x18000c1e9  shl     ax, 2
0x18000c1ed  add     cx, ax
0x18000c1f0  add     cx, cx
0x18000c1f3  add     cx, [rsp+710h+var_6A4]
0x18000c1f8  mov     word ptr [rsp+710h+pidl], cx
0x18000c1fd  movzx   ecx, [rsp+710h+var_6A0]
0x18000c202  movzx   eax, cx
0x18000c205  shl     ax, 2
0x18000c209  add     cx, ax
0x18000c20c  add     cx, cx
0x18000c20f  add     cx, [rsp+710h+var_69C]
0x18000c214  mov     word ptr [rsp+710h+pidl+2], cx
0x18000c219  movzx   ecx, [rsp+710h+var_698]
0x18000c21e  movzx   eax, cx
0x18000c221  shl     ax, 2
0x18000c225  add     cx, ax
0x18000c228  add     cx, cx
0x18000c22b  add     cx, [rsp+710h+var_694]
0x18000c230  mov     word ptr [rsp+710h+pidl+6], cx
0x18000c235  lea     rcx, [rsp+710h+pidl]; lpSystemTime
0x18000c23a  call    cs:__imp_SystemTimeToFileTime
0x18000c241  nop     dword ptr [rax+rax+00h]
0x18000c246  test    eax, eax
0x18000c248  jnz     short loc_18000C2BE
0x18000c24a  mov     edi, 80004005h
0x18000c24f  jmp     loc_18000C061
0x18000c254  mov     rcx, [rsi+38h]; hMem
0x18000c258  test    rcx, rcx
0x18000c25b  jnz     loc_18000C49F
0x18000c261  test    r15, r15
0x18000c264  jnz     loc_18000C4B4
0x18000c26a  mov     edi, r12d
0x18000c26d  mov     edx, 0FFFAh
0x18000c272  mov     r8d, 6368h
0x18000c278  mov     r9d, 6369h
0x18000c27e  movzx   eax, word ptr [rbx]
0x18000c281  add     rbx, rax
0x18000c284  test    edi, edi
0x18000c286  jns     loc_18000C046
0x18000c28c  jmp     loc_18000C061
0x18000c291  mov     rbx, rdx
0x18000c294  jmp     loc_18000C01F
0x18000c299  cmp     ax, r13w
0x18000c29d  jz      loc_18000C100
0x18000c2a3  cmp     dword ptr [rsi+34h], 2
  ... truncated ...
```
