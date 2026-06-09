# URLMONRequest::recycle(void)

- ea: `0x1801597a0`
- end: `0x180159a6a`
- name: `?recycle@URLMONRequest@@UEAAXXZ`
- size: `714`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800868bc`
- `0x180086968`
- `0x180087570`
- `0x1800bc52c`
- `0x1800cadc4`
- `0x1801597a0`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801599f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801599f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015996b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015996b`

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

  if ( (xmmword_1801F6C20 & 8) != 0 )
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
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_d(0x403u, 0x23u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x1801597a0  mov     [rsp+arg_0], rbx
0x1801597a5  mov     [rsp+arg_8], rsi
0x1801597aa  push    rdi
0x1801597ab  sub     rsp, 20h
0x1801597af  mov     rbx, this
0x1801597b2  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x1801597b9  jz      short loc_1801597D4
0x1801597bb  mov     edx, 22h ; '"'; id
0x1801597c0  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801597c7  mov     ecx, 403h; LevelKeyword
0x1801597cc  mov     r9, rbx; _a1
0x1801597cf  call    WPP_SF_q
0x1801597d4  mov     rax, [rbx]
0x1801597d7  mov     this, rbx
0x1801597da  mov     rax, [rax+0F8h]
0x1801597e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801597e6  xor     esi, esi
0x1801597e8  cmp     [rbx+0Eh], sil
0x1801597ec  jnz     short loc_1801597F9
0x1801597ee  mov     dil, sil
0x1801597f1  cmp     [rbx+260h], esi
0x1801597f7  jz      short loc_1801597FC
0x1801597f9  mov     dil, 1
0x1801597fc  mov     this, rbx; this
0x1801597ff  call    ?recycle@URLRequest@@UEAAXXZ; URLRequest::recycle(void)
0x180159804  lea     this, [rbx+0D0h]; this
0x18015980b  call    ?reset@HTTPHeaders@@QEAAXXZ; HTTPHeaders::reset(void)
0x180159810  lea     this, [rbx+120h]; this
0x180159817  call    ?reset@HTTPHeaders@@QEAAXXZ; HTTPHeaders::reset(void)
0x18015981c  lea     this, [rbx+1B8h]; this
0x180159823  mov     [rbx+190h], rsi
0x18015982a  mov     [rbx+1D0h], rsi
0x180159831  mov     [rbx+19Bh], si
0x180159838  mov     [rbx+198h], si
0x18015983f  mov     [rbx+19Ah], sil
0x180159846  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x18015984b  lea     this, [rbx+1A0h]; this
0x180159852  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180159857  mov     this, [rbx+170h]
0x18015985e  test    this, this
0x180159861  jz      short loc_180159876
0x180159863  mov     rax, [this]
0x180159866  mov     rax, [rax+10h]
0x18015986a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015986f  mov     [rbx+170h], rsi
0x180159876  mov     this, [rbx+178h]
0x18015987d  test    this, this
0x180159880  jz      short loc_180159895
0x180159882  mov     rax, [this]
0x180159885  mov     rax, [rax+10h]
0x180159889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015988e  mov     [rbx+178h], rsi
0x180159895  mov     this, [rbx+188h]
0x18015989c  test    this, this
0x18015989f  jz      short loc_1801598B4
0x1801598a1  mov     rax, [this]
0x1801598a4  mov     rax, [rax+10h]
0x1801598a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801598ad  mov     [rbx+188h], rsi
0x1801598b4  mov     this, [rbx+180h]
0x1801598bb  test    this, this
0x1801598be  jz      short loc_1801598D3
0x1801598c0  mov     rax, [this]
0x1801598c3  mov     rax, [rax+10h]
0x1801598c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801598cc  mov     [rbx+180h], rsi
0x1801598d3  mov     this, [rbx+210h]
0x1801598da  test    this, this
0x1801598dd  jz      short loc_1801598F2
0x1801598df  mov     rax, [this]
0x1801598e2  mov     rax, [rax+10h]
0x1801598e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801598eb  mov     [rbx+210h], rsi
0x1801598f2  mov     this, [rbx+218h]
0x1801598f9  test    this, this
0x1801598fc  jz      short loc_180159911
0x1801598fe  mov     rax, [this]
0x180159901  mov     rax, [rax+10h]
0x180159905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015990a  mov     [rbx+218h], rsi
0x180159911  mov     this, [rbx+0C0h]
0x180159918  test    this, this
0x18015991b  jz      short loc_180159930
0x18015991d  mov     rax, [this]
0x180159920  mov     rax, [rax+10h]
0x180159924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159929  mov     [rbx+0C0h], rsi
0x180159930  mov     this, [rbx+0C8h]
0x180159937  mov     [rbx+220h], rsi
0x18015993e  test    this, this
0x180159941  jz      short loc_180159956
0x180159943  mov     rax, [this]
0x180159946  mov     rax, [rax+10h]
0x18015994a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015994f  mov     [rbx+0C8h], rsi
0x180159956  mov     this, rbx; this
0x180159959  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x18015995e  mov     this, [rbx+1E0h]; pv
0x180159965  mov     [rbx+1D8h], esi
0x18015996b  call    cs:__imp_CoTaskMemFree
0x180159971  mov     [rbx+1E0h], rsi
0x180159978  mov     [rbx+1E8h], esi
0x18015997e  mov     [rbx+270h], rsi
0x180159985  test    dil, dil
0x180159988  jnz     short loc_1801599A9
0x18015998a  mov     this, [rbx+0B8h]
0x180159991  test    this, this
0x180159994  jz      short loc_1801599A9
0x180159996  mov     rax, [this]
0x180159999  mov     rax, [rax+10h]
0x18015999d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801599a2  mov     [rbx+0B8h], rsi
0x1801599a9  mov     this, [rbx+250h]; block
0x1801599b0  mov     edx, 2; __formal
0x1801599b5  mov     [rbx+1F0h], esi
0x1801599bb  mov     [rbx+258h], esi
0x1801599c1  mov     [rbx+238h], esi
0x1801599c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801599cc  xor     eax, eax
0x1801599ce  xorps   xmm0, xmm0
0x1801599d1  movups  xmmword ptr [rbx+240h], xmm0
0x1801599d8  mov     [rbx+250h], rax
0x1801599df  mov     this, [rbx+228h]; hObject
0x1801599e6  mov     [rbx+19Dh], sil
0x1801599ed  mov     [rbx+268h], rsi
0x1801599f4  test    this, this
0x1801599f7  jz      short loc_180159A06
0x1801599f9  call    cs:__imp_CloseHandle
0x1801599ff  mov     [rbx+228h], rsi
0x180159a06  lea     this, [rbx+288h]; this
0x180159a0d  mov     [rbx+278h], rsi
0x180159a14  mov     [rbx+280h], rsi
0x180159a1b  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180159a20  mov     rax, [rbx]
0x180159a23  mov     this, rbx
0x180159a26  mov     [rbx+2A0h], esi
0x180159a2c  mov     rax, [rax+100h]
0x180159a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159a38  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180159a3f  jz      short loc_180159A5A
0x180159a41  mov     edx, 23h ; '#'; id
0x180159a46  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159a4d  mov     ecx, 403h; LevelKeyword
0x180159a52  xor     r9d, r9d; _a1
0x180159a55  call    WPP_SF_d
0x180159a5a  mov     rbx, [rsp+28h+arg_0]
0x180159a5f  mov     rsi, [rsp+28h+arg_8]
0x180159a64  add     rsp, 20h
0x180159a68  pop     rdi
0x180159a69  retn
```
