# HTTPStream::OpenRequest(ushort const *)

- ea: `0x1013dc0e`
- end: `0x1013dd97`
- name: `?OpenRequest@HTTPStream@@IAEJPBG@Z`
- size: `393`
- prototype: `HRESULT __thiscall(HTTPStream *this, const wchar_t *pwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1013e020`

## callees

- `0x10040d5e`
- `0x100656b3`
- `0x1006c2c4`
- `0x1013dc0e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dd6e`
- `WINHTTP!WinHttpSetOption` at `0x1013dc73`
- `WINHTTP!WinHttpSetOption` at `0x1013dd4c`
- `WINHTTP!WinHttpSetOption` at `0x1013dd64`
- `WINHTTP!WinHttpSetOption` at `0x1013dc73`
- `WINHTTP!WinHttpSetOption` at `0x1013dd4c`
- `WINHTTP!WinHttpSetOption` at `0x1013dd64`
- `WINHTTP!WinHttpConnect` at `0x1013dd04`
- `WINHTTP!WinHttpConnect` at `0x1013dd04`
- `WINHTTP!WinHttpCloseHandle` at `0x1013dc2a`
- `WINHTTP!WinHttpCloseHandle` at `0x1013dc3b`
- `WINHTTP!WinHttpCloseHandle` at `0x1013dc2a`
- `WINHTTP!WinHttpCloseHandle` at `0x1013dc3b`
- `WINHTTP!WinHttpCrackUrl` at `0x1013dcad`
- `WINHTTP!WinHttpCrackUrl` at `0x1013dcad`
- `WINHTTP!WinHttpOpenRequest` at `0x1013dd2f`
- `WINHTTP!WinHttpOpenRequest` at `0x1013dd2f`
- `WINHTTP!WinHttpOpen` at `0x1013dc52`
- `WINHTTP!WinHttpOpen` at `0x1013dc52`

## string_xrefs

