# CHistFolder::_CleanUpHistory(_FILETIME,_FILETIME)

- ea: `0x18000679c`
- end: `0x180006c8a`
- name: `?_CleanUpHistory@CHistFolder@@IEAAJU_FILETIME@@0@Z`
- size: `1262`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800072f0`

## callees

- `0x180006140`
- `0x18000679c`
- `0x180006c90`
- `0x1800072f0`
- `0x180007fc0`
- `0x180009318`
- `0x180009930`
- `0x180009d18`
- `0x180078828`
- `0x180167a6c`
- `0x18026ad50`
- `0x180516f40`
- `0x180516fb0`
- `0x18054e310`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000681d`
- `KERNEL32!CompareFileTime` at `0x180006837`
- `KERNEL32!CompareFileTime` at `0x1800068c7`
- `KERNEL32!CompareFileTime` at `0x1800068d8`
- `KERNEL32!CompareFileTime` at `0x18000681d`
- `KERNEL32!CompareFileTime` at `0x180006837`
- `KERNEL32!CompareFileTime` at `0x1800068c7`
- `KERNEL32!CompareFileTime` at `0x1800068d8`
- `KERNEL32!FileTimeToSystemTime` at `0x180006af0`
- `KERNEL32!FileTimeToSystemTime` at `0x180006afe`
- `KERNEL32!FileTimeToSystemTime` at `0x180006af0`
- `KERNEL32!FileTimeToSystemTime` at `0x180006afe`
- `KERNEL32!LocalAlloc` at `0x18000698a`
- `KERNEL32!LocalAlloc` at `0x18000698a`
- `KERNEL32!LocalFree` at `0x180006a40`
- `KERNEL32!LocalFree` at `0x180006a40`
- `KERNEL32!GetLastError` at `0x180006bb1`
- `KERNEL32!GetLastError` at `0x180006bb1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180006b6c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180006b6c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180006b7e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x180006b7e`
- `WININET!DeleteUrlCacheContainerA` at `0x180006ba7`
- `WININET!DeleteUrlCacheContainerA` at `0x180006ba7`
- `WININET!FindCloseUrlCache` at `0x180006a4e`
- `WININET!FindCloseUrlCache` at `0x180006a4e`
- `WININET!FindNextUrlCacheEntryW` at `0x1800069e7`
- `WININET!FindNextUrlCacheEntryW` at `0x1800069e7`
- `WININET!FindFirstUrlCacheEntryW` at `0x1800069d4`
- `WININET!FindFirstUrlCacheEntryW` at `0x1800069d4`

## pseudocode

