# HTTPStream::OpenRequest(ushort const *)

- ea: `0x18015fd40`
- end: `0x18015ffb4`
- name: `?OpenRequest@HTTPStream@@IEAAJPEBG@Z`
- size: `628`
- prototype: `HRESULT __fastcall(HTTPStream *this, const wchar_t *pwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801602e0`

## callees

- `0x180017480`
- `0x1800393c0`
- `0x1800cd3e4`
- `0x18015fd40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ff76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ff76`
- `WINHTTP!WinHttpSetOption` at `0x18015fdf7`
- `WINHTTP!WinHttpSetOption` at `0x18015ff36`
- `WINHTTP!WinHttpSetOption` at `0x18015ff62`
- `WINHTTP!WinHttpSetOption` at `0x18015fdf7`
- `WINHTTP!WinHttpSetOption` at `0x18015ff36`
- `WINHTTP!WinHttpSetOption` at `0x18015ff62`
- `WINHTTP!WinHttpConnect` at `0x18015feb2`
- `WINHTTP!WinHttpConnect` at `0x18015feb2`
- `WINHTTP!WinHttpCloseHandle` at `0x18015fd75`
- `WINHTTP!WinHttpCloseHandle` at `0x18015fd94`
- `WINHTTP!WinHttpCloseHandle` at `0x18015fd75`
- `WINHTTP!WinHttpCloseHandle` at `0x18015fd94`
- `WINHTTP!WinHttpCrackUrl` at `0x18015fe42`
- `WINHTTP!WinHttpCrackUrl` at `0x18015fe42`
- `WINHTTP!WinHttpOpenRequest` at `0x18015ff06`
- `WINHTTP!WinHttpOpenRequest` at `0x18015ff06`
- `WINHTTP!WinHttpOpen` at `0x18015fdc3`
- `WINHTTP!WinHttpOpen` at `0x18015fdc3`

## string_xrefs

