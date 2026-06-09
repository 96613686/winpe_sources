# HTTPStream::OpenRequest(ushort const *)

- ea: `0x18015c4d0`
- end: `0x18015c707`
- name: `?OpenRequest@HTTPStream@@IEAAJPEBG@Z`
- size: `567`
- prototype: `HRESULT __fastcall(HTTPStream *this, const wchar_t *pwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18015c9d0`

## callees

- `0x18000ae54`
- `0x180064204`
- `0x1800cba94`
- `0x18015c4d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c6d0`
- `WINHTTP!WinHttpSetOption` at `0x18015c575`
- `WINHTTP!WinHttpSetOption` at `0x18015c69c`
- `WINHTTP!WinHttpSetOption` at `0x18015c6c2`
- `WINHTTP!WinHttpSetOption` at `0x18015c575`
- `WINHTTP!WinHttpSetOption` at `0x18015c69c`
- `WINHTTP!WinHttpSetOption` at `0x18015c6c2`
- `WINHTTP!WinHttpConnect` at `0x18015c624`
- `WINHTTP!WinHttpConnect` at `0x18015c624`
- `WINHTTP!WinHttpCloseHandle` at `0x18015c505`
- `WINHTTP!WinHttpCloseHandle` at `0x18015c51e`
- `WINHTTP!WinHttpCloseHandle` at `0x18015c505`
- `WINHTTP!WinHttpCloseHandle` at `0x18015c51e`
- `WINHTTP!WinHttpCrackUrl` at `0x18015c5ba`
- `WINHTTP!WinHttpCrackUrl` at `0x18015c5ba`
- `WINHTTP!WinHttpOpenRequest` at `0x18015c672`
- `WINHTTP!WinHttpOpenRequest` at `0x18015c672`
- `WINHTTP!WinHttpOpen` at `0x18015c547`
- `WINHTTP!WinHttpOpen` at `0x18015c547`

## string_xrefs