- `0x1013dc4d`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)`

## pseudocode

```c
unsigned int __thiscall HTTPStream::OpenRequest(HTTPStream *this, const wchar_t *pwszUrl)
{
  wchar_t *v3; // ebx
  HINTERNET v4; // eax
  unsigned int v5; // esi
  int v6; // eax
  HINTERNET v7; // eax
  DWORD v8; // ecx
  HINTERNET v9; // eax
  signed int LastError; // eax
  URL_COMPONENTSW url; // [esp+Ch] [ebp-4Ch] BYREF
  unsigned int dwAutoLogonPolicy; // [esp+48h] [ebp-10h] BYREF
  unsigned int dwDisable; // [esp+4Ch] [ebp-Ch] BYREF
  unsigned int dwCodePage; // [esp+50h] [ebp-8h] BYREF
  wchar_t *pwszHostName; // [esp+54h] [ebp-4h] BYREF

  v3 = 0;
  pwszHostName = 0;
  if ( this->_hHTTP )
  {
    WinHttpCloseHandle(this->_hHTTP);
    this->_hHTTP = 0;
  }
  if ( this->_hConnection )
  {
    WinHttpCloseHandle(this->_hConnection);
    this->_hConnection = 0;
  }
  if ( !this->_hInet )
  {
    v4 = WinHttpOpen(L"Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)", 0, 0, 0, 0);
    this->_hInet = v4;
    if ( !v4 )
      goto winhttp_error_0;
    dwCodePage = 65001;
    if ( !WinHttpSetOption(v4, 0x44u, &dwCodePage, 4u) )
      goto winhttp_error_0;
  }
  memset(&url, 0, sizeof(url));
  url.dwStructSize = 60;
  url.dwHostNameLength = 1;
  url.dwUrlPathLength = 1;
  url.dwExtraInfoLength = 1;
  if ( !WinHttpCrackUrl(pwszUrl, 0, 0, &url) )
    goto winhttp_error_0;
  if ( url.nScheme != INTERNET_SCHEME_FTP && url.nScheme != INTERNET_SCHEME_GOPHER )
    return -1072954815;
  if ( !url.dwUrlPathLength )
  {
    url.lpszUrlPath = (wchar_t *)L"/";
    url.dwUrlPathLength = 1;
  }
  v6 = allocStrWHR(url.lpszHostName, &pwszHostName, url.dwHostNameLength);
  v3 = pwszHostName;
  v5 = v6;
  if ( v6 >= 0 )
  {
    v5 = 0;
    v7 = WinHttpConnect(this->_hInet, pwszHostName, url.nPort, 0);
    this->_hConnection = v7;
    if ( !v7 )
      goto winhttp_error_0;
    v8 = 128;
    if ( url.nScheme == INTERNET_SCHEME_GOPHER )
      v8 = 8388736;
    v9 = WinHttpOpenRequest(v7, L"GET", url.lpszUrlPath, 0, 0, 0, v8);
    this->_hHTTP = v9;
    if ( !v9
      || (dwDisable = 2, !WinHttpSetOption(v9, 0x3Fu, &dwDisable, 4u))
      || (dwAutoLogonPolicy = 0, !WinHttpSetOption(this->_hHTTP, 0x4Du, &dwAutoLogonPolicy, 4u)) )
    {
winhttp_error_0:
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v3 )
    MemFree(v3);
  return v5;
}

```

## disassembly

```asm
0x1013dc0e  mov     edi, edi
0x1013dc10  push    ebp
0x1013dc11  mov     ebp, esp
0x1013dc13  sub     esp, 4Ch
0x1013dc16  push    ebx; ISAXLocator *
0x1013dc17  push    esi; this
0x1013dc18  push    edi
0x1013dc19  mov     edi, this
0x1013dc1b  xor     esi, esi
0x1013dc1d  mov     ebx, esi
0x1013dc1f  mov     [ebp+pwszHostName], ebx
0x1013dc22  cmp     [edi+5Ch], ebx
0x1013dc25  jz      short loc_1013DC33
0x1013dc27  push    dword ptr [edi+5Ch]; hInternet
0x1013dc2a  call    ds:__imp__WinHttpCloseHandle@4; WinHttpCloseHandle(x)
0x1013dc30  mov     [edi+5Ch], esi
0x1013dc33  cmp     [edi+58h], ebx
0x1013dc36  jz      short loc_1013DC44
0x1013dc38  push    dword ptr [edi+58h]; hInternet
0x1013dc3b  call    ds:__imp__WinHttpCloseHandle@4; WinHttpCloseHandle(x)
0x1013dc41  mov     [edi+58h], esi
0x1013dc44  cmp     [edi+54h], esi
0x1013dc47  jnz     short loc_1013DC81
0x1013dc49  push    esi; dwFlags
0x1013dc4a  push    esi; pszProxyBypassW
0x1013dc4b  push    esi; pszProxyW
0x1013dc4c  push    esi; dwAccessType
0x1013dc4d  push    offset aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x1013dc52  call    ds:__imp__WinHttpOpen@20; WinHttpOpen(x,x,x,x,x)
0x1013dc58  mov     [edi+54h], eax
0x1013dc5b  test    eax, eax
0x1013dc5d  jz      winhttp_error_0
0x1013dc63  push    4; dwBufferLength
0x1013dc65  lea     this, [ebp+dwCodePage]
0x1013dc68  mov     [ebp+dwCodePage], 0FDE9h
0x1013dc6f  push    this; lpBuffer
0x1013dc70  push    44h ; 'D'; dwOption
0x1013dc72  push    eax; hInternet
0x1013dc73  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013dc79  test    eax, eax
0x1013dc7b  jz      winhttp_error_0
0x1013dc81  push    3Ch ; '<'
0x1013dc83  pop     esi
0x1013dc84  push    esi; Size
0x1013dc85  lea     eax, [ebp+url]
0x1013dc88  push    0; Val
0x1013dc8a  push    eax; void *
0x1013dc8b  call    _memset
0x1013dc90  add     esp, 0Ch
0x1013dc93  mov     [ebp+url.dwStructSize], esi
0x1013dc96  lea     eax, [ebp+url]
0x1013dc99  xor     esi, esi
0x1013dc9b  inc     esi
0x1013dc9c  mov     [ebp+url.dwHostNameLength], esi
0x1013dc9f  push    eax; lpUrlComponents
0x1013dca0  push    0; dwFlags
0x1013dca2  push    0; dwUrlLength
0x1013dca4  push    [ebp+pwszUrl]; pwszUrl
0x1013dca7  mov     [ebp+url.dwUrlPathLength], esi
0x1013dcaa  mov     [ebp+url.dwExtraInfoLength], esi
0x1013dcad  call    ds:__imp__WinHttpCrackUrl@16; WinHttpCrackUrl(x,x,x,x)
0x1013dcb3  test    eax, eax
0x1013dcb5  jz      winhttp_error_0
0x1013dcbb  cmp     [ebp+url.nScheme], esi
0x1013dcbe  jz      short loc_1013DCD0
0x1013dcc0  cmp     [ebp+url.nScheme], 2
0x1013dcc4  jz      short loc_1013DCD0
0x1013dcc6  mov     esi, 0C00C0241h
0x1013dccb  jmp     loc_1013DD8E
0x1013dcd0  cmp     [ebp+url.dwUrlPathLength], ebx
0x1013dcd3  jnz     short loc_1013DCDF
0x1013dcd5  mov     [ebp+url.lpszUrlPath], offset asc_1001E7D0; "/" ...
0x1013dcdc  mov     [ebp+url.dwUrlPathLength], esi
0x1013dcdf  push    [ebp+url.dwHostNameLength]; cch
0x1013dce2  mov     this, [ebp+url.lpszHostName]; psz
0x1013dce5  lea     edx, [ebp+pwszHostName]; ppszDup
0x1013dce8  call    ?allocStrWHR@@YGJPBGPAPAGI@Z; allocStrWHR(ushort const *,ushort * *,uint)
0x1013dced  mov     ebx, [ebp+pwszHostName]
0x1013dcf0  mov     esi, eax
0x1013dcf2  test    esi, esi
0x1013dcf4  js      error_0
0x1013dcfa  xor     esi, esi
0x1013dcfc  push    esi; dwReserved
0x1013dcfd  push    dword ptr [ebp+url.nPort]; nServerPort
0x1013dd00  push    ebx; pswzServerName
0x1013dd01  push    dword ptr [edi+54h]; hSession
0x1013dd04  call    ds:__imp__WinHttpConnect@16; WinHttpConnect(x,x,x,x)
0x1013dd0a  mov     [edi+58h], eax
0x1013dd0d  test    eax, eax
0x1013dd0f  jz      short winhttp_error_0
0x1013dd11  cmp     [ebp+url.nScheme], 2
0x1013dd15  mov     edx, 800080h
0x1013dd1a  mov     this, 80h
0x1013dd1f  cmovz   this, edx
0x1013dd22  push    this; dwFlags
0x1013dd23  push    esi; ppwszAcceptTypes
0x1013dd24  push    esi; pwszReferrer
0x1013dd25  push    esi; pwszVersion
0x1013dd26  push    [ebp+url.lpszUrlPath]; pwszObjectName
0x1013dd29  push    offset aGet; "GET"
0x1013dd2e  push    eax; hConnect
0x1013dd2f  call    ds:__imp__WinHttpOpenRequest@28; WinHttpOpenRequest(x,x,x,x,x,x,x)
0x1013dd35  mov     [edi+5Ch], eax
0x1013dd38  test    eax, eax
0x1013dd3a  jz      short winhttp_error_0
0x1013dd3c  push    4; dwBufferLength
0x1013dd3e  lea     this, [ebp+dwDisable]
0x1013dd41  mov     [ebp+dwDisable], 2
0x1013dd48  push    this; lpBuffer
0x1013dd49  push    3Fh ; '?'; dwOption
0x1013dd4b  push    eax; hInternet
0x1013dd4c  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013dd52  test    eax, eax
0x1013dd54  jz      short winhttp_error_0
0x1013dd56  push    4; dwBufferLength
0x1013dd58  lea     eax, [ebp+dwAutoLogonPolicy]
0x1013dd5b  mov     [ebp+dwAutoLogonPolicy], esi
0x1013dd5e  push    eax; lpBuffer
0x1013dd5f  push    4Dh ; 'M'; dwOption
0x1013dd61  push    dword ptr [edi+5Ch]; hInternet
0x1013dd64  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013dd6a  test    eax, eax
0x1013dd6c  jnz     short error_0
0x1013dd6e  call    ds:__imp__GetLastError@0; GetLastError()
0x1013dd74  mov     esi, eax
0x1013dd76  test    esi, esi
0x1013dd78  jle     short error_0
0x1013dd7a  movzx   esi, si
0x1013dd7d  or      esi, 80070000h
0x1013dd83  test    ebx, ebx
0x1013dd85  jz      short loc_1013DD8E
0x1013dd87  mov     this, ebx; pv
0x1013dd89  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x1013dd8e  pop     edi
0x1013dd8f  mov     eax, esi
0x1013dd91  pop     esi
0x1013dd92  pop     ebx
0x1013dd93  leave
0x1013dd94  retn    4
```