- `0x18015fdba`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)`

## pseudocode

```c
__int64 __fastcall HTTPStream::OpenRequest(HTTPStream *this, const wchar_t *pwszUrl)
{
  wchar_t *v2; // rsi
  void *hHTTP; // rcx
  void *hConnection; // rcx
  HINTERNET v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  HINTERNET v10; // rax
  DWORD v11; // ecx
  HINTERNET v12; // rax
  void *v13; // rcx
  signed int LastError; // eax
  wchar_t *pwszHostName; // [rsp+40h] [rbp-39h] BYREF
  URL_COMPONENTSW url; // [rsp+50h] [rbp-29h] BYREF
  unsigned int dwCodePage; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int dwDisable; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int dwAutoLogonPolicy; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  hHTTP = this->_hHTTP;
  pwszHostName = 0;
  dwCodePage = 0;
  dwDisable = 0;
  dwAutoLogonPolicy = 0;
  if ( hHTTP )
  {
    WinHttpCloseHandle(hHTTP);
    this->_hHTTP = 0;
  }
  hConnection = this->_hConnection;
  if ( hConnection )
  {
    WinHttpCloseHandle(hConnection);
    this->_hConnection = 0;
  }
  if ( !this->_hInet )
  {
    v7 = WinHttpOpen(L"Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)", 0, 0, 0, 0);
    this->_hInet = v7;
    if ( !v7 )
      goto $winhttp_error_0;
    dwCodePage = 65001;
    if ( !WinHttpSetOption(v7, 0x44u, &dwCodePage, 4u) )
      goto $winhttp_error_0;
  }
  memset_0(&url, 0, sizeof(url));
  url.dwStructSize = 104;
  url.dwHostNameLength = 1;
  url.dwUrlPathLength = 1;
  url.dwExtraInfoLength = 1;
  if ( !WinHttpCrackUrl(pwszUrl, 0, 0, &url) )
    goto $winhttp_error_0;
  if ( (unsigned int)(url.nScheme - 1) > 1 )
    return (unsigned int)-1072954815;
  if ( !url.dwUrlPathLength )
  {
    url.dwUrlPathLength = 1;
    url.lpszUrlPath = (wchar_t *)L"/";
  }
  v9 = allocStrWHR(url.lpszHostName, &pwszHostName, url.dwHostNameLength);
  v2 = pwszHostName;
  v8 = v9;
  if ( v9 >= 0 )
  {
    v10 = WinHttpConnect(this->_hInet, pwszHostName, url.nPort, 0);
    this->_hConnection = v10;
    if ( v10 )
    {
      v11 = 128;
      if ( url.nScheme == INTERNET_SCHEME_GOPHER )
        v11 = 8388736;
      v12 = WinHttpOpenRequest(v10, L"GET", url.lpszUrlPath, 0, 0, 0, v11);
      this->_hHTTP = v12;
      if ( v12 )
      {
        dwDisable = 2;
        if ( WinHttpSetOption(v12, 0x3Fu, &dwDisable, 4u) )
        {
          v13 = this->_hHTTP;
          dwAutoLogonPolicy = 0;
          if ( WinHttpSetOption(v13, 0x4Du, &dwAutoLogonPolicy, 4u) )
          {
            v8 = 0;
            goto $error_4;
          }
        }
      }
    }
$winhttp_error_0:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
$error_4:
  if ( v2 )
    MemFree(v2);
  return v8;
}

```

## disassembly

```asm
0x18015fd40  mov     [rsp-8+arg_8], rbx
0x18015fd45  push    rbp
0x18015fd46  push    rsi
0x18015fd47  push    rdi
0x18015fd48  lea     rbp, [rsp-47h]
0x18015fd4d  sub     rsp, 0C0h
0x18015fd54  xor     esi, esi
0x18015fd56  mov     rdi, this
0x18015fd59  mov     this, [this+0B0h]; hInternet
0x18015fd60  mov     rbx, pwszUrl
0x18015fd63  mov     [rbp+57h+pwszHostName], rsi
0x18015fd67  mov     [rbp+57h+dwCodePage], esi
0x18015fd6a  mov     [rbp+57h+dwDisable], esi
0x18015fd6d  mov     [rbp+57h+dwAutoLogonPolicy], esi
0x18015fd70  test    this, this
0x18015fd73  jz      short loc_18015FD88
0x18015fd75  call    cs:__imp_WinHttpCloseHandle
0x18015fd7c  nop     dword ptr [rax+rax+00h]
0x18015fd81  mov     [rdi+0B0h], rsi
0x18015fd88  mov     this, [rdi+0A8h]; hInternet
0x18015fd8f  test    this, this
0x18015fd92  jz      short loc_18015FDA7
0x18015fd94  call    cs:__imp_WinHttpCloseHandle
0x18015fd9b  nop     dword ptr [rax+rax+00h]
0x18015fda0  mov     [rdi+0A8h], rsi
0x18015fda7  cmp     [rdi+0A0h], rsi
0x18015fdae  jnz     short loc_18015FE0B
0x18015fdb0  xor     r9d, r9d; pszProxyBypassW
0x18015fdb3  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x18015fdb7  xor     r8d, r8d; pszProxyW
0x18015fdba  lea     this, aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x18015fdc1  xor     edx, edx; dwAccessType
0x18015fdc3  call    cs:__imp_WinHttpOpen
0x18015fdca  nop     dword ptr [rax+rax+00h]
0x18015fdcf  mov     [rdi+0A0h], rax
0x18015fdd6  test    rax, rax
0x18015fdd9  jz      $winhttp_error_0
0x18015fddf  mov     r9d, 4; dwBufferLength
0x18015fde5  mov     [rbp+57h+dwCodePage], 0FDE9h
0x18015fdec  lea     r8, [rbp+57h+dwCodePage]; lpBuffer
0x18015fdf0  mov     this, rax; hInternet
0x18015fdf3  lea     edx, [r9+40h]; dwOption
0x18015fdf7  call    cs:__imp_WinHttpSetOption
0x18015fdfe  nop     dword ptr [rax+rax+00h]
0x18015fe03  test    eax, eax
0x18015fe05  jz      $winhttp_error_0
0x18015fe0b  xor     edx, edx; Val
0x18015fe0d  lea     this, [rbp+57h+url]; void *
0x18015fe11  lea     r8d, [pwszUrl+68h]; Size
0x18015fe15  call    memset_0
0x18015fe1a  lea     r9, [rbp+57h+url]; lpUrlComponents
0x18015fe1e  mov     [rbp+57h+url.dwStructSize], 68h ; 'h'
0x18015fe25  xor     r8d, r8d; dwFlags
0x18015fe28  mov     [rbp+57h+url.dwHostNameLength], 1
0x18015fe2f  xor     edx, edx; dwUrlLength
0x18015fe31  mov     [rbp+57h+url.dwUrlPathLength], 1
0x18015fe38  mov     this, rbx; pwszUrl
0x18015fe3b  mov     [rbp+57h+url.dwExtraInfoLength], 1
0x18015fe42  call    cs:__imp_WinHttpCrackUrl
0x18015fe49  nop     dword ptr [rax+rax+00h]
0x18015fe4e  test    eax, eax
0x18015fe50  jz      $winhttp_error_0
0x18015fe56  mov     eax, [rbp+57h+url.nScheme]
0x18015fe59  dec     eax
0x18015fe5b  cmp     eax, 1
0x18015fe5e  jbe     short loc_18015FE6A
0x18015fe60  mov     ebx, 0C00C0241h
0x18015fe65  jmp     loc_18015FF9E
0x18015fe6a  cmp     [rbp+57h+url.dwUrlPathLength], esi
0x18015fe6d  jnz     short loc_18015FE81
0x18015fe6f  lea     rax, asc_1801BF460; "/"
0x18015fe76  mov     [rbp+57h+url.dwUrlPathLength], 1
0x18015fe7d  mov     [rbp+57h+url.lpszUrlPath], rax
0x18015fe81  mov     r8d, [rbp+57h+url.dwHostNameLength]; cch
0x18015fe85  lea     pwszUrl, [rbp+57h+pwszHostName]; ppszDup
0x18015fe89  mov     this, [rbp+57h+url.lpszHostName]; psz
0x18015fe8d  call    ?allocStrWHR@@YAJPEBGPEAPEAG_K@Z; allocStrWHR(ushort const *,ushort * *,unsigned __int64)
0x18015fe92  mov     rsi, [rbp+57h+pwszHostName]
0x18015fe96  mov     ebx, eax
0x18015fe98  test    eax, eax
0x18015fe9a  js      $error_4
0x18015fea0  movzx   r8d, [rbp+57h+url.nPort]; nServerPort
0x18015fea5  xor     r9d, r9d; dwReserved
0x18015fea8  mov     this, [rdi+0A0h]; hSession
0x18015feaf  mov     pwszUrl, rsi; pswzServerName
0x18015feb2  call    cs:__imp_WinHttpConnect
0x18015feb9  nop     dword ptr [rax+rax+00h]
0x18015febe  mov     [rdi+0A8h], rax
0x18015fec5  test    rax, rax
0x18015fec8  jz      $winhttp_error_0
0x18015fece  cmp     [rbp+57h+url.nScheme], 2
0x18015fed2  mov     ecx, 80h
0x18015fed7  mov     r8, [rbp+57h+url.lpszUrlPath]; pwszObjectName
0x18015fedb  mov     edx, 800080h
0x18015fee0  cmovz   ecx, edx
0x18015fee3  xor     r9d, r9d; pwszVersion
0x18015fee6  mov     [rsp+0D0h+var_A0], ecx; dwFlags
0x18015feea  lea     pwszUrl, aGet_0; "GET"
0x18015fef1  mov     [rsp+0D0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18015fefa  mov     this, rax; hConnect
0x18015fefd  mov     qword ptr [rsp+0D0h+dwFlags], 0; pwszReferrer
0x18015ff06  call    cs:__imp_WinHttpOpenRequest
0x18015ff0d  nop     dword ptr [rax+rax+00h]
0x18015ff12  mov     [rdi+0B0h], rax
0x18015ff19  test    rax, rax
0x18015ff1c  jz      short $winhttp_error_0
0x18015ff1e  mov     r9d, 4; dwBufferLength
0x18015ff24  mov     [rbp+57h+dwDisable], 2
0x18015ff2b  lea     r8, [rbp+57h+dwDisable]; lpBuffer
0x18015ff2f  mov     this, rax; hInternet
0x18015ff32  lea     edx, [r9+3Bh]; dwOption
0x18015ff36  call    cs:__imp_WinHttpSetOption
0x18015ff3d  nop     dword ptr [rax+rax+00h]
0x18015ff42  test    eax, eax
0x18015ff44  jz      short $winhttp_error_0
0x18015ff46  mov     this, [rdi+0B0h]; hInternet
0x18015ff4d  lea     r8, [rbp+57h+dwAutoLogonPolicy]; lpBuffer
0x18015ff51  mov     r9d, 4; dwBufferLength
0x18015ff57  mov     [rbp+57h+dwAutoLogonPolicy], 0
0x18015ff5e  lea     edx, [r9+49h]; dwOption
0x18015ff62  call    cs:__imp_WinHttpSetOption
0x18015ff69  nop     dword ptr [rax+rax+00h]
0x18015ff6e  test    eax, eax
0x18015ff70  jz      short $winhttp_error_0
0x18015ff72  xor     ebx, ebx
0x18015ff74  jmp     short $error_4
0x18015ff76  call    cs:__imp_GetLastError
0x18015ff7d  nop     dword ptr [rax+rax+00h]
0x18015ff82  mov     ebx, eax
0x18015ff84  test    eax, eax
0x18015ff86  jle     short $error_4
0x18015ff88  movzx   ebx, ax
0x18015ff8b  or      ebx, 80070000h
0x18015ff91  test    rsi, rsi
0x18015ff94  jz      short loc_18015FF9E
0x18015ff96  mov     this, rsi; pv
0x18015ff99  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18015ff9e  mov     eax, ebx
0x18015ffa0  mov     rbx, [rsp+0D0h+arg_8]
0x18015ffa8  add     rsp, 0C0h
0x18015ffaf  pop     rdi
0x18015ffb0  pop     rsi
0x18015ffb1  pop     rbp
0x18015ffb2  retn
```
