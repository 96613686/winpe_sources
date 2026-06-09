# UrlCreateEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort,ushort const *,ushort *,ulong,ulong)

- ea: `0x180021714`
- end: `0x1800217de`
- name: `?UrlCreateEx@@YAJPEBG0000G0PEAGKK@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, const unsigned __int16 *, LPWSTR lpszUrl, DWORD dwUrlLength, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d4c0`
- `0x18001f858`
- `0x1800207b8`
- `0x180020c9c`

## callees

- `0x18000958c`
- `0x180021714`

## import_xrefs

- `WININET!InternetCreateUrlW` at `0x1800217af`
- `WININET!InternetCreateUrlW` at `0x1800217af`

## pseudocode

```c
__int64 __fastcall UrlCreateEx(
        WCHAR *a1,
        WCHAR *a2,
        WCHAR *a3,
        WCHAR *a4,
        unsigned __int16 *a5,
        INTERNET_PORT a6,
        const unsigned __int16 *a7,
        LPWSTR lpszUrl,
        DWORD dwUrlLength,
        unsigned int a10)
{
  unsigned __int64 v10; // rdi
  unsigned int v11; // ebx
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+20h] [rbp-69h] BYREF

  v10 = dwUrlLength;
  v11 = -2147467259;
  UrlComponents.nPort = a6;
  *(_QWORD *)&UrlComponents.dwStructSize = 104;
  UrlComponents.lpszScheme = 0;
  UrlComponents.dwSchemeLength = 0;
  UrlComponents.nScheme = INTERNET_SCHEME_FTP;
  UrlComponents.lpszHostName = a1;
  UrlComponents.dwHostNameLength = 0;
  *(&UrlComponents.nPort + 1) = 0;
  if ( !a2 || (UrlComponents.lpszUserName = a2, !*a2) )
    UrlComponents.lpszUserName = 0;
  *(_QWORD *)&UrlComponents.dwUserNameLength = 0;
  if ( !a3 || (UrlComponents.lpszPassword = a3, !*a3) )
    UrlComponents.lpszPassword = 0;
  UrlComponents.lpszUrlPath = a4;
  *(_QWORD *)&UrlComponents.dwPasswordLength = 0;
  memset(&UrlComponents.dwUrlPathLength, 0, 24);
  if ( InternetCreateUrlW(&UrlComponents, a10 | 0x40002000, lpszUrl, &dwUrlLength) )
  {
    v11 = 0;
    if ( a5 )
      StringCchCatW(lpszUrl, v10, a5);
  }
  return v11;
}

```

## disassembly

```asm
0x180021714  push    rbp
0x180021716  push    rbx
0x180021717  push    rsi
0x180021718  push    rdi
0x180021719  lea     rbp, [rsp-0Fh]
0x18002171e  sub     rsp, 98h
0x180021725  movzx   eax, [rbp+27h+arg_28]
0x180021729  xor     esi, esi
0x18002172b  mov     edi, [rbp+27h+dwUrlLength]
0x18002172e  mov     ebx, 80004005h
0x180021733  mov     [rbp+27h+UrlComponents.nPort], ax
0x180021737  xor     eax, eax
0x180021739  mov     [rbp+27h+dwUrlLength], edi
0x18002173c  mov     qword ptr [rbp+27h+UrlComponents.dwStructSize], 68h ; 'h'
0x180021744  mov     [rbp+27h+UrlComponents.lpszScheme], rsi
0x180021748  mov     [rbp+27h+UrlComponents.dwSchemeLength], esi
0x18002174b  mov     [rbp+27h+UrlComponents.nScheme], 1
0x180021752  mov     [rbp+27h+UrlComponents.lpszHostName], rcx
0x180021756  mov     [rbp+27h+UrlComponents.dwHostNameLength], esi
0x180021759  mov     word ptr [rbp+27h+UrlComponents+26h], ax
0x18002175d  test    rdx, rdx
0x180021760  jz      short loc_18002176B
0x180021762  mov     [rbp+27h+UrlComponents.lpszUserName], rdx
0x180021766  cmp     [rdx], si
0x180021769  jnz     short loc_18002176F
0x18002176b  mov     [rbp+27h+UrlComponents.lpszUserName], rsi
0x18002176f  mov     qword ptr [rbp+27h+UrlComponents.dwUserNameLength], rsi
0x180021773  test    r8, r8
0x180021776  jz      short loc_180021782
0x180021778  mov     [rbp+27h+UrlComponents.lpszPassword], r8
0x18002177c  cmp     [r8], si
0x180021780  jnz     short loc_180021786
0x180021782  mov     [rbp+27h+UrlComponents.lpszPassword], rsi
0x180021786  mov     edx, [rbp+27h+arg_48]
0x180021789  lea     rcx, [rbp+27h+UrlComponents]; lpUrlComponents
0x18002178d  mov     r8, [rbp+27h+lpszUrl]; lpszUrl
0x180021791  or      edx, 40002000h; dwFlags
0x180021797  mov     [rbp+27h+UrlComponents.lpszUrlPath], r9
0x18002179b  lea     r9, [rbp+27h+dwUrlLength]; lpdwUrlLength
0x18002179f  mov     qword ptr [rbp+27h+UrlComponents.dwPasswordLength], rsi
0x1800217a3  mov     qword ptr [rbp+27h+UrlComponents.dwUrlPathLength], rsi
0x1800217a7  mov     [rbp+27h+UrlComponents.lpszExtraInfo], rsi
0x1800217ab  mov     qword ptr [rbp+27h+UrlComponents.dwExtraInfoLength], rsi
0x1800217af  call    cs:__imp_InternetCreateUrlW
0x1800217b5  test    eax, eax
0x1800217b7  jz      short loc_1800217D0
0x1800217b9  mov     r8, [rbp+27h+arg_20]; unsigned __int16 *
0x1800217bd  mov     ebx, esi
0x1800217bf  test    r8, r8
0x1800217c2  jz      short loc_1800217D0
0x1800217c4  mov     rcx, [rbp+27h+lpszUrl]; unsigned __int16 *
0x1800217c8  mov     rdx, rdi; unsigned __int64
0x1800217cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800217d0  mov     eax, ebx
0x1800217d2  add     rsp, 98h
0x1800217d9  pop     rdi
0x1800217da  pop     rsi
0x1800217db  pop     rbx
0x1800217dc  pop     rbp
0x1800217dd  retn
```
