# URLMONRequest::~URLMONRequest(void)

- ea: `0x180086664`
- end: `0x18008687a`
- name: `??1URLMONRequest@@UEAA@XZ`
- size: `534`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180155470`

## callees

- `0x180086664`
- `0x180086880`
- `0x1800868bc`
- `0x1800bc47c`
- `0x1800bc52c`
- `0x1800c3c98`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800867fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800867fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800867e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800867e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800867b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800867b3`

## pseudocode

```c
void __fastcall URLMONRequest::~URLMONRequest(URLMONRequest *this)
{
  IStream *pstrmResponse; // rcx
  ISequentialStream *psstrmSeqResponse; // rcx
  ISequentialStream *pstrmCustom; // rcx
  ISequentialStream *psstrmCallback; // rcx
  IXMLHTTPRequest2Callback *pStatusCallback; // rcx
  IXMLHTTPRequest3Callback *pStatusCallback3; // rcx
  IUri *pUri; // rcx
  INotificationTransportSync *pTransportSync; // rcx
  unsigned __int8 *pbClientCert; // rcx
  CCritSec *pCritSec; // rcx
  void *hStartComplete; // rcx
  HINSTANCE__ *hModule; // rcx

  this->__vftable = (URLMONRequest_vtbl *)URLMONRequest::`vftable';
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0xCu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
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
  pstrmCustom = this->_pstrmCustom;
  if ( pstrmCustom )
  {
    pstrmCustom->Release(pstrmCustom);
    this->_pstrmCustom = 0;
  }
  psstrmCallback = this->_psstrmCallback;
  if ( psstrmCallback )
  {
    psstrmCallback->Release(psstrmCallback);
    this->_psstrmCallback = 0;
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
  pCritSec = this->_pCritSec;
  this->_pbClientCert = 0;
  if ( pCritSec )
  {
    CCritSec::Release(pCritSec);
    this->_pCritSec = 0;
  }
  hStartComplete = this->_hStartComplete;
  if ( hStartComplete )
  {
    CloseHandle(hStartComplete);
    this->_hStartComplete = 0;
  }
  hModule = this->_hModule;
  if ( hModule )
  {
    FreeLibrary(hModule);
    this->_hModule = 0;
  }
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_d(0x403u, 0xDu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
  SecureString::reset(&this->_ssEDPClaim);
  SecureString::reset(&this->_ssProxyPassword);
  SecureString::reset(&this->_ssProxyUserName);
  HTTPHeaders::~HTTPHeaders(&this->_responseHeaders);
  HTTPHeaders::~HTTPHeaders(&this->_requestHeaders);
  URLRequest::~URLRequest(this);
}

```

## disassembly

```asm
0x180086664  mov     [rsp+arg_0], rbx
0x180086669  push    rdi
0x18008666a  sub     rsp, 20h
0x18008666e  lea     rax, ??_7URLMONRequest@@6B@; const URLMONRequest::`vftable'
0x180086675  mov     rbx, this
0x180086678  mov     [this], rax
0x18008667b  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180086682  jz      short loc_18008669D
0x180086684  mov     edx, 0Ch; id
0x180086689  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180086690  mov     ecx, 403h; LevelKeyword
0x180086695  mov     r9, rbx; _a1
0x180086698  call    WPP_SF_q
0x18008669d  mov     this, [rbx+170h]
0x1800866a4  xor     edi, edi
0x1800866a6  test    this, this
0x1800866a9  jz      short loc_1800866BE
0x1800866ab  mov     rax, [this]
0x1800866ae  mov     rax, [rax+10h]
0x1800866b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866b7  mov     [rbx+170h], rdi
0x1800866be  mov     this, [rbx+178h]
0x1800866c5  test    this, this
0x1800866c8  jz      short loc_1800866DD
0x1800866ca  mov     rax, [this]
0x1800866cd  mov     rax, [rax+10h]
0x1800866d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866d6  mov     [rbx+178h], rdi
0x1800866dd  mov     this, [rbx+180h]
0x1800866e4  test    this, this
0x1800866e7  jz      short loc_1800866FC
0x1800866e9  mov     rax, [this]
0x1800866ec  mov     rax, [rax+10h]
0x1800866f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866f5  mov     [rbx+180h], rdi
0x1800866fc  mov     this, [rbx+188h]
0x180086703  test    this, this
0x180086706  jz      short loc_18008671B
0x180086708  mov     rax, [this]
0x18008670b  mov     rax, [rax+10h]
0x18008670f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086714  mov     [rbx+188h], rdi
0x18008671b  mov     this, [rbx+210h]
0x180086722  test    this, this
0x180086725  jz      short loc_18008673A
0x180086727  mov     rax, [this]
0x18008672a  mov     rax, [rax+10h]
0x18008672e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086733  mov     [rbx+210h], rdi
0x18008673a  mov     this, [rbx+218h]
0x180086741  test    this, this
0x180086744  jz      short loc_180086759
0x180086746  mov     rax, [this]
0x180086749  mov     rax, [rax+10h]
0x18008674d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086752  mov     [rbx+218h], rdi
0x180086759  mov     this, [rbx+0C0h]
0x180086760  test    this, this
0x180086763  jz      short loc_180086778
0x180086765  mov     rax, [this]
0x180086768  mov     rax, [rax+10h]
0x18008676c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086771  mov     [rbx+0C0h], rdi
0x180086778  mov     this, [rbx+0C8h]
0x18008677f  mov     [rbx+220h], rdi
0x180086786  test    this, this
0x180086789  jz      short loc_18008679E
0x18008678b  mov     rax, [this]
0x18008678e  mov     rax, [rax+10h]
0x180086792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086797  mov     [rbx+0C8h], rdi
0x18008679e  mov     this, rbx; this
0x1800867a1  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x1800867a6  mov     this, [rbx+1E0h]; pv
0x1800867ad  mov     [rbx+1D8h], edi
0x1800867b3  call    cs:__imp_CoTaskMemFree
0x1800867b9  mov     this, [rbx+2A8h]; this
0x1800867c0  mov     [rbx+1E0h], rdi
0x1800867c7  test    this, this
0x1800867ca  jz      short loc_1800867D8
0x1800867cc  call    ?Release@CCritSec@@QEAAKXZ; CCritSec::Release(void)
0x1800867d1  mov     [rbx+2A8h], rdi
0x1800867d8  mov     this, [rbx+228h]; hObject
0x1800867df  test    this, this
0x1800867e2  jz      short loc_1800867F1
0x1800867e4  call    cs:__imp_CloseHandle
0x1800867ea  mov     [rbx+228h], rdi
0x1800867f1  mov     this, [rbx+230h]; hLibModule
0x1800867f8  test    this, this
0x1800867fb  jz      short loc_18008680A
0x1800867fd  call    cs:__imp_FreeLibrary
0x180086803  mov     [rbx+230h], rdi
0x18008680a  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180086811  jz      short loc_18008682C
0x180086813  mov     edx, 0Dh; id
0x180086818  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18008681f  mov     ecx, 403h; LevelKeyword
0x180086824  xor     r9d, r9d; _a1
0x180086827  call    WPP_SF_d
0x18008682c  lea     this, [rbx+288h]; this
0x180086833  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180086838  lea     this, [rbx+1B8h]; this
0x18008683f  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180086844  lea     this, [rbx+1A0h]; this
0x18008684b  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180086850  lea     this, [rbx+120h]; this
0x180086857  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x18008685c  lea     this, [rbx+0D0h]; this
0x180086863  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x180086868  mov     this, rbx
0x18008686b  mov     rbx, [rsp+28h+arg_0]
0x180086870  add     rsp, 20h
0x180086874  pop     rdi
0x180086875  jmp     ??1URLRequest@@UEAA@XZ; URLRequest::~URLRequest(void)
```
