# CHistFolder::_CleanUpHistory(_FILETIME,_FILETIME)

- ea: `0x18000d928`
- end: `0x18000de71`
- name: `?_CleanUpHistory@CHistFolder@@IEAAJU_FILETIME@@0@Z`
- size: `1353`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e550`

## callees

- `0x18000d260`
- `0x18000d928`
- `0x18000de78`
- `0x18000e550`
- `0x18000f2a0`
- `0x18001071c`
- `0x1800110fc`
- `0x180011528`
- `0x18007e4ec`
- `0x180178dcc`
- `0x18028b358`
- `0x180557f68`
- `0x180557fe8`
- `0x180591f80`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000d9a9`
- `KERNEL32!CompareFileTime` at `0x18000d9c9`
- `KERNEL32!CompareFileTime` at `0x18000da5f`
- `KERNEL32!CompareFileTime` at `0x18000da76`
- `KERNEL32!CompareFileTime` at `0x18000d9a9`
- `KERNEL32!CompareFileTime` at `0x18000d9c9`
- `KERNEL32!CompareFileTime` at `0x18000da5f`
- `KERNEL32!CompareFileTime` at `0x18000da76`
- `KERNEL32!FileTimeToSystemTime` at `0x18000dcb2`
- `KERNEL32!FileTimeToSystemTime` at `0x18000dcc6`
- `KERNEL32!FileTimeToSystemTime` at `0x18000dcb2`
- `KERNEL32!FileTimeToSystemTime` at `0x18000dcc6`
- `KERNEL32!LocalAlloc` at `0x18000db2e`
- `KERNEL32!LocalAlloc` at `0x18000db2e`
- `KERNEL32!LocalFree` at `0x18000dbf6`
- `KERNEL32!LocalFree` at `0x18000dbf6`
- `KERNEL32!GetLastError` at `0x18000dd91`
- `KERNEL32!GetLastError` at `0x18000dd91`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000dd3a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000dd3a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000dd52`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000dd52`
- `WININET!DeleteUrlCacheContainerA` at `0x18000dd81`
- `WININET!DeleteUrlCacheContainerA` at `0x18000dd81`
- `WININET!FindCloseUrlCache` at `0x18000dc0a`
- `WININET!FindCloseUrlCache` at `0x18000dc0a`
- `WININET!FindNextUrlCacheEntryW` at `0x18000db97`
- `WININET!FindNextUrlCacheEntryW` at `0x18000db97`
- `WININET!FindFirstUrlCacheEntryW` at `0x18000db7e`
- `WININET!FindFirstUrlCacheEntryW` at `0x18000db7e`

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
0x18000d928  mov     [rsp-8+arg_18], rbx
0x18000d92d  push    rbp
0x18000d92e  push    rsi
0x18000d92f  push    rdi
0x18000d930  push    r12
0x18000d932  push    r13
0x18000d934  push    r14
0x18000d936  push    r15
0x18000d938  lea     rbp, [rsp-120h]
0x18000d940  sub     rsp, 220h
0x18000d947  mov     rax, cs:__security_cookie
0x18000d94e  xor     rax, rsp
0x18000d951  mov     [rbp+150h+var_40], rax
0x18000d958  xor     r13d, r13d
0x18000d95b  mov     qword ptr [rsp+250h+FileTime2.dwLowDateTime], rdx
0x18000d960  mov     r14d, r13d
0x18000d963  mov     [rsp+250h+cbCacheEntryInfo], r13d
0x18000d968  mov     rdi, rcx
0x18000d96b  mov     qword ptr [rsp+250h+var_1D8.dwLowDateTime], r8
0x18000d970  call    ?_LoadIntervalCache@CHistFolder@@IEAAJXZ; CHistFolder::_LoadIntervalCache(void)
0x18000d975  mov     ebx, eax
0x18000d977  lea     eax, [r13+1]
0x18000d97b  test    ebx, ebx
0x18000d97d  js      loc_18000DE3C
0x18000d983  mov     eax, r13d
0x18000d986  mov     [rsp+250h+var_1E8], eax
0x18000d98a  cmp     eax, [rdi+54h]
0x18000d98d  jge     loc_18000DE35
0x18000d993  mov     rcx, [rdi+58h]
0x18000d997  lea     rdx, [rsp+250h+FileTime2]; lpFileTime2
0x18000d99c  cdqe
0x18000d99e  add     rcx, 8
0x18000d9a2  imul    r15, rax, 3Ch ; '<'
0x18000d9a6  add     rcx, r15; lpFileTime1
0x18000d9a9  call    cs:__imp_CompareFileTime
0x18000d9b0  nop     dword ptr [rax+rax+00h]
0x18000d9b5  test    eax, eax
0x18000d9b7  js      loc_18000DC62
0x18000d9bd  mov     rcx, [rdi+58h]
0x18000d9c1  lea     rdx, [rsp+250h+var_1D8]; lpFileTime2
0x18000d9c6  add     rcx, r15; lpFileTime1
0x18000d9c9  call    cs:__imp_CompareFileTime
0x18000d9d0  nop     dword ptr [rax+rax+00h]
0x18000d9d5  test    eax, eax
0x18000d9d7  jns     loc_18000DC62
0x18000d9dd  mov     r9, [rdi+58h]
0x18000d9e1  mov     r10, 0C92A69C000h
0x18000d9eb  lea     r12, [r15+r9]
0x18000d9ef  mov     ecx, [r12+8]
0x18000d9f4  mov     eax, [r12+0Ch]
0x18000d9f9  shl     rax, 20h
0x18000d9fd  or      rax, rcx
0x18000da00  mov     ecx, [r12]
0x18000da04  cqo
0x18000da06  idiv    r10
0x18000da09  mov     r8, rax
0x18000da0c  mov     eax, [r12+4]
0x18000da11  shl     rax, 20h
0x18000da15  or      rax, rcx
0x18000da18  cqo
0x18000da1a  idiv    r10
0x18000da1d  sub     r8d, eax
0x18000da20  cmp     r8d, 1
0x18000da24  jnz     loc_18000DE23
0x18000da2a  test    r9, r9
0x18000da2d  jz      loc_18000DE23
0x18000da33  mov     esi, r13d
0x18000da36  cmp     esi, [rdi+54h]
0x18000da39  jge     loc_18000DE1B
0x18000da3f  mov     r14, [rdi+58h]
0x18000da43  movsxd  rax, esi
0x18000da46  imul    r13, rax, 3Ch ; '<'
0x18000da4a  mov     eax, 1
0x18000da4f  add     r14, r13
0x18000da52  cmp     [r14+3Ah], ax
0x18000da57  jnz     short loc_18000DAC8
0x18000da59  mov     rdx, r12; lpFileTime2
0x18000da5c  mov     rcx, r14; lpFileTime1
0x18000da5f  call    cs:__imp_CompareFileTime
0x18000da66  nop     dword ptr [rax+rax+00h]
0x18000da6b  test    eax, eax
0x18000da6d  jg      short loc_18000DAC8
0x18000da6f  lea     rdx, [r14+8]; lpFileTime2
0x18000da73  mov     rcx, r12; lpFileTime1
0x18000da76  call    cs:__imp_CompareFileTime
0x18000da7d  nop     dword ptr [rax+rax+00h]
0x18000da82  test    eax, eax
0x18000da84  jns     short loc_18000DAC8
0x18000da86  add     r13, [rdi+58h]
0x18000da8a  mov     r9, 0C92A69C000h
0x18000da94  mov     ecx, [r13+8]
0x18000da98  mov     eax, [r13+0Ch]
0x18000da9c  shl     rax, 20h
0x18000daa0  or      rax, rcx
0x18000daa3  mov     ecx, [r13+0]
0x18000daa7  cqo
0x18000daa9  idiv    r9
0x18000daac  mov     r8, rax
0x18000daaf  mov     eax, [r13+4]
0x18000dab3  shl     rax, 20h
0x18000dab7  or      rax, rcx
0x18000daba  cqo
0x18000dabc  idiv    r9
0x18000dabf  sub     r8d, eax
0x18000dac2  cmp     r8d, 7
0x18000dac6  jz      short loc_18000DACF
0x18000dac8  inc     esi
0x18000daca  jmp     loc_18000DA36
0x18000dacf  mov     r12, [rdi+58h]
0x18000dad3  lea     rax, [rbp+150h+szUrlSearchPattern]
0x18000dad7  xor     ebx, ebx
0x18000dad9  mov     ecx, 7FFFFFFEh
0x18000dade  mov     [rsp+250h+cbCacheEntryInfo], ebx
0x18000dae2  lea     r8, [r12+10h]
0x18000dae7  add     r8, r15
0x18000daea  lea     edx, [rbx+41h]
0x18000daed  test    rcx, rcx
0x18000daf0  jz      short loc_18000DB16
0x18000daf2  movzx   r9d, word ptr [r8]
0x18000daf6  test    r9w, r9w
0x18000dafa  jz      short loc_18000DB16
0x18000dafc  mov     [rax], r9w
0x18000db00  add     r8, 2
0x18000db04  mov     r9d, 1
0x18000db0a  add     rax, 2
0x18000db0e  sub     rcx, r9
0x18000db11  sub     rdx, r9
0x18000db14  jnz     short loc_18000DAED
0x18000db16  test    rdx, rdx
0x18000db19  lea     rcx, [rax-2]
0x18000db1d  mov     edx, 1000h; uBytes
0x18000db22  cmovnz  rcx, rax
0x18000db26  mov     [rcx], bx
0x18000db29  mov     ecx, 40h ; '@'; uFlags
0x18000db2e  call    cs:__imp_LocalAlloc
0x18000db35  nop     dword ptr [rax+rax+00h]
0x18000db3a  mov     rsi, rax
0x18000db3d  test    rax, rax
0x18000db40  jz      loc_18000DE2E
0x18000db46  xor     edx, edx; struct _FILETIME *
0x18000db48  mov     rcx, rdi; this
0x18000db4b  mov     r14, rbx
0x18000db4e  call    ?_ValidateIntervalCache@CHistFolder@@IEAAJPEBU_FILETIME@@@Z; CHistFolder::_ValidateIntervalCache(_FILETIME const *)
0x18000db53  mov     ebx, eax
0x18000db55  test    eax, eax
0x18000db57  js      loc_18000DBF3
0x18000db5d  test    ebx, ebx
0x18000db5f  js      loc_18000DBF3
0x18000db65  mov     [rsp+250h+cbCacheEntryInfo], 1000h
0x18000db6d  lea     r8, [rsp+250h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x18000db72  mov     rdx, rsi; lpNextCacheEntryInfo
0x18000db75  test    r14, r14
0x18000db78  jnz     short loc_18000DB94
0x18000db7a  lea     rcx, [rbp+150h+szUrlSearchPattern]; lpszUrlSearchPattern
0x18000db7e  call    cs:__imp_FindFirstUrlCacheEntryW
0x18000db85  nop     dword ptr [rax+rax+00h]
0x18000db8a  mov     r14, rax
0x18000db8d  test    rax, rax
0x18000db90  jnz     short loc_18000DBA9
0x18000db92  jmp     short loc_18000DBF3
0x18000db94  mov     rcx, r14; hEnumHandle
0x18000db97  call    cs:__imp_FindNextUrlCacheEntryW
0x18000db9e  nop     dword ptr [rax+rax+00h]
0x18000dba3  xor     ecx, ecx
0x18000dba5  test    eax, eax
0x18000dba7  jz      short loc_18000DBF1
0x18000dba9  test    dword ptr [rsi+18h], 200000h
0x18000dbb0  jz      short loc_18000DB5D
0x18000dbb2  lea     rdx, [r12+10h]
0x18000dbb7  mov     rcx, rsi
0x18000dbba  add     rdx, r15
0x18000dbbd  call    _FilterPrefix
0x18000dbc2  xor     ecx, ecx
0x18000dbc4  test    eax, eax
0x18000dbc6  jz      short loc_18000DB5D
0x18000dbc8  mov     r9, [rsi+2Ch]; struct _FILETIME
0x18000dbcc  mov     r8, [rsi+34h]; struct _FILETIME
0x18000dbd0  mov     rdx, [rsi+8]; unsigned __int16 *
0x18000dbd4  mov     [rsp+250h+var_228], rcx; struct _ITEMIDLIST_ABSOLUTE **
0x18000dbd9  mov     [rsp+250h+var_230], ecx; int
0x18000dbdd  mov     rcx, rdi; this
0x18000dbe0  call    ?_WriteHistory@CHistFolder@@IEAAJPEBGU_FILETIME@@1HPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CHistFolder::_WriteHistory(ushort const *,_FILETIME,_FILETIME,int,_ITEMIDLIST_ABSOLUTE * *)
0x18000dbe5  mov     ebx, eax
0x18000dbe7  mov     eax, 1
0x18000dbec  jmp     loc_18000DB5D
0x18000dbf1  mov     ebx, ecx
0x18000dbf3  mov     rcx, rsi; hMem
0x18000dbf6  call    cs:__imp_LocalFree
0x18000dbfd  nop     dword ptr [rax+rax+00h]
0x18000dc02  test    r14, r14
0x18000dc05  jz      short loc_18000DC16
0x18000dc07  mov     rcx, r14; hEnumHandle
0x18000dc0a  call    cs:__imp_FindCloseUrlCache
0x18000dc11  nop     dword ptr [rax+rax+00h]
0x18000dc16  test    ebx, ebx
0x18000dc18  js      loc_18000DE44
0x18000dc1e  mov     ebx, 1
0x18000dc23  mov     r8d, 1000h; int
0x18000dc29  mov     rdx, r13; struct _HSFINTERVAL *
0x18000dc2c  mov     [rsp+250h+cbCacheEntryInfo], ebx
0x18000dc30  mov     rcx, rdi; this
0x18000dc33  mov     r14d, ebx
0x18000dc36  call    ?_NotifyInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@J@Z; CHistFolder::_NotifyInterval(_HSFINTERVAL *,long)
0x18000dc3b  mov     rdx, [rdi+58h]
0x18000dc3f  mov     r8b, bl; bool
0x18000dc42  add     rdx, r15; struct _HSFINTERVAL *
0x18000dc45  mov     rcx, rdi; this
0x18000dc48  call    ?_DeleteInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@_N@Z; CHistFolder::_DeleteInterval(_HSFINTERVAL *,bool)
0x18000dc4d  xor     r13d, r13d
0x18000dc50  mov     ebx, eax
0x18000dc52  test    eax, eax
0x18000dc54  jns     loc_18000DE23
0x18000dc5a  mov     rax, r14
0x18000dc5d  jmp     loc_18000DE3A
0x18000dc62  mov     rsi, [rdi+58h]
0x18000dc66  xorps   xmm0, xmm0
0x18000dc69  add     rsi, r15
0x18000dc6c  xorps   xmm1, xmm1
0x18000dc6f  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x18000dc73  movups  xmmword ptr [rbp+150h+var_1D0.wYear], xmm1
0x18000dc77  cmp     [rsi+3Ah], r13w
0x18000dc7c  jz      short loc_18000DC9B
0x18000dc7e  movzx   r9d, word ptr [rsi+3Ah]
0x18000dc83  lea     r8, a02lu; "%02lu"
0x18000dc8a  mov     edx, 3; unsigned __int64
0x18000dc8f  lea     rcx, [rsp+250h+var_1EC]; char *
0x18000dc94  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000dc99  jmp     short loc_18000DCA0
0x18000dc9b  mov     [rsp+250h+var_1EC], r13b
0x18000dca0  mov     r14d, 1
0x18000dca6  lea     rdx, [rbp+150h+SystemTime]; lpSystemTime
0x18000dcaa  mov     rcx, rsi; lpFileTime
0x18000dcad  mov     [rsp+250h+cbCacheEntryInfo], r14d
0x18000dcb2  call    cs:__imp_FileTimeToSystemTime
0x18000dcb9  nop     dword ptr [rax+rax+00h]
0x18000dcbe  lea     rcx, [rsi+8]; lpFileTime
0x18000dcc2  lea     rdx, [rbp+150h+var_1D0]; lpSystemTime
0x18000dcc6  call    cs:__imp_FileTimeToSystemTime
0x18000dccd  nop     dword ptr [rax+rax+00h]
0x18000dcd2  movzx   eax, [rbp+150h+var_1D0.wDay]
0x18000dcd6  movzx   ecx, [rbp+150h+var_1D0.wMonth]
0x18000dcda  movzx   edx, [rbp+150h+var_1D0.wYear]
0x18000dcde  movzx   r8d, [rbp+150h+SystemTime.wDay]
0x18000dce3  movzx   r9d, [rbp+150h+SystemTime.wMonth]
0x18000dce8  movzx   r10d, [rbp+150h+SystemTime.wYear]
0x18000dced  mov     [rsp+250h+var_200], eax
0x18000dcf1  lea     rax, [rsp+250h+var_1EC]
0x18000dcf6  mov     [rsp+250h+var_208], ecx
0x18000dcfa  lea     rcx, [rbp+150h+szUrlSearchPattern]; char *
0x18000dcfe  mov     [rsp+250h+var_210], edx
0x18000dd02  mov     edx, 104h; unsigned __int64
0x18000dd07  mov     [rsp+250h+var_218], r8d
0x18000dd0c  lea     r8, aSS04lu02lu02lu; "%s%s%04lu%02lu%02lu%04lu%02lu%02lu"
0x18000dd13  mov     [rsp+250h+var_220], r9d
0x18000dd18  lea     r9, aMshist; "MSHist"
0x18000dd1f  mov     dword ptr [rsp+250h+var_228], r10d
0x18000dd24  mov     qword ptr [rsp+250h+var_230], rax
0x18000dd29  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000dd2e  lea     r8d, [r14+18h]; cwchBuf
0x18000dd32  lea     rdx, [rbp+150h+pwszDst]; pwszDst
0x18000dd36  lea     rcx, [rbp+150h+szUrlSearchPattern]; pszSrc
0x18000dd3a  call    cs:__imp_SHAnsiToUnicode
0x18000dd41  nop     dword ptr [rax+rax+00h]
0x18000dd46  lea     r8d, [r14+18h]; cchBuf
0x18000dd4a  lea     rdx, [rbp+150h+pszDst]; pszDst
0x18000dd4e  lea     rcx, [rbp+150h+pwszDst]; pwszSrc
0x18000dd52  call    cs:__imp_SHUnicodeToAnsi
0x18000dd59  nop     dword ptr [rax+rax+00h]
0x18000dd5e  mov     eax, 6364h
0x18000dd63  cmp     [rsi+38h], ax
0x18000dd67  jnz     short loc_18000DD7B
0x18000dd69  lea     rdx, [rsi+10h]; unsigned __int16 *
0x18000dd6d  xor     r9d, r9d; void *
0x18000dd70  xor     r8d, r8d; int (*)(struct _INTERNET_CACHE_ENTRY_INFOW *, void *)
0x18000dd73  mov     rcx, rdi; this
0x18000dd76  call    ?_DeleteEntries@CHistFolder@@IEAAJPEBGP6AHPEAU_INTERNET_CACHE_ENTRY_INFOW@@PEAX@Z2@Z; CHistFolder::_DeleteEntries(ushort const *,int (*)(_INTERNET_CACHE_ENTRY_INFOW *,void *),void *)
0x18000dd7b  xor     edx, edx; dwOptions
0x18000dd7d  lea     rcx, [rbp+150h+pszDst]; Name
0x18000dd81  call    cs:__imp_DeleteUrlCacheContainerA
0x18000dd88  nop     dword ptr [rax+rax+00h]
0x18000dd8d  test    eax, eax
0x18000dd8f  jnz     short loc_18000DDA1
0x18000dd91  call    cs:__imp_GetLastError
0x18000dd98  nop     dword ptr [rax+rax+00h]
0x18000dd9d  mov     ebx, eax
0x18000dd9f  jmp     short loc_18000DDB5
0x18000dda1  mov     r8d, 10h; int
0x18000dda7  mov     rdx, rsi; struct _HSFINTERVAL *
0x18000ddaa  mov     rcx, rdi; this
0x18000ddad  mov     ebx, r13d
0x18000ddb0  call    ?_NotifyInterval@CHistFolder@@IEAAJPEAU_HSFINTERVAL@@J@Z; CHistFolder::_NotifyInterval(_HSFINTERVAL *,long)
0x18000ddb5  cmp     cs:?AlreadyChecked@?1??IsOptedIntoGeneral@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, r13b; bool `TelemetryPermissionsDownlevel::IsOptedIntoGeneral(bool)'::`2'::AlreadyChecked
0x18000ddbc  jnz     short loc_18000DDE7
0x18000ddbe  xor     edx, edx; unsigned __int16
0x18000ddc0  lea     ecx, [rdx+0Ah]; unsigned __int16
0x18000ddc3  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18000ddc8  test    al, al
0x18000ddca  jz      short loc_18000DDD3
0x18000ddcc  call    ?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z; TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)
0x18000ddd1  jmp     short loc_18000DDD8
  ... truncated ...
```
