# IsUrlFromInternetCache(char const *)

- ea: `0x1800696e0`
- end: `0x180069884`
- name: `?IsUrlFromInternetCache@@YAHPEBD@Z`
- size: `420`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069690`
- `0x180069a30`

## callees

- `0x180065d30`
- `0x180066e50`
- `0x1800696e0`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetShortPathNameA` at `0x18006980a`
- `KERNEL32!GetShortPathNameA` at `0x18006982a`
- `KERNEL32!GetShortPathNameA` at `0x18006980a`
- `KERNEL32!GetShortPathNameA` at `0x18006982a`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18006973b`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18006973b`
- `SHLWAPI!PathIsPrefixA` at `0x180069858`
- `SHLWAPI!PathIsPrefixA` at `0x180069858`
- `SHLWAPI!StrChrA` at `0x1800697ca`
- `SHLWAPI!StrChrA` at `0x1800697e5`
- `SHLWAPI!StrChrA` at `0x1800697ca`
- `SHLWAPI!StrChrA` at `0x1800697e5`

## pseudocode

```c
_BOOL8 __fastcall IsUrlFromInternetCache(const char *a1)
{
  unsigned int v2; // r8d
  PSTR v3; // rax
  PSTR v4; // rbx
  CHAR pszStart; // [rsp+20h] [rbp-668h] BYREF
  _BYTE v7[271]; // [rsp+21h] [rbp-667h] BYREF
  CHAR szLongPath[272]; // [rsp+130h] [rbp-558h] BYREF
  CHAR szShortPath[272]; // [rsp+240h] [rbp-448h] BYREF
  CHAR pszPrefix[272]; // [rsp+350h] [rbp-338h] BYREF
  WCHAR pszPath[264]; // [rsp+460h] [rbp-228h] BYREF

  memset_0(szLongPath, 0, 0x104u);
  memset_0(pszPath, 0, 0x208u);
  if ( !SHGetSpecialFolderPathW(0, pszPath, 32, 0) )
    return 0;
  if ( !pszPath[0] )
    return 0;
  if ( !ConvertPathToAnsiWithNoBestFitMatching(pszPath, szLongPath, 0x104u) )
    return 0;
  if ( !szLongPath[0] )
    return 0;
  pszStart = 0;
  memset_0(v7, 0, 0x103u);
  if ( (int)GetFilePathFromUrl(a1, &pszStart, v2) < 0 )
    return 0;
  if ( !pszStart )
    return 0;
  v3 = StrChrA(&pszStart, 0x5Cu);
  if ( !v3 )
    return 0;
  do
  {
    v4 = v3;
    v3 = StrChrA(v3 + 1, 0x5Cu);
  }
  while ( v3 );
  *v4 = 0;
  return GetShortPathNameA(&pszStart, szShortPath, 0x104u)
      && GetShortPathNameA(szLongPath, pszPrefix, 0x104u)
      && szShortPath[0]
      && pszPrefix[0]
      && PathIsPrefixA(pszPrefix, szShortPath);
}

```

## disassembly