- `0x18015c53e`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)`

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
0x18015c4d0  mov     [rsp-8+arg_8], rbx
0x18015c4d5  push    rbp
0x18015c4d6  push    rsi
0x18015c4d7  push    rdi
0x18015c4d8  lea     rbp, [rsp-47h]
0x18015c4dd  sub     rsp, 0C0h
0x18015c4e4  xor     esi, esi
0x18015c4e6  mov     rdi, this
0x18015c4e9  mov     this, [this+0B0h]; hInternet
0x18015c4f0  mov     rbx, pwszUrl
0x18015c4f3  mov     [rbp+57h+pwszHostName], rsi
0x18015c4f7  mov     [rbp+57h+dwCodePage], esi
0x18015c4fa  mov     [rbp+57h+dwDisable], esi
0x18015c4fd  mov     [rbp+57h+dwAutoLogonPolicy], esi
0x18015c500  test    this, this
0x18015c503  jz      short loc_18015C512
0x18015c505  call    cs:__imp_WinHttpCloseHandle
0x18015c50b  mov     [rdi+0B0h], rsi
0x18015c512  mov     this, [rdi+0A8h]; hInternet
0x18015c519  test    this, this
0x18015c51c  jz      short loc_18015C52B
0x18015c51e  call    cs:__imp_WinHttpCloseHandle
0x18015c524  mov     [rdi+0A8h], rsi
0x18015c52b  cmp     [rdi+0A0h], rsi
0x18015c532  jnz     short loc_18015C583
0x18015c534  xor     r9d, r9d; pszProxyBypassW
0x18015c537  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x18015c53b  xor     r8d, r8d; pszProxyW
0x18015c53e  lea     this, aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x18015c545  xor     edx, edx; dwAccessType
0x18015c547  call    cs:__imp_WinHttpOpen
0x18015c54d  mov     [rdi+0A0h], rax
0x18015c554  test    rax, rax
0x18015c557  jz      $winhttp_error_0
0x18015c55d  mov     r9d, 4; dwBufferLength
0x18015c563  mov     [rbp+57h+dwCodePage], 0FDE9h
0x18015c56a  lea     r8, [rbp+57h+dwCodePage]; lpBuffer
0x18015c56e  mov     this, rax; hInternet
0x18015c571  lea     edx, [r9+40h]; dwOption
0x18015c575  call    cs:__imp_WinHttpSetOption
0x18015c57b  test    eax, eax
0x18015c57d  jz      $winhttp_error_0
0x18015c583  xor     edx, edx; Val
0x18015c585  lea     this, [rbp+57h+url]; void *
0x18015c589  lea     r8d, [pwszUrl+68h]; Size
0x18015c58d  call    memset_0
0x18015c592  lea     r9, [rbp+57h+url]; lpUrlComponents
0x18015c596  mov     [rbp+57h+url.dwStructSize], 68h ; 'h'
0x18015c59d  xor     r8d, r8d; dwFlags
0x18015c5a0  mov     [rbp+57h+url.dwHostNameLength], 1
0x18015c5a7  xor     edx, edx; dwUrlLength
0x18015c5a9  mov     [rbp+57h+url.dwUrlPathLength], 1
0x18015c5b0  mov     this, rbx; pwszUrl
0x18015c5b3  mov     [rbp+57h+url.dwExtraInfoLength], 1
0x18015c5ba  call    cs:__imp_WinHttpCrackUrl
0x18015c5c0  test    eax, eax
0x18015c5c2  jz      $winhttp_error_0
0x18015c5c8  mov     eax, [rbp+57h+url.nScheme]
0x18015c5cb  dec     eax
0x18015c5cd  cmp     eax, 1
0x18015c5d0  jbe     short loc_18015C5DC
0x18015c5d2  mov     ebx, 0C00C0241h
0x18015c5d7  jmp     loc_18015C6F2
0x18015c5dc  cmp     [rbp+57h+url.dwUrlPathLength], esi
0x18015c5df  jnz     short loc_18015C5F3
0x18015c5e1  lea     rax, asc_1801BFB38; "/"
0x18015c5e8  mov     [rbp+57h+url.dwUrlPathLength], 1
0x18015c5ef  mov     [rbp+57h+url.lpszUrlPath], rax
0x18015c5f3  mov     r8d, [rbp+57h+url.dwHostNameLength]; cch
0x18015c5f7  lea     pwszUrl, [rbp+57h+pwszHostName]; ppszDup
0x18015c5fb  mov     this, [rbp+57h+url.lpszHostName]; psz
0x18015c5ff  call    ?allocStrWHR@@YAJPEBGPEAPEAG_K@Z; allocStrWHR(ushort const *,ushort * *,unsigned __int64)
0x18015c604  mov     rsi, [rbp+57h+pwszHostName]
0x18015c608  mov     ebx, eax
0x18015c60a  test    eax, eax
0x18015c60c  js      $error_4
0x18015c612  movzx   r8d, [rbp+57h+url.nPort]; nServerPort
0x18015c617  xor     r9d, r9d; dwReserved
0x18015c61a  mov     this, [rdi+0A0h]; hSession
0x18015c621  mov     pwszUrl, rsi; pswzServerName
0x18015c624  call    cs:__imp_WinHttpConnect
0x18015c62a  mov     [rdi+0A8h], rax
0x18015c631  test    rax, rax
0x18015c634  jz      $winhttp_error_0
0x18015c63a  cmp     [rbp+57h+url.nScheme], 2
0x18015c63e  mov     ecx, 80h
0x18015c643  mov     r8, [rbp+57h+url.lpszUrlPath]; pwszObjectName
0x18015c647  mov     edx, 800080h
0x18015c64c  cmovz   ecx, edx
0x18015c64f  xor     r9d, r9d; pwszVersion
0x18015c652  mov     [rsp+0D0h+var_A0], ecx; dwFlags
0x18015c656  lea     pwszUrl, aGet_0; "GET"
0x18015c65d  mov     [rsp+0D0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18015c666  mov     this, rax; hConnect
0x18015c669  mov     qword ptr [rsp+0D0h+dwFlags], 0; pwszReferrer
0x18015c672  call    cs:__imp_WinHttpOpenRequest
0x18015c678  mov     [rdi+0B0h], rax
0x18015c67f  test    rax, rax
0x18015c682  jz      short $winhttp_error_0
0x18015c684  mov     r9d, 4; dwBufferLength
0x18015c68a  mov     [rbp+57h+dwDisable], 2
0x18015c691  lea     r8, [rbp+57h+dwDisable]; lpBuffer
0x18015c695  mov     this, rax; hInternet
0x18015c698  lea     edx, [r9+3Bh]; dwOption
0x18015c69c  call    cs:__imp_WinHttpSetOption
0x18015c6a2  test    eax, eax
0x18015c6a4  jz      short $winhttp_error_0
0x18015c6a6  mov     this, [rdi+0B0h]; hInternet
0x18015c6ad  lea     r8, [rbp+57h+dwAutoLogonPolicy]; lpBuffer
0x18015c6b1  mov     r9d, 4; dwBufferLength
0x18015c6b7  mov     [rbp+57h+dwAutoLogonPolicy], 0
0x18015c6be  lea     edx, [r9+49h]; dwOption
0x18015c6c2  call    cs:__imp_WinHttpSetOption
0x18015c6c8  test    eax, eax
0x18015c6ca  jz      short $winhttp_error_0
0x18015c6cc  xor     ebx, ebx
0x18015c6ce  jmp     short $error_4
0x18015c6d0  call    cs:__imp_GetLastError
0x18015c6d6  mov     ebx, eax
0x18015c6d8  test    eax, eax
0x18015c6da  jle     short $error_4
0x18015c6dc  movzx   ebx, ax
0x18015c6df  or      ebx, 80070000h
0x18015c6e5  test    rsi, rsi
0x18015c6e8  jz      short loc_18015C6F2
0x18015c6ea  mov     this, rsi; pv
0x18015c6ed  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18015c6f2  mov     eax, ebx
0x18015c6f4  mov     rbx, [rsp+0D0h+arg_8]
0x18015c6fc  add     rsp, 0C0h
0x18015c703  pop     rdi
0x18015c704  pop     rsi
0x18015c705  pop     rbp
0x18015c706  retn
```
