# HTTPStream::OpenRequest(ushort const *)

- ea: `0x1800f443c`
- end: `0x1800f4673`
- name: `?OpenRequest@HTTPStream@@IEAAJPEBG@Z`
- size: `567`
- prototype: `int(HTTPStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f4950`

## callees

- `0x18001f080`
- `0x18003e82c`
- `0x1800f443c`
- `0x180102cde`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f463c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f463c`
- `WINHTTP!WinHttpOpenRequest` at `0x1800f45de`
- `WINHTTP!WinHttpOpenRequest` at `0x1800f45de`
- `WINHTTP!WinHttpConnect` at `0x1800f4590`
- `WINHTTP!WinHttpConnect` at `0x1800f4590`
- `WINHTTP!WinHttpSetOption` at `0x1800f44e1`
- `WINHTTP!WinHttpSetOption` at `0x1800f4608`
- `WINHTTP!WinHttpSetOption` at `0x1800f462e`
- `WINHTTP!WinHttpSetOption` at `0x1800f44e1`
- `WINHTTP!WinHttpSetOption` at `0x1800f4608`
- `WINHTTP!WinHttpSetOption` at `0x1800f462e`
- `WINHTTP!WinHttpOpen` at `0x1800f44b3`
- `WINHTTP!WinHttpOpen` at `0x1800f44b3`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f4471`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f448a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f4471`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f448a`
- `WINHTTP!WinHttpCrackUrl` at `0x1800f4526`
- `WINHTTP!WinHttpCrackUrl` at `0x1800f4526`

## string_xrefs

