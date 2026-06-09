# URLMONRequest::recycle(void)

- ea: `0x18015cf00`
- end: `0x18015d1d7`
- name: `?recycle@URLMONRequest@@UEAAXXZ`
- size: `727`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180084fe4`
- `0x180085094`
- `0x180086880`
- `0x1800bdb84`
- `0x1800cc6e4`
- `0x18015cf00`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015d15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015d15f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015d0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015d0cb`

## pseudocode

```c
void __fastcall URLMONRequest::recycle(URLMONRequest *this)
{
  char v2; // di
  IStream *pstrmResponse; // rcx
  ISequentialStream *psstrmSeqResponse; // rcx
  ISequentialStream *psstrmCallback; // rcx
  ISequentialStream *pstrmCustom; // rcx
  IXMLHTTPRequest2Callback *pStatusCallback; // rcx
  IXMLHTTPRequest3Callback *pStatusCallback3; // rcx
  IUri *pUri; // rcx
  INotificationTransportSync *pTransportSync; // rcx
  unsigned __int8 *pbClientCert; // rcx
  IInternetProtocol *pIInternetProtocol; // rcx
  wchar_t *pwszResult; // rcx
  void *hStartComplete; // rcx
  URLMONRequest_vtbl *v15; // rax

  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x22u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  this->Lock(this);
  if ( this->_fAborted || (v2 = 0, this->_fAbortPending) )
    v2 = 1;
  URLRequest::recycle(this);
  HTTPHeaders::reset(&this->_requestHeaders);
  HTTPHeaders::reset(&this->_responseHeaders);
  *(_QWORD *)&this->_dwAuth = 0;
  *(_QWORD *)&this->_dwTimeout = 0;
  *(_WORD *)&this->_fProxyUserNameAndPassword = 0;
  *(_WORD *)&this->_fNoCache = 0;
  this->_fQueryStringInUtf8 = 0;
  SecureString::reset(&this->_ssProxyPassword);
  SecureString::reset(&this->_ssProxyUserName);
  pstrmResponse = this->_pstrmResponse;
  if ( pstrmResponse )
  {
    pstrmResponse->Release(pstrmResponse);
    this->_pstrmResponse = 0;
  }
  psstrmSeqResponse = this->_psstrmSeqResponse;
  if ( psstrmSeqResponse )
  {
    psstrmSeqResponse->Release(psstrmSeqResponse);
    this->_psstrmSeqResponse = 0;
  }
  psstrmCallback = this->_psstrmCallback;
  if ( psstrmCallback )
  {
    psstrmCallback->Release(psstrmCallback);
    this->_psstrmCallback = 0;
  }
  pstrmCustom = this->_pstrmCustom;
  if ( pstrmCustom )
  {
    pstrmCustom->Release(pstrmCustom);
    this->_pstrmCustom = 0;
  }
  pStatusCallback = this->_pStatusCallback;
  if ( pStatusCallback )
  {
    pStatusCallback->Release(pStatusCallback);
    this->_pStatusCallback = 0;
  }
  pStatusCallback3 = this->_pStatusCallback3;
  if ( pStatusCallback3 )
  {
    pStatusCallback3->Release(pStatusCallback3);
    this->_pStatusCallback3 = 0;
  }
  pUri = this->_pUri;
  if ( pUri )
  {
    pUri->Release(pUri);
    this->_pUri = 0;
  }
  pTransportSync = this->_pTransportSync;
  this->_pXhr2 = 0;
  if ( pTransportSync )
  {
    pTransportSync->Release(pTransportSync);
    this->_pTransportSync = 0;
  }
  URLMONRequest::_FreeTransportSettings(this);
  pbClientCert = this->_pbClientCert;
  this->_cbClientCert = 0;
  CoTaskMemFree(pbClientCert);
  this->_pbClientCert = 0;
  this->_fBindStatusUsingCachedCopy = 0;
  *(_QWORD *)&this->_fInvokedCallOnServerCert = 0;
  if ( !v2 )
  {
    pIInternetProtocol = this->_pIInternetProtocol;
    if ( pIInternetProtocol )
    {
      pIInternetProtocol->Release(pIInternetProtocol);
      this->_pIInternetProtocol = 0;
    }
  }
  pwszResult = this->_PendingResultCallback.pwszResult;
  this->_dwError = 0;
  this->_dwUrlmonCallbackThread = 0;
  this->_dwPendingDataCallback = 0;
  operator delete(pwszResult, (const std::nothrow_t *)2);
  *(_OWORD *)&this->_PendingResultCallback.fPending = 0;
  this->_PendingResultCallback.pwszResult = 0;
  hStartComplete = this->_hStartComplete;
  this->_fFinished = 0;
  *(_QWORD *)&this->_fHTTPS = 0;
  if ( hStartComplete )
  {
    CloseHandle(hStartComplete);
    this->_hStartComplete = 0;
  }
  this->_ullOnDataThreshold = 0;
  this->_ullDataSinceOnData = 0;
  SecureString::reset(&this->_ssEDPClaim);
  v15 = this->__vftable;
  this->_dwMaxConns = 0;
  v15->Unlock(this);
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_d(0x403u, 0x23u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x18015cf00  mov     [rsp+arg_0], rbx
0x18015cf05  mov     [rsp+arg_8], rsi
0x18015cf0a  push    rdi
0x18015cf0b  sub     rsp, 20h
0x18015cf0f  mov     rbx, this
0x18015cf12  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015cf19  jz      short loc_18015CF34
0x18015cf1b  mov     edx, 22h ; '"'; id
0x18015cf20  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015cf27  mov     ecx, 403h; LevelKeyword
0x18015cf2c  mov     r9, rbx; _a1
0x18015cf2f  call    WPP_SF_q
0x18015cf34  mov     rax, [rbx]
0x18015cf37  mov     this, rbx
0x18015cf3a  mov     rax, [rax+0F8h]
0x18015cf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cf46  xor     esi, esi
0x18015cf48  cmp     [rbx+0Eh], sil
0x18015cf4c  jnz     short loc_18015CF59
0x18015cf4e  mov     dil, sil
0x18015cf51  cmp     [rbx+260h], esi
0x18015cf57  jz      short loc_18015CF5C
0x18015cf59  mov     dil, 1
0x18015cf5c  mov     this, rbx; this
0x18015cf5f  call    ?recycle@URLRequest@@UEAAXXZ; URLRequest::recycle(void)
0x18015cf64  lea     this, [rbx+0D0h]; this
0x18015cf6b  call    ?reset@HTTPHeaders@@QEAAXXZ; HTTPHeaders::reset(void)
0x18015cf70  lea     this, [rbx+120h]; this
0x18015cf77  call    ?reset@HTTPHeaders@@QEAAXXZ; HTTPHeaders::reset(void)
0x18015cf7c  lea     this, [rbx+1B8h]; this
0x18015cf83  mov     [rbx+190h], rsi
0x18015cf8a  mov     [rbx+1D0h], rsi
0x18015cf91  mov     [rbx+19Bh], si
0x18015cf98  mov     [rbx+198h], si
0x18015cf9f  mov     [rbx+19Ah], sil
0x18015cfa6  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x18015cfab  lea     this, [rbx+1A0h]; this
0x18015cfb2  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x18015cfb7  mov     this, [rbx+170h]
0x18015cfbe  test    this, this
0x18015cfc1  jz      short loc_18015CFD6
0x18015cfc3  mov     rax, [this]
0x18015cfc6  mov     rax, [rax+10h]
0x18015cfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cfcf  mov     [rbx+170h], rsi
0x18015cfd6  mov     this, [rbx+178h]
0x18015cfdd  test    this, this
0x18015cfe0  jz      short loc_18015CFF5
0x18015cfe2  mov     rax, [this]
0x18015cfe5  mov     rax, [rax+10h]
0x18015cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cfee  mov     [rbx+178h], rsi
0x18015cff5  mov     this, [rbx+188h]
0x18015cffc  test    this, this
0x18015cfff  jz      short loc_18015D014
0x18015d001  mov     rax, [this]
0x18015d004  mov     rax, [rax+10h]
0x18015d008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d00d  mov     [rbx+188h], rsi
0x18015d014  mov     this, [rbx+180h]
0x18015d01b  test    this, this
0x18015d01e  jz      short loc_18015D033
0x18015d020  mov     rax, [this]
0x18015d023  mov     rax, [rax+10h]
0x18015d027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d02c  mov     [rbx+180h], rsi
0x18015d033  mov     this, [rbx+210h]
0x18015d03a  test    this, this
0x18015d03d  jz      short loc_18015D052
0x18015d03f  mov     rax, [this]
0x18015d042  mov     rax, [rax+10h]
0x18015d046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d04b  mov     [rbx+210h], rsi
0x18015d052  mov     this, [rbx+218h]
0x18015d059  test    this, this
0x18015d05c  jz      short loc_18015D071
0x18015d05e  mov     rax, [this]
0x18015d061  mov     rax, [rax+10h]
0x18015d065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d06a  mov     [rbx+218h], rsi
0x18015d071  mov     this, [rbx+0C0h]
0x18015d078  test    this, this
0x18015d07b  jz      short loc_18015D090
0x18015d07d  mov     rax, [this]
0x18015d080  mov     rax, [rax+10h]
0x18015d084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d089  mov     [rbx+0C0h], rsi
0x18015d090  mov     this, [rbx+0C8h]
0x18015d097  mov     [rbx+220h], rsi
0x18015d09e  test    this, this
0x18015d0a1  jz      short loc_18015D0B6
0x18015d0a3  mov     rax, [this]
0x18015d0a6  mov     rax, [rax+10h]
0x18015d0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d0af  mov     [rbx+0C8h], rsi
0x18015d0b6  mov     this, rbx; this
0x18015d0b9  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x18015d0be  mov     this, [rbx+1E0h]; pv
0x18015d0c5  mov     [rbx+1D8h], esi
0x18015d0cb  call    cs:__imp_CoTaskMemFree
0x18015d0d2  nop     dword ptr [rax+rax+00h]
0x18015d0d7  mov     [rbx+1E0h], rsi
0x18015d0de  mov     [rbx+1E8h], esi
0x18015d0e4  mov     [rbx+270h], rsi
0x18015d0eb  test    dil, dil
0x18015d0ee  jnz     short loc_18015D10F
0x18015d0f0  mov     this, [rbx+0B8h]
0x18015d0f7  test    this, this
0x18015d0fa  jz      short loc_18015D10F
0x18015d0fc  mov     rax, [this]
0x18015d0ff  mov     rax, [rax+10h]
0x18015d103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d108  mov     [rbx+0B8h], rsi
0x18015d10f  mov     this, [rbx+250h]; block
0x18015d116  mov     edx, 2; __formal
0x18015d11b  mov     [rbx+1F0h], esi
0x18015d121  mov     [rbx+258h], esi
0x18015d127  mov     [rbx+238h], esi
0x18015d12d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18015d132  xor     eax, eax
0x18015d134  xorps   xmm0, xmm0
0x18015d137  movups  xmmword ptr [rbx+240h], xmm0
0x18015d13e  mov     [rbx+250h], rax
0x18015d145  mov     this, [rbx+228h]; hObject
0x18015d14c  mov     [rbx+19Dh], sil
0x18015d153  mov     [rbx+268h], rsi
0x18015d15a  test    this, this
0x18015d15d  jz      short loc_18015D172
0x18015d15f  call    cs:__imp_CloseHandle
0x18015d166  nop     dword ptr [rax+rax+00h]
0x18015d16b  mov     [rbx+228h], rsi
0x18015d172  lea     this, [rbx+288h]; this
0x18015d179  mov     [rbx+278h], rsi
0x18015d180  mov     [rbx+280h], rsi
0x18015d187  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x18015d18c  mov     rax, [rbx]
0x18015d18f  mov     this, rbx
0x18015d192  mov     [rbx+2A0h], esi
0x18015d198  mov     rax, [rax+100h]
0x18015d19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d1a4  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015d1ab  jz      short loc_18015D1C6
0x18015d1ad  mov     edx, 23h ; '#'; id
0x18015d1b2  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d1b9  mov     ecx, 403h; LevelKeyword
0x18015d1be  xor     r9d, r9d; _a1
0x18015d1c1  call    WPP_SF_d
0x18015d1c6  mov     rbx, [rsp+28h+arg_0]
0x18015d1cb  mov     rsi, [rsp+28h+arg_8]
0x18015d1d0  add     rsp, 20h
0x18015d1d4  pop     rdi
0x18015d1d5  retn
```
