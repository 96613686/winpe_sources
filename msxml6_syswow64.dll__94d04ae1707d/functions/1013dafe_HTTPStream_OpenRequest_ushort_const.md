# HTTPStream::OpenRequest(ushort const *)

- ea: `0x1013dafe`
- end: `0x1013dc87`
- name: `?OpenRequest@HTTPStream@@IAEJPBG@Z`
- size: `393`
- prototype: `HRESULT __thiscall(HTTPStream *this, const wchar_t *pwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1013df10`

## callees

- `0x10040dee`
- `0x10065753`
- `0x1006c354`
- `0x1013dafe`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dc5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013dc5e`
- `WINHTTP!WinHttpSetOption` at `0x1013db63`
- `WINHTTP!WinHttpSetOption` at `0x1013dc3c`
- `WINHTTP!WinHttpSetOption` at `0x1013dc54`
- `WINHTTP!WinHttpSetOption` at `0x1013db63`
- `WINHTTP!WinHttpSetOption` at `0x1013dc3c`
- `WINHTTP!WinHttpSetOption` at `0x1013dc54`
- `WINHTTP!WinHttpConnect` at `0x1013dbf4`
- `WINHTTP!WinHttpConnect` at `0x1013dbf4`
- `WINHTTP!WinHttpCloseHandle` at `0x1013db1a`
- `WINHTTP!WinHttpCloseHandle` at `0x1013db2b`
- `WINHTTP!WinHttpCloseHandle` at `0x1013db1a`
- `WINHTTP!WinHttpCloseHandle` at `0x1013db2b`
- `WINHTTP!WinHttpCrackUrl` at `0x1013db9d`
- `WINHTTP!WinHttpCrackUrl` at `0x1013db9d`
- `WINHTTP!WinHttpOpenRequest` at `0x1013dc1f`
- `WINHTTP!WinHttpOpenRequest` at `0x1013dc1f`
- `WINHTTP!WinHttpOpen` at `0x1013db42`
- `WINHTTP!WinHttpOpen` at `0x1013db42`

## string_xrefs

- `0x1013db3d`: `Mozilla/4.0 (compatible; MSIE 5.01; Windows NT 5.0)`

## pseudocode

```c
unsigned int __thiscall HTTPStream::OpenRequest(HTTPStream *this, const wchar_t *pwszUrl)
{
  wchar_t *v3; // ebx
  HINTERNET v4; // eax
  unsigned int v5; // esi
  HRESULT v6; // eax
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
0x1013dafe  mov     edi, edi
0x1013db00  push    ebp
0x1013db01  mov     ebp, esp
0x1013db03  sub     esp, 4Ch
0x1013db06  push    ebx; ISAXLocator *
0x1013db07  push    esi; this
0x1013db08  push    edi
0x1013db09  mov     edi, this
0x1013db0b  xor     esi, esi
0x1013db0d  mov     ebx, esi
0x1013db0f  mov     [ebp+pwszHostName], ebx
0x1013db12  cmp     [edi+5Ch], ebx
0x1013db15  jz      short loc_1013DB23
0x1013db17  push    dword ptr [edi+5Ch]; hInternet
0x1013db1a  call    ds:__imp__WinHttpCloseHandle@4; WinHttpCloseHandle(x)
0x1013db20  mov     [edi+5Ch], esi
0x1013db23  cmp     [edi+58h], ebx
0x1013db26  jz      short loc_1013DB34
0x1013db28  push    dword ptr [edi+58h]; hInternet
0x1013db2b  call    ds:__imp__WinHttpCloseHandle@4; WinHttpCloseHandle(x)
0x1013db31  mov     [edi+58h], esi
0x1013db34  cmp     [edi+54h], esi
0x1013db37  jnz     short loc_1013DB71
0x1013db39  push    esi; dwFlags
0x1013db3a  push    esi; pszProxyBypassW
0x1013db3b  push    esi; pszProxyW
0x1013db3c  push    esi; dwAccessType
0x1013db3d  push    offset aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 5.01; Win"...
0x1013db42  call    ds:__imp__WinHttpOpen@20; WinHttpOpen(x,x,x,x,x)
0x1013db48  mov     [edi+54h], eax
0x1013db4b  test    eax, eax
0x1013db4d  jz      winhttp_error_0
0x1013db53  push    4; dwBufferLength
0x1013db55  lea     this, [ebp+dwCodePage]
0x1013db58  mov     [ebp+dwCodePage], 0FDE9h
0x1013db5f  push    this; lpBuffer
0x1013db60  push    44h ; 'D'; dwOption
0x1013db62  push    eax; hInternet
0x1013db63  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013db69  test    eax, eax
0x1013db6b  jz      winhttp_error_0
0x1013db71  push    3Ch ; '<'
0x1013db73  pop     esi
0x1013db74  push    esi; Size
0x1013db75  lea     eax, [ebp+url]
0x1013db78  push    0; Val
0x1013db7a  push    eax; void *
0x1013db7b  call    _memset
0x1013db80  add     esp, 0Ch
0x1013db83  mov     [ebp+url.dwStructSize], esi
0x1013db86  lea     eax, [ebp+url]
0x1013db89  xor     esi, esi
0x1013db8b  inc     esi
0x1013db8c  mov     [ebp+url.dwHostNameLength], esi
0x1013db8f  push    eax; lpUrlComponents
0x1013db90  push    0; dwFlags
0x1013db92  push    0; dwUrlLength
0x1013db94  push    [ebp+pwszUrl]; pwszUrl
0x1013db97  mov     [ebp+url.dwUrlPathLength], esi
0x1013db9a  mov     [ebp+url.dwExtraInfoLength], esi
0x1013db9d  call    ds:__imp__WinHttpCrackUrl@16; WinHttpCrackUrl(x,x,x,x)
0x1013dba3  test    eax, eax
0x1013dba5  jz      winhttp_error_0
0x1013dbab  cmp     [ebp+url.nScheme], esi
0x1013dbae  jz      short loc_1013DBC0
0x1013dbb0  cmp     [ebp+url.nScheme], 2
0x1013dbb4  jz      short loc_1013DBC0
0x1013dbb6  mov     esi, 0C00C0241h
0x1013dbbb  jmp     loc_1013DC7E
0x1013dbc0  cmp     [ebp+url.dwUrlPathLength], ebx
0x1013dbc3  jnz     short loc_1013DBCF
0x1013dbc5  mov     [ebp+url.lpszUrlPath], offset asc_1001E7D0; "/" ...
0x1013dbcc  mov     [ebp+url.dwUrlPathLength], esi
0x1013dbcf  push    [ebp+url.dwHostNameLength]; cch
0x1013dbd2  mov     this, [ebp+url.lpszHostName]; psz
0x1013dbd5  lea     edx, [ebp+pwszHostName]; ppszDup
0x1013dbd8  call    ?allocStrWHR@@YGJPBGPAPAGI@Z; allocStrWHR(ushort const *,ushort * *,uint)
0x1013dbdd  mov     ebx, [ebp+pwszHostName]
0x1013dbe0  mov     esi, eax
0x1013dbe2  test    esi, esi
0x1013dbe4  js      error_0
0x1013dbea  xor     esi, esi
0x1013dbec  push    esi; dwReserved
0x1013dbed  push    dword ptr [ebp+url.nPort]; nServerPort
0x1013dbf0  push    ebx; pswzServerName
0x1013dbf1  push    dword ptr [edi+54h]; hSession
0x1013dbf4  call    ds:__imp__WinHttpConnect@16; WinHttpConnect(x,x,x,x)
0x1013dbfa  mov     [edi+58h], eax
0x1013dbfd  test    eax, eax
0x1013dbff  jz      short winhttp_error_0
0x1013dc01  cmp     [ebp+url.nScheme], 2
0x1013dc05  mov     edx, 800080h
0x1013dc0a  mov     this, 80h
0x1013dc0f  cmovz   this, edx
0x1013dc12  push    this; dwFlags
0x1013dc13  push    esi; ppwszAcceptTypes
0x1013dc14  push    esi; pwszReferrer
0x1013dc15  push    esi; pwszVersion
0x1013dc16  push    [ebp+url.lpszUrlPath]; pwszObjectName
0x1013dc19  push    offset aGet; "GET"
0x1013dc1e  push    eax; hConnect
0x1013dc1f  call    ds:__imp__WinHttpOpenRequest@28; WinHttpOpenRequest(x,x,x,x,x,x,x)
0x1013dc25  mov     [edi+5Ch], eax
0x1013dc28  test    eax, eax
0x1013dc2a  jz      short winhttp_error_0
0x1013dc2c  push    4; dwBufferLength
0x1013dc2e  lea     this, [ebp+dwDisable]
0x1013dc31  mov     [ebp+dwDisable], 2
0x1013dc38  push    this; lpBuffer
0x1013dc39  push    3Fh ; '?'; dwOption
0x1013dc3b  push    eax; hInternet
0x1013dc3c  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013dc42  test    eax, eax
0x1013dc44  jz      short winhttp_error_0
0x1013dc46  push    4; dwBufferLength
0x1013dc48  lea     eax, [ebp+dwAutoLogonPolicy]
0x1013dc4b  mov     [ebp+dwAutoLogonPolicy], esi
0x1013dc4e  push    eax; lpBuffer
0x1013dc4f  push    4Dh ; 'M'; dwOption
0x1013dc51  push    dword ptr [edi+5Ch]; hInternet
0x1013dc54  call    ds:__imp__WinHttpSetOption@16; WinHttpSetOption(x,x,x,x)
0x1013dc5a  test    eax, eax
0x1013dc5c  jnz     short error_0
0x1013dc5e  call    ds:__imp__GetLastError@0; GetLastError()
0x1013dc64  mov     esi, eax
0x1013dc66  test    esi, esi
0x1013dc68  jle     short error_0
0x1013dc6a  movzx   esi, si
0x1013dc6d  or      esi, 80070000h
0x1013dc73  test    ebx, ebx
0x1013dc75  jz      short loc_1013DC7E
0x1013dc77  mov     this, ebx; pv
0x1013dc79  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x1013dc7e  pop     edi
0x1013dc7f  mov     eax, esi
0x1013dc81  pop     esi
0x1013dc82  pop     ebx
0x1013dc83  leave
0x1013dc84  retn    4
```