- `0x1800f44aa`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)`

## pseudocode

```c
__int64 __fastcall HTTPStream::OpenRequest(HTTPStream *this, const unsigned __int16 *a2)
{
  WCHAR *v2; // rsi
  void *v4; // rcx
  void *v6; // rcx
  void *v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  void *v10; // rax
  DWORD v11; // ecx
  void *v12; // rax
  void *v13; // rcx
  signed int LastError; // eax
  LPCWSTR pswzServerName; // [rsp+40h] [rbp-39h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-29h] BYREF
  int Buffer; // [rsp+E0h] [rbp+67h] BYREF
  int v19; // [rsp+F0h] [rbp+77h] BYREF
  int v20; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  v4 = (void *)*((_QWORD *)this + 22);
  pswzServerName = 0;
  Buffer = 0;
  v19 = 0;
  v20 = 0;
  if ( v4 )
  {
    WinHttpCloseHandle(v4);
    *((_QWORD *)this + 22) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 21);
  if ( v6 )
  {
    WinHttpCloseHandle(v6);
    *((_QWORD *)this + 21) = 0;
  }
  if ( !*((_QWORD *)this + 20) )
  {
    v7 = WinHttpOpen(L"Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)", 0, 0, 0, 0);
    *((_QWORD *)this + 20) = v7;
    if ( !v7 )
      goto LABEL_21;
    Buffer = 65001;
    if ( !WinHttpSetOption(v7, 0x44u, &Buffer, 4u) )
      goto LABEL_21;
  }
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwExtraInfoLength = 1;
  if ( !WinHttpCrackUrl(a2, 0, 0, &UrlComponents) )
    goto LABEL_21;
  if ( (unsigned int)(UrlComponents.nScheme - 1) > 1 )
    return (unsigned int)-2147467259;
  if ( !UrlComponents.dwUrlPathLength )
  {
    UrlComponents.dwUrlPathLength = 1;
    UrlComponents.lpszUrlPath = (LPSTR)L"/";
  }
  v9 = allocStrWHR(
         (const unsigned __int16 *)UrlComponents.lpszHostName,
         (unsigned __int16 **)&pswzServerName,
         UrlComponents.dwHostNameLength);
  v2 = (WCHAR *)pswzServerName;
  v8 = v9;
  if ( v9 >= 0 )
  {
    v10 = WinHttpConnect(*((HINTERNET *)this + 20), pswzServerName, UrlComponents.nPort, 0);
    *((_QWORD *)this + 21) = v10;
    if ( v10 )
    {
      v11 = 128;
      if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
        v11 = 8388736;
      v12 = WinHttpOpenRequest(v10, L"GET", (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, v11);
      *((_QWORD *)this + 22) = v12;
      if ( v12 )
      {
        v19 = 2;
        if ( WinHttpSetOption(v12, 0x3Fu, &v19, 4u) )
        {
          v13 = (void *)*((_QWORD *)this + 22);
          v20 = 0;
          if ( WinHttpSetOption(v13, 0x4Du, &v20, 4u) )
          {
            v8 = 0;
            goto LABEL_23;
          }
        }
      }
    }
LABEL_21:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_23:
  if ( v2 )
    MemFreeObject(v2);
  return v8;
}

```

## disassembly

```asm
0x1800f443c  mov     [rsp-8+arg_8], rbx
0x1800f4441  push    rbp
0x1800f4442  push    rsi
0x1800f4443  push    rdi
0x1800f4444  lea     rbp, [rsp-47h]
0x1800f4449  sub     rsp, 0C0h
0x1800f4450  xor     esi, esi
0x1800f4452  mov     rdi, rcx
0x1800f4455  mov     rcx, [rcx+0B0h]; hInternet
0x1800f445c  mov     rbx, rdx
0x1800f445f  mov     [rbp+57h+pswzServerName], rsi
0x1800f4463  mov     [rbp+57h+Buffer], esi
0x1800f4466  mov     [rbp+57h+arg_10], esi
0x1800f4469  mov     [rbp+57h+arg_18], esi
0x1800f446c  test    rcx, rcx
0x1800f446f  jz      short loc_1800F447E
0x1800f4471  call    cs:__imp_WinHttpCloseHandle
0x1800f4477  mov     [rdi+0B0h], rsi
0x1800f447e  mov     rcx, [rdi+0A8h]; hInternet
0x1800f4485  test    rcx, rcx
0x1800f4488  jz      short loc_1800F4497
0x1800f448a  call    cs:__imp_WinHttpCloseHandle
0x1800f4490  mov     [rdi+0A8h], rsi
0x1800f4497  cmp     [rdi+0A0h], rsi
0x1800f449e  jnz     short loc_1800F44EF
0x1800f44a0  xor     r9d, r9d; pszProxyBypassW
0x1800f44a3  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x1800f44a7  xor     r8d, r8d; pszProxyW
0x1800f44aa  lea     rcx, pszAgentW; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x1800f44b1  xor     edx, edx; dwAccessType
0x1800f44b3  call    cs:__imp_WinHttpOpen
0x1800f44b9  mov     [rdi+0A0h], rax
0x1800f44c0  test    rax, rax
0x1800f44c3  jz      loc_1800F463C
0x1800f44c9  mov     r9d, 4; dwBufferLength
0x1800f44cf  mov     [rbp+57h+Buffer], 0FDE9h
0x1800f44d6  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800f44da  mov     rcx, rax; hInternet
0x1800f44dd  lea     edx, [r9+40h]; dwOption
0x1800f44e1  call    cs:__imp_WinHttpSetOption
0x1800f44e7  test    eax, eax
0x1800f44e9  jz      loc_1800F463C
0x1800f44ef  xor     edx, edx; Val
0x1800f44f1  lea     rcx, [rbp+57h+UrlComponents]; void *
0x1800f44f5  lea     r8d, [rdx+68h]; Size
0x1800f44f9  call    memset_0
0x1800f44fe  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800f4502  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800f4509  xor     r8d, r8d; dwFlags
0x1800f450c  mov     [rbp+57h+UrlComponents.dwHostNameLength], 1
0x1800f4513  xor     edx, edx; dwUrlLength
0x1800f4515  mov     [rbp+57h+UrlComponents.dwUrlPathLength], 1
0x1800f451c  mov     rcx, rbx; pwszUrl
0x1800f451f  mov     [rbp+57h+UrlComponents.dwExtraInfoLength], 1
0x1800f4526  call    cs:__imp_WinHttpCrackUrl
0x1800f452c  test    eax, eax
0x1800f452e  jz      loc_1800F463C
0x1800f4534  mov     eax, [rbp+57h+UrlComponents.nScheme]
0x1800f4537  dec     eax
0x1800f4539  cmp     eax, 1
0x1800f453c  jbe     short loc_1800F4548
0x1800f453e  mov     ebx, 80004005h
0x1800f4543  jmp     loc_1800F465E
0x1800f4548  cmp     [rbp+57h+UrlComponents.dwUrlPathLength], esi
0x1800f454b  jnz     short loc_1800F455F
0x1800f454d  lea     rax, asc_18012E034; "/"
0x1800f4554  mov     [rbp+57h+UrlComponents.dwUrlPathLength], 1
0x1800f455b  mov     [rbp+57h+UrlComponents.lpszUrlPath], rax
0x1800f455f  mov     r8d, [rbp+57h+UrlComponents.dwHostNameLength]; unsigned __int64
0x1800f4563  lea     rdx, [rbp+57h+pswzServerName]; unsigned __int16 **
0x1800f4567  mov     rcx, [rbp+57h+UrlComponents.lpszHostName]; Src
0x1800f456b  call    ?allocStrWHR@@YAJPEBGPEAPEAG_K@Z; allocStrWHR(ushort const *,ushort * *,unsigned __int64)
0x1800f4570  mov     rsi, [rbp+57h+pswzServerName]
0x1800f4574  mov     ebx, eax
0x1800f4576  test    eax, eax
0x1800f4578  js      loc_1800F4651
0x1800f457e  movzx   r8d, [rbp+57h+UrlComponents.nPort]; nServerPort
0x1800f4583  xor     r9d, r9d; dwReserved
0x1800f4586  mov     rcx, [rdi+0A0h]; hSession
0x1800f458d  mov     rdx, rsi; pswzServerName
0x1800f4590  call    cs:__imp_WinHttpConnect
0x1800f4596  mov     [rdi+0A8h], rax
0x1800f459d  test    rax, rax
0x1800f45a0  jz      loc_1800F463C
0x1800f45a6  cmp     [rbp+57h+UrlComponents.nScheme], 2
0x1800f45aa  mov     ecx, 80h
0x1800f45af  mov     r8, [rbp+57h+UrlComponents.lpszUrlPath]; pwszObjectName
0x1800f45b3  mov     edx, 800080h
0x1800f45b8  cmovz   ecx, edx
0x1800f45bb  xor     r9d, r9d; pwszVersion
0x1800f45be  mov     [rsp+0D0h+var_A0], ecx; dwFlags
0x1800f45c2  lea     rdx, pwszVerb; "GET"
0x1800f45c9  mov     [rsp+0D0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1800f45d2  mov     rcx, rax; hConnect
0x1800f45d5  mov     qword ptr [rsp+0D0h+dwFlags], 0; pwszReferrer
0x1800f45de  call    cs:__imp_WinHttpOpenRequest
0x1800f45e4  mov     [rdi+0B0h], rax
0x1800f45eb  test    rax, rax
0x1800f45ee  jz      short loc_1800F463C
0x1800f45f0  mov     r9d, 4; dwBufferLength
0x1800f45f6  mov     [rbp+57h+arg_10], 2
0x1800f45fd  lea     r8, [rbp+57h+arg_10]; lpBuffer
0x1800f4601  mov     rcx, rax; hInternet
0x1800f4604  lea     edx, [r9+3Bh]; dwOption
0x1800f4608  call    cs:__imp_WinHttpSetOption
0x1800f460e  test    eax, eax
0x1800f4610  jz      short loc_1800F463C
0x1800f4612  mov     rcx, [rdi+0B0h]; hInternet
0x1800f4619  lea     r8, [rbp+57h+arg_18]; lpBuffer
0x1800f461d  mov     r9d, 4; dwBufferLength
0x1800f4623  mov     [rbp+57h+arg_18], 0
0x1800f462a  lea     edx, [r9+49h]; dwOption
0x1800f462e  call    cs:__imp_WinHttpSetOption
0x1800f4634  test    eax, eax
0x1800f4636  jz      short loc_1800F463C
0x1800f4638  xor     ebx, ebx
0x1800f463a  jmp     short loc_1800F4651
0x1800f463c  call    cs:__imp_GetLastError
0x1800f4642  mov     ebx, eax
0x1800f4644  test    eax, eax
0x1800f4646  jle     short loc_1800F4651
0x1800f4648  movzx   ebx, ax
0x1800f464b  or      ebx, 80070000h
0x1800f4651  test    rsi, rsi
0x1800f4654  jz      short loc_1800F465E
0x1800f4656  mov     rcx, rsi; void *
0x1800f4659  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800f465e  mov     eax, ebx
0x1800f4660  mov     rbx, [rsp+0D0h+arg_8]
0x1800f4668  add     rsp, 0C0h
0x1800f466f  pop     rdi
0x1800f4670  pop     rsi
0x1800f4671  pop     rbp
0x1800f4672  retn
```