```c
__int64 __fastcall CHistFolder::_CleanUpHistory(CHistFolder *this, FILETIME a2, FILETIME a3)
{
  DWORD v3; // r14d
  signed int IntervalCache; // ebx
  bool v6; // zf
  int i; // eax
  __int64 v8; // r15
  __int64 v9; // r9
  const FILETIME *v10; // r12
  int j; // esi
  __int64 v12; // r13
  __int64 v13; // r14
  __int64 v14; // r13
  __int64 v15; // r12
  WCHAR *v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // r8
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  struct _INTERNET_CACHE_ENTRY_INFOW *v21; // rsi
  HANDLE FirstUrlCacheEntryW; // r14
  bool v23; // sf
  __int64 v24; // rsi
  unsigned __int16 v25; // r8
  char IsWin10TelemetryTypeAllowed; // al
  DWORD cbCacheEntryInfo; // [rsp+60h] [rbp-A0h] BYREF
  char v29[4]; // [rsp+64h] [rbp-9Ch] BYREF
  int v30; // [rsp+68h] [rbp-98h]
  FILETIME FileTime2; // [rsp+70h] [rbp-90h] BYREF
  FILETIME v32; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME v33; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  CHAR pszDst[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pwszDst[32]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szUrlSearchPattern[136]; // [rsp+100h] [rbp+0h] BYREF

  FileTime2 = a2;
  v3 = 0;
  cbCacheEntryInfo = 0;
  v32 = a3;
  IntervalCache = CHistFolder::_LoadIntervalCache(this);
  v6 = IntervalCache == 0;
  if ( IntervalCache < 0 )
  {
LABEL_64:
    if ( v6 && v3 )
      return 1;
    return (unsigned int)IntervalCache;
  }
  for ( i = 0; ; i = v30 + 1 )
  {
    v30 = i;
    if ( i >= *((_DWORD *)this + 21) )
    {
LABEL_63:
      v6 = IntervalCache == 0;
      goto LABEL_64;
    }
    v8 = 60LL * i;
    if ( CompareFileTime((const FILETIME *)(v8 + *((_QWORD *)this + 11) + 8LL), &FileTime2) >= 0
      && CompareFileTime((const FILETIME *)(v8 + *((_QWORD *)this + 11)), &v32) < 0 )
    {
      break;
    }
    v24 = v8 + *((_QWORD *)this + 11);
    SystemTime = 0;
    v33 = 0;
    if ( *(_WORD *)(v24 + 58) )
      StringCchPrintfA(v29, 3u, "%02lu", *(unsigned __int16 *)(v24 + 58));
    else
      v29[0] = 0;
    v3 = 1;
    cbCacheEntryInfo = 1;
    FileTimeToSystemTime((const FILETIME *)v24, &SystemTime);
    FileTimeToSystemTime((const FILETIME *)(v24 + 8), &v33);
    StringCchPrintfA(
      (char *)szUrlSearchPattern,
      0x104u,
      "%s%s%04lu%02lu%02lu%04lu%02lu%02lu",
      "MSHist",
      v29,
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      v33.wYear,
      v33.wMonth,
      v33.wDay);
    SHAnsiToUnicode((PCSTR)szUrlSearchPattern, pwszDst, 25);
    SHUnicodeToAnsi(pwszDst, pszDst, 25);
    if ( *(_WORD *)(v24 + 56) == 25444 )
      CHistFolder::_DeleteEntries(this, (const unsigned __int16 *)(v24 + 16), 0, 0);
    if ( DeleteUrlCacheContainerA(pszDst, 0) )
    {
      IntervalCache = 0;
      CHistFolder::_NotifyInterval(this, (struct _HSFINTERVAL *)v24, 16);
    }
    else
    {
      IntervalCache = GetLastError();
    }
    if ( `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::AlreadyChecked )
    {
      IsWin10TelemetryTypeAllowed = `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::IsOptedIn;
    }
    else
    {
      if ( IsWindowsVersionOrGreater(0xAu, 0, v25) )
        IsWin10TelemetryTypeAllowed = TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed();
      else
        IsWin10TelemetryTypeAllowed = TelemetryPermissionsDownlevel::IsLessThanWin10TelemetryTypeAllowed();
      `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
      `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::AlreadyChecked = 1;
    }
    if ( IsWin10TelemetryTypeAllowed && IEHistoryJournalInstance::s_lLock <= 0 )
      OnlineHistorySettings::IsDataStreamFeatureEnabled();
    if ( IntervalCache )
    {
      if ( IntervalCache > 0 )
        IntervalCache = (unsigned __int16)IntervalCache | 0x80070000;
      v23 = IntervalCache < 0;
LABEL_36:
      if ( v23 )
        goto LABEL_63;
    }
    else
    {
      IntervalCache = 0;
    }
LABEL_61:
    ;
  }
  v9 = *((_QWORD *)this + 11);
  v10 = (const FILETIME *)(v8 + v9);
  if ( (unsigned int)(*(_QWORD *)(v8 + v9 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)(v8 + v9) / 864000000000LL) != 1
    || !v9 )
  {
    goto LABEL_61;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= *((_DWORD *)this + 21) )
    {
      v3 = cbCacheEntryInfo;
      goto LABEL_61;
    }
    v12 = 60LL * j;
    v13 = v12 + *((_QWORD *)this + 11);
    if ( *(_WORD *)(v13 + 58) == 1
      && CompareFileTime((const FILETIME *)(v12 + *((_QWORD *)this + 11)), v10) <= 0
      && CompareFileTime(v10, (const FILETIME *)(v13 + 8)) < 0 )
    {
      v14 = *((_QWORD *)this + 11) + v12;
      if ( (unsigned int)(*(_QWORD *)(v14 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)v14 / 864000000000LL) == 7 )
        break;
    }
  }
  v15 = *((_QWORD *)this + 11);
  v16 = szUrlSearchPattern;
  v17 = 2147483646;
  cbCacheEntryInfo = 0;
  v18 = (WCHAR *)(v8 + v15 + 16);
  v19 = 65;
  do
  {
    if ( !v17 )
      break;
    if ( !*v18 )
      break;
    *v16++ = *v18++;
    --v17;
    --v19;
  }
  while ( v19 );
  v20 = v16 - 1;
  if ( v19 )
    v20 = v16;
  *v20 = 0;
  v21 = (struct _INTERNET_CACHE_ENTRY_INFOW *)LocalAlloc(0x40u, 0x1000u);
  if ( v21 )
  {
    FirstUrlCacheEntryW = 0;
    IntervalCache = CHistFolder::_ValidateIntervalCache(this, 0);
    if ( IntervalCache >= 0 )
    {
      while ( IntervalCache >= 0 )
      {
        cbCacheEntryInfo = 4096;
        if ( FirstUrlCacheEntryW )
        {
          if ( !FindNextUrlCacheEntryW(FirstUrlCacheEntryW, v21, &cbCacheEntryInfo) )
          {
            IntervalCache = 0;
            break;
          }
        }
        else
        {
          FirstUrlCacheEntryW = FindFirstUrlCacheEntryW(szUrlSearchPattern, v21, &cbCacheEntryInfo);
          if ( !FirstUrlCacheEntryW )
            break;
        }
        if ( (v21->CacheEntryType & 0x200000) != 0 && (unsigned int)FilterPrefix(v21, v8 + v15 + 16) )
          IntervalCache = CHistFolder::_WriteHistory(
                            this,
                            v21->lpszSourceUrlName,
                            v21->ExpireTime,
                            v21->LastModifiedTime,
                            0,
                            0);
      }
    }
    LocalFree(v21);
    if ( FirstUrlCacheEntryW )
      FindCloseUrlCache(FirstUrlCacheEntryW);
    if ( IntervalCache >= 0 )
    {
      cbCacheEntryInfo = 1;
      v3 = 1;
      CHistFolder::_NotifyInterval(this, (struct _HSFINTERVAL *)v14, 4096);
      IntervalCache = CHistFolder::_DeleteInterval(this, (struct _HSFINTERVAL *)(v8 + *((_QWORD *)this + 11)), 1);
      v23 = IntervalCache < 0;
      goto LABEL_36;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)IntervalCache;
}

```

## disassembly

```asm
0x18000679c  mov     [rsp-8+arg_18], rbx
0x1800067a1  push    rbp
0x1800067a2  push    rsi
0x1800067a3  push    rdi
0x1800067a4  push    r12
0x1800067a6  push    r13
0x1800067a8  push    r14
0x1800067aa  push    r15
0x1800067ac  lea     rbp, [rsp-120h]
0x1800067b4  sub     rsp, 220h
0x1800067bb  mov     rax, cs:__security_cookie
0x1800067c2  xor     rax, rsp
0x1800067c5  mov     [rbp+150h+var_40], rax
0x1800067cc  xor     r13d, r13d
0x1800067cf  mov     qword ptr [rsp+250h+FileTime2.dwLowDateTime], rdx
0x1800067d4  mov     r14d, r13d
0x1800067d7  mov     [rsp+250h+cbCacheEntryInfo], r13d
0x1800067dc  mov     rdi, rcx
0x1800067df  mov     qword ptr [rsp+250h+var_1D8.dwLowDateTime], r8
0x1800067e4  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x1800067e9  mov     ebx, eax
0x1800067eb  lea     eax, [r13+1]
0x1800067ef  test    ebx, ebx
0x1800067f1  js      loc_180006C56
0x1800067f7  mov     eax, r13d
0x1800067fa  mov     [rsp+250h+var_1E8], eax
0x1800067fe  cmp     eax, [rdi+54h]
0x180006801  jge     loc_180006C4F
0x180006807  mov     rcx, [rdi+58h]
0x18000680b  lea     rdx, [rsp+250h+FileTime2]; lpFileTime2
0x180006810  cdqe
0x180006812  add     rcx, 8
0x180006816  imul    r15, rax, 3Ch ; '<'
0x18000681a  add     rcx, r15; lpFileTime1
0x18000681d  call    cs:__imp_CompareFileTime
0x180006823  test    eax, eax
0x180006825  js      loc_180006AA0
0x18000682b  mov     rcx, [rdi+58h]
0x18000682f  lea     rdx, [rsp+250h+var_1D8]; lpFileTime2
0x180006834  add     rcx, r15; lpFileTime1
0x180006837  call    cs:__imp_CompareFileTime
0x18000683d  test    eax, eax
0x18000683f  jns     loc_180006AA0
0x180006845  mov     r9, [rdi+58h]
0x180006849  mov     r10, 0C92A69C000h
0x180006853  lea     r12, [r15+r9]
0x180006857  mov     ecx, [r12+8]
0x18000685c  mov     eax, [r12+0Ch]
0x180006861  shl     rax, 20h
0x180006865  or      rax, rcx
0x180006868  mov     ecx, [r12]
0x18000686c  cqo
0x18000686e  idiv    r10
0x180006871  mov     r8, rax
0x180006874  mov     eax, [r12+4]
0x180006879  shl     rax, 20h
0x18000687d  or      rax, rcx
0x180006880  cqo
0x180006882  idiv    r10
0x180006885  sub     r8d, eax
0x180006888  cmp     r8d, 1
0x18000688c  jnz     loc_180006C3D
0x180006892  test    r9, r9
0x180006895  jz      loc_180006C3D
0x18000689b  mov     esi, r13d
0x18000689e  cmp     esi, [rdi+54h]
0x1800068a1  jge     loc_180006C35
0x1800068a7  mov     r14, [rdi+58h]
0x1800068ab  movsxd  rax, esi
0x1800068ae  imul    r13, rax, 3Ch ; '<'
0x1800068b2  mov     eax, 1
0x1800068b7  add     r14, r13
0x1800068ba  cmp     [r14+3Ah], ax
0x1800068bf  jnz     short loc_180006924
0x1800068c1  mov     rdx, r12; lpFileTime2
0x1800068c4  mov     rcx, r14; lpFileTime1
0x1800068c7  call    cs:__imp_CompareFileTime
0x1800068cd  test    eax, eax
0x1800068cf  jg      short loc_180006924
0x1800068d1  lea     rdx, [r14+8]; lpFileTime2
0x1800068d5  mov     rcx, r12; lpFileTime1
0x1800068d8  call    cs:__imp_CompareFileTime
0x1800068de  test    eax, eax
0x1800068e0  jns     short loc_180006924
0x1800068e2  add     r13, [rdi+58h]
0x1800068e6  mov     r9, 0C92A69C000h
0x1800068f0  mov     ecx, [r13+8]
0x1800068f4  mov     eax, [r13+0Ch]
0x1800068f8  shl     rax, 20h
0x1800068fc  or      rax, rcx
0x1800068ff  mov     ecx, [r13+0]
0x180006903  cqo
0x180006905  idiv    r9
0x180006908  mov     r8, rax
0x18000690b  mov     eax, [r13+4]
0x18000690f  shl     rax, 20h
0x180006913  or      rax, rcx
0x180006916  cqo
0x180006918  idiv    r9
0x18000691b  sub     r8d, eax
0x18000691e  cmp     r8d, 7
0x180006922  jz      short loc_18000692B
0x180006924  inc     esi
0x180006926  jmp     loc_18000689E
0x18000692b  mov     r12, [rdi+58h]
0x18000692f  lea     rax, [rbp+150h+szUrlSearchPattern]
0x180006933  xor     ebx, ebx
0x180006935  mov     ecx, 7FFFFFFEh
0x18000693a  mov     [rsp+250h+cbCacheEntryInfo], ebx
0x18000693e  lea     r8, [r12+10h]
0x180006943  add     r8, r15
0x180006946  lea     edx, [rbx+41h]
0x180006949  test    rcx, rcx
0x18000694c  jz      short loc_180006972
0x18000694e  movzx   r9d, word ptr [r8]
0x180006952  test    r9w, r9w
0x180006956  jz      short loc_180006972
0x180006958  mov     [rax], r9w
0x18000695c  add     r8, 2
0x180006960  mov     r9d, 1
0x180006966  add     rax, 2
0x18000696a  sub     rcx, r9
0x18000696d  sub     rdx, r9
0x180006970  jnz     short loc_180006949
0x180006972  test    rdx, rdx
0x180006975  lea     rcx, [rax-2]
0x180006979  mov     edx, 1000h; uBytes
0x18000697e  cmovnz  rcx, rax
0x180006982  mov     [rcx], bx
0x180006985  mov     ecx, 40h ; '@'; uFlags
0x18000698a  call    cs:__imp_LocalAlloc
0x180006990  mov     rsi, rax
0x180006993  test    rax, rax
0x180006996  jz      loc_180006C48
0x18000699c  xor     edx, edx; struct _FILETIME *
0x18000699e  mov     rcx, rdi; this
0x1800069a1  mov     r14, rbx
0x1800069a4  call    ?_ValidateIntervalCache@CHistFolder@@IEAAJPEBU_FILETIME@@@Z; CHistFolder::_ValidateIntervalCache(_FILETIME const *)
0x1800069a9  mov     ebx, eax
0x1800069ab  test    eax, eax
0x1800069ad  js      loc_180006A3D
0x1800069b3  test    ebx, ebx
0x1800069b5  js      loc_180006A3D
0x1800069bb  mov     [rsp+250h+cbCacheEntryInfo], 1000h
0x1800069c3  lea     r8, [rsp+250h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800069c8  mov     rdx, rsi; lpNextCacheEntryInfo
0x1800069cb  test    r14, r14
0x1800069ce  jnz     short loc_1800069E4
0x1800069d0  lea     rcx, [rbp+150h+szUrlSearchPattern]; lpszUrlSearchPattern
0x1800069d4  call    cs:__imp_FindFirstUrlCacheEntryW
0x1800069da  mov     r14, rax
0x1800069dd  test    rax, rax
0x1800069e0  jnz     short loc_1800069F3
0x1800069e2  jmp     short loc_180006A3D
0x1800069e4  mov     rcx, r14; hEnumHandle
0x1800069e7  call    cs:__imp_FindNextUrlCacheEntryW
0x1800069ed  xor     ecx, ecx
0x1800069ef  test    eax, eax
0x1800069f1  jz      short loc_180006A3B
0x1800069f3  test    dword ptr [rsi+18h], 200000h
0x1800069fa  jz      short loc_1800069B3
0x1800069fc  lea     rdx, [r12+10h]
0x180006a01  mov     rcx, rsi
0x180006a04  add     rdx, r15
0x180006a07  call    _FilterPrefix
0x180006a0c  xor     ecx, ecx
0x180006a0e  test    eax, eax
0x180006a10  jz      short loc_1800069B3
0x180006a12  mov     r9, [rsi+2Ch]; struct _FILETIME
0x180006a16  mov     r8, [rsi+34h]; struct _FILETIME
0x180006a1a  mov     rdx, [rsi+8]; unsigned __int16 *
0x180006a1e  mov     [rsp+250h+var_228], rcx; struct _ITEMIDLIST_ABSOLUTE **
0x180006a23  mov     [rsp+250h+var_230], ecx; int
0x180006a27  mov     rcx, rdi; this
0x180006a2a  call    ?_WriteHistory@CHistFolder@@IEAAJPEBGU_FILETIME@@1HPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CHistFolder::_WriteHistory(ushort const *,_FILETIME,_FILETIME,int,_ITEMIDLIST_ABSOLUTE * *)
0x180006a2f  mov     ebx, eax
0x180006a31  mov     eax, 1
0x180006a36  jmp     loc_1800069B3
0x180006a3b  mov     ebx, ecx
0x180006a3d  mov     rcx, rsi; hMem
0x180006a40  call    cs:__imp_LocalFree
0x180006a46  test    r14, r14
0x180006a49  jz      short loc_180006A54
0x180006a4b  mov     rcx, r14; hEnumHandle
0x180006a4e  call    cs:__imp_FindCloseUrlCache
0x180006a54  test    ebx, ebx
0x180006a56  js      loc_180006C5E
0x180006a5c  mov     ebx, 1
0x180006a61  mov     r8d, 1000h; int
0x180006a67  mov     rdx, r13; struct _HSFINTERVAL *
0x180006a6a  mov     [rsp+250h+cbCacheEntryInfo], ebx
0x180006a6e  mov     rcx, rdi; this
0x180006a71  mov     r14d, ebx
0x180006a74  call    ?_NotifyInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@J@Z; CHistFolder::_NotifyInterval(_HSFINTERVAL *,long)
0x180006a79  mov     rdx, [rdi+58h]
0x180006a7d  mov     r8b, bl; bool
0x180006a80  add     rdx, r15; struct _HSFINTERVAL *
0x180006a83  mov     rcx, rdi; this
0x180006a86  call    ?_DeleteInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@_N@Z; CHistFolder::_DeleteInterval(_HSFINTERVAL *,bool)
0x180006a8b  xor     r13d, r13d
0x180006a8e  mov     ebx, eax
0x180006a90  test    eax, eax
0x180006a92  jns     loc_180006C3D
0x180006a98  mov     rax, r14
0x180006a9b  jmp     loc_180006C54
0x180006aa0  mov     rsi, [rdi+58h]
0x180006aa4  xorps   xmm0, xmm0
0x180006aa7  add     rsi, r15
0x180006aaa  xorps   xmm1, xmm1
0x180006aad  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x180006ab1  movups  xmmword ptr [rbp+150h+var_1D0.wYear], xmm1
0x180006ab5  cmp     [rsi+3Ah], r13w
0x180006aba  jz      short loc_180006AD9
0x180006abc  movzx   r9d, word ptr [rsi+3Ah]
0x180006ac1  lea     r8, a02lu; "%02lu"
0x180006ac8  mov     edx, 3; unsigned __int64
0x180006acd  lea     rcx, [rsp+250h+var_1EC]; char *
0x180006ad2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006ad7  jmp     short loc_180006ADE
0x180006ad9  mov     [rsp+250h+var_1EC], r13b
0x180006ade  mov     r14d, 1
0x180006ae4  lea     rdx, [rbp+150h+SystemTime]; lpSystemTime
0x180006ae8  mov     rcx, rsi; lpFileTime
0x180006aeb  mov     [rsp+250h+cbCacheEntryInfo], r14d
0x180006af0  call    cs:__imp_FileTimeToSystemTime
0x180006af6  lea     rcx, [rsi+8]; lpFileTime
0x180006afa  lea     rdx, [rbp+150h+var_1D0]; lpSystemTime
0x180006afe  call    cs:__imp_FileTimeToSystemTime
0x180006b04  movzx   eax, [rbp+150h+var_1D0.wDay]
0x180006b08  movzx   ecx, [rbp+150h+var_1D0.wMonth]
0x180006b0c  movzx   edx, [rbp+150h+var_1D0.wYear]
0x180006b10  movzx   r8d, [rbp+150h+SystemTime.wDay]
0x180006b15  movzx   r9d, [rbp+150h+SystemTime.wMonth]
0x180006b1a  movzx   r10d, [rbp+150h+SystemTime.wYear]
0x180006b1f  mov     [rsp+250h+var_200], eax
0x180006b23  lea     rax, [rsp+250h+var_1EC]
0x180006b28  mov     [rsp+250h+var_208], ecx
0x180006b2c  lea     rcx, [rbp+150h+szUrlSearchPattern]; char *
0x180006b30  mov     [rsp+250h+var_210], edx
0x180006b34  mov     edx, 104h; unsigned __int64
0x180006b39  mov     [rsp+250h+var_218], r8d
0x180006b3e  lea     r8, aSS04lu02lu02lu; "%s%s%04lu%02lu%02lu%04lu%02lu%02lu"
0x180006b45  mov     [rsp+250h+var_220], r9d
0x180006b4a  lea     r9, String2; "MSHist"
0x180006b51  mov     dword ptr [rsp+250h+var_228], r10d
0x180006b56  mov     qword ptr [rsp+250h+var_230], rax
0x180006b5b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006b60  lea     r8d, [r14+18h]; cwchBuf
0x180006b64  lea     rdx, [rbp+150h+pwszDst]; pwszDst
0x180006b68  lea     rcx, [rbp+150h+szUrlSearchPattern]; pszSrc
0x180006b6c  call    cs:__imp_SHAnsiToUnicode
0x180006b72  lea     r8d, [r14+18h]; cchBuf
0x180006b76  lea     rdx, [rbp+150h+pszDst]; pszDst
0x180006b7a  lea     rcx, [rbp+150h+pwszDst]; pwszSrc
0x180006b7e  call    cs:__imp_SHUnicodeToAnsi
0x180006b84  mov     eax, 6364h
0x180006b89  cmp     [rsi+38h], ax
0x180006b8d  jnz     short loc_180006BA1
0x180006b8f  lea     rdx, [rsi+10h]; unsigned __int16 *
0x180006b93  xor     r9d, r9d; void *
0x180006b96  xor     r8d, r8d; int (*)(struct _INTERNET_CACHE_ENTRY_INFOW *, void *)
0x180006b99  mov     rcx, rdi; this
0x180006b9c  call    ?_DeleteEntries@CHistFolder@@IEAAJPEBGP6AHPEAU_INTERNET_CACHE_ENTRY_INFOW@@PEAX@Z2@Z; CHistFolder::_DeleteEntries(ushort const *,int (*)(_INTERNET_CACHE_ENTRY_INFOW *,void *),void *)
0x180006ba1  xor     edx, edx; dwOptions
0x180006ba3  lea     rcx, [rbp+150h+pszDst]; Name
0x180006ba7  call    cs:__imp_DeleteUrlCacheContainerA
0x180006bad  test    eax, eax
0x180006baf  jnz     short loc_180006BBB
0x180006bb1  call    cs:__imp_GetLastError
0x180006bb7  mov     ebx, eax
0x180006bb9  jmp     short loc_180006BCF
0x180006bbb  mov     r8d, 10h; int
0x180006bc1  mov     rdx, rsi; struct _HSFINTERVAL *
0x180006bc4  mov     rcx, rdi; this
0x180006bc7  mov     ebx, r13d
0x180006bca  call    ?_NotifyInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@J@Z; CHistFolder::_NotifyInterval(_HSFINTERVAL *,long)
0x180006bcf  cmp     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, r13b; bool `TelemetryPermissionsDownlevel::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x180006bd6  jnz     short loc_180006C01
0x180006bd8  xor     edx, edx; unsigned __int16
0x180006bda  lea     ecx, [rdx+0Ah]; unsigned __int16
0x180006bdd  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180006be2  test    al, al
0x180006be4  jz      short loc_180006BED
0x180006be6  call    ?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z; TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)
0x180006beb  jmp     short loc_180006BF2
0x180006bed  call    ?IsLessThanWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z; TelemetryPermissionsDownlevel::IsLessThanWin10TelemetryTypeAllowed(TelemetryType)
0x180006bf2  mov     cs:?IsOptedIn@?1??IsOptedIntoGeneral@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, al; bool `TelemetryPermissionsDownlevel::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x180006bf8  mov     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, r14b; bool `TelemetryPermissionsDownlevel::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x180006bff  jmp     short loc_180006C07
0x180006c01  mov     al, cs:?IsOptedIn@?1??IsOptedIntoGeneral@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA; bool `TelemetryPermissionsDownlevel::IsOptedIntoGeneral(bool)'::`2'::IsOptedIn
0x180006c07  test    al, al
0x180006c09  jz      short loc_180006C1A
0x180006c0b  mov     eax, cs:?s_lLock@IEHistoryJournalInstance@@0JC; long volatile IEHistoryJournalInstance::s_lLock
0x180006c11  test    eax, eax
0x180006c13  jg      short loc_180006C1A
0x180006c15  call    ?IsDataStreamFeatureEnabled@OnlineHistorySettings@@SA_NXZ; OnlineHistorySettings::IsDataStreamFeatureEnabled(void)
0x180006c1a  test    ebx, ebx
0x180006c1c  jnz     short loc_180006C23
0x180006c1e  mov     ebx, r13d
0x180006c21  jmp     short loc_180006C3D
  ... truncated ...
```