```asm
0x1800696e0  push    rbx
0x1800696e2  sub     rsp, 680h
0x1800696e9  mov     rax, cs:__security_cookie
0x1800696f0  xor     rax, rsp
0x1800696f3  mov     [rsp+688h+var_18], rax
0x1800696fb  mov     rbx, rcx
0x1800696fe  xor     edx, edx; Val
0x180069700  lea     rcx, [rsp+688h+szLongPath]; void *
0x180069708  mov     r8d, 104h; Size
0x18006970e  call    memset_0
0x180069713  xor     edx, edx; Val
0x180069715  lea     rcx, [rsp+688h+pszPath]; void *
0x18006971d  mov     r8d, 208h; Size
0x180069723  call    memset_0
0x180069728  xor     r9d, r9d; fCreate
0x18006972b  lea     rdx, [rsp+688h+pszPath]; pszPath
0x180069733  mov     r8d, 20h ; ' '; csidl
0x180069739  xor     ecx, ecx; hwnd
0x18006973b  call    cs:__imp_SHGetSpecialFolderPathW
0x180069741  test    eax, eax
0x180069743  jz      loc_180069869
0x180069749  cmp     [rsp+688h+pszPath], 0
0x180069752  jz      loc_180069869
0x180069758  mov     r8d, 104h; unsigned int
0x18006975e  lea     rdx, [rsp+688h+szLongPath]; lpMultiByteStr
0x180069766  lea     rcx, [rsp+688h+pszPath]; lpszLongPath
0x18006976e  call    ?ConvertPathToAnsiWithNoBestFitMatching@@YA_NPEBGPEADK@Z; ConvertPathToAnsiWithNoBestFitMatching(ushort const *,char *,ulong)
0x180069773  test    al, al
0x180069775  jz      loc_180069869
0x18006977b  cmp     [rsp+688h+szLongPath], 0
0x180069783  jz      loc_180069869
0x180069789  xor     edx, edx; Val
0x18006978b  mov     [rsp+688h+pszStart], 0
0x180069790  mov     r8d, 103h; Size
0x180069796  lea     rcx, [rsp+688h+var_667]; void *
0x18006979b  call    memset_0
0x1800697a0  lea     rdx, [rsp+688h+pszStart]; char *
0x1800697a5  mov     rcx, rbx; char *
0x1800697a8  call    ?GetFilePathFromUrl@@YAJPEBDPEADK@Z; GetFilePathFromUrl(char const *,char *,ulong)
0x1800697ad  test    eax, eax
0x1800697af  js      loc_180069869
0x1800697b5  cmp     [rsp+688h+pszStart], 0
0x1800697ba  jz      loc_180069869
0x1800697c0  mov     edx, 5Ch ; '\'; wMatch
0x1800697c5  lea     rcx, [rsp+688h+pszStart]; pszStart
0x1800697ca  call    cs:__imp_StrChrA
0x1800697d0  test    rax, rax
0x1800697d3  jz      loc_180069869
0x1800697d9  mov     edx, 5Ch ; '\'; wMatch
0x1800697de  lea     rcx, [rax+1]; pszStart
0x1800697e2  mov     rbx, rax
0x1800697e5  call    cs:__imp_StrChrA
0x1800697eb  test    rax, rax
0x1800697ee  jnz     short loc_1800697D9
0x1800697f0  test    rbx, rbx
0x1800697f3  jz      short loc_180069869
0x1800697f5  mov     r8d, 104h; cchBuffer
0x1800697fb  mov     [rbx], al
0x1800697fd  lea     rdx, [rsp+688h+szShortPath]; lpszShortPath
0x180069805  lea     rcx, [rsp+688h+pszStart]; lpszLongPath
0x18006980a  call    cs:__imp_GetShortPathNameA
0x180069810  test    eax, eax
0x180069812  jz      short loc_180069869
0x180069814  mov     r8d, 104h; cchBuffer
0x18006981a  lea     rdx, [rsp+688h+pszPrefix]; lpszShortPath
0x180069822  lea     rcx, [rsp+688h+szLongPath]; lpszLongPath
0x18006982a  call    cs:__imp_GetShortPathNameA
0x180069830  test    eax, eax
0x180069832  jz      short loc_180069869
0x180069834  cmp     [rsp+688h+szShortPath], 0
0x18006983c  jz      short loc_180069869
0x18006983e  cmp     [rsp+688h+pszPrefix], 0
0x180069846  jz      short loc_180069869
0x180069848  lea     rdx, [rsp+688h+szShortPath]; pszPath
0x180069850  lea     rcx, [rsp+688h+pszPrefix]; pszPrefix
0x180069858  call    cs:__imp_PathIsPrefixA
0x18006985e  test    eax, eax
0x180069860  jz      short loc_180069869
0x180069862  mov     eax, 1
0x180069867  jmp     short loc_18006986B
0x180069869  xor     eax, eax
0x18006986b  mov     rcx, [rsp+688h+var_18]
0x180069873  xor     rcx, rsp; StackCookie
0x180069876  call    __security_check_cookie
0x18006987b  add     rsp, 680h
0x180069882  pop     rbx
0x180069883  retn
```
