# WinHttpConnection::CreateUrl(ushort * *)

- ea: `0x180078098`
- end: `0x1800781e3`
- name: `?CreateUrl@WinHttpConnection@@QEAAJPEAPEAG@Z`
- size: `331`
- prototype: `int(WinHttpConnection *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003d19c`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180011fc0`
- `0x180012cf0`
- `0x1800307c4`
- `0x18003334c`
- `0x180078098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007810e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007810e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078179`
- `WINHTTP!WinHttpCreateUrl` at `0x180078100`
- `WINHTTP!WinHttpCreateUrl` at `0x18007816f`
- `WINHTTP!WinHttpCreateUrl` at `0x180078100`
- `WINHTTP!WinHttpCreateUrl` at `0x18007816f`

## string_xrefs

- `0x1800781a6`: `CopyStringNullSafeW`
- `0x1800781b6`: `WinHttpCreateUrl`
- `0x1800780bf`: `WinHttpConnection::CreateUrl`
- `0x1800780d9`: `WinHttpConnection::CreateUrl`
- `0x180078148`: `WinHttpConnection::CreateUrl`
- `0x1800781bd`: `WinHttpConnection::CreateUrl`

## pseudocode

```c
__int64 __fastcall WinHttpConnection::CreateUrl(WinHttpConnection *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  signed int v4; // ebx
  struct $BC2FB811D417144E831EE3AEA4A279C8 *v5; // rbp
  signed int LastError; // eax
  WCHAR *v7; // rax
  signed int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  const wchar_t *v11; // r8
  DWORD pdwUrlLength; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  pdwUrlLength = 0;
  if ( a2 )
  {
    v5 = (struct $BC2FB811D417144E831EE3AEA4A279C8 *)((char *)this + 16);
    v4 = 0;
    *a2 = 0;
    if ( WinHttpCreateUrl((LPURL_COMPONENTS)((char *)this + 16), 0, 0, &pdwUrlLength) )
      goto LABEL_18;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147024774 )
    {
      v7 = (WCHAR *)SafeAlloc(2LL * pdwUrlLength + 2);
      v2 = v7;
      if ( !v7 )
      {
        v4 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpConnection::CreateUrl");
        goto LABEL_18;
      }
      if ( WinHttpCreateUrl(v5, 0, v7, &pdwUrlLength) )
        goto LABEL_13;
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_13:
        v9 = CopyStringNullSafeW(v2, a2);
        v4 = v9;
        if ( v9 >= 0 )
          goto LABEL_18;
        v10 = (unsigned int)v9;
        v11 = L"CopyStringNullSafeW";
LABEL_17:
        Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"WinHttpConnection::CreateUrl", v11, v10);
        goto LABEL_18;
      }
    }
    else if ( v4 >= 0 )
    {
      goto LABEL_18;
    }
    v10 = (unsigned int)v4;
    v11 = L"WinHttpCreateUrl";
    goto LABEL_17;
  }
  v4 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpConnection::CreateUrl", L"url");
  Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpConnection::CreateUrl", L"url");
LABEL_18:
  SafeFree(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180078098  push    rbx
0x18007809a  push    rbp
0x18007809b  push    rsi
0x18007809c  push    rdi
0x18007809d  sub     rsp, 28h
0x1800780a1  xor     edi, edi
0x1800780a3  mov     [rsp+48h+pdwUrlLength], 0
0x1800780ab  mov     rsi, rdx
0x1800780ae  test    rdx, rdx
0x1800780b1  jnz     short loc_1800780EA
0x1800780b3  lea     r8, aUrl_1; "url"
0x1800780ba  mov     ebx, 80070057h
0x1800780bf  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x1800780c6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800780cd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800780d2  lea     rdx, aUrl_1; "url"
0x1800780d9  lea     rcx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x1800780e0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800780e5  jmp     loc_1800781D0
0x1800780ea  lea     rbp, [rcx+10h]
0x1800780ee  xor     ebx, ebx
0x1800780f0  mov     [rdx], rbx
0x1800780f3  lea     r9, [rsp+48h+pdwUrlLength]; pdwUrlLength
0x1800780f8  xor     edx, edx; dwFlags
0x1800780fa  xor     r8d, r8d; pwszUrl
0x1800780fd  mov     rcx, rbp; lpUrlComponents
0x180078100  call    cs:__imp_WinHttpCreateUrl
0x180078106  test    eax, eax
0x180078108  jnz     loc_1800781D0
0x18007810e  call    cs:__imp_GetLastError
0x180078114  mov     ebx, eax
0x180078116  test    eax, eax
0x180078118  jle     short loc_180078123
0x18007811a  movzx   ebx, ax
0x18007811d  or      ebx, 80070000h
0x180078123  cmp     ebx, 8007007Ah
0x180078129  jnz     loc_1800781AF
0x18007812f  mov     ecx, [rsp+48h+pdwUrlLength]
0x180078133  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18007813b  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180078140  mov     rdi, rax
0x180078143  test    rax, rax
0x180078146  jnz     short loc_180078162
0x180078148  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x18007814f  mov     ebx, 8007000Eh
0x180078154  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18007815b  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180078160  jmp     short loc_1800781D0
0x180078162  lea     r9, [rsp+48h+pdwUrlLength]; pdwUrlLength
0x180078167  mov     r8, rdi; pwszUrl
0x18007816a  xor     edx, edx; dwFlags
0x18007816c  mov     rcx, rbp; lpUrlComponents
0x18007816f  call    cs:__imp_WinHttpCreateUrl
0x180078175  test    eax, eax
0x180078177  jnz     short loc_180078192
0x180078179  call    cs:__imp_GetLastError
0x18007817f  mov     ebx, eax
0x180078181  test    eax, eax
0x180078183  jle     short loc_18007818E
0x180078185  movzx   ebx, ax
0x180078188  or      ebx, 80070000h
0x18007818e  test    ebx, ebx
0x180078190  js      short loc_1800781B3
0x180078192  mov     rdx, rsi; unsigned __int16 **
0x180078195  mov     rcx, rdi; Source
0x180078198  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18007819d  mov     ebx, eax
0x18007819f  test    eax, eax
0x1800781a1  jns     short loc_1800781D0
0x1800781a3  mov     r9d, eax
0x1800781a6  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x1800781ad  jmp     short loc_1800781BD
0x1800781af  test    ebx, ebx
0x1800781b1  jns     short loc_1800781D0
0x1800781b3  mov     r9d, ebx
0x1800781b6  lea     r8, aWinhttpcreateu_0; "WinHttpCreateUrl"
0x1800781bd  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x1800781c4  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800781cb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800781d0  mov     rcx, rdi; lpMem
0x1800781d3  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800781d8  mov     eax, ebx
0x1800781da  add     rsp, 28h
0x1800781de  pop     rdi
0x1800781df  pop     rsi
0x1800781e0  pop     rbp
0x1800781e1  pop     rbx
0x1800781e2  retn
```
