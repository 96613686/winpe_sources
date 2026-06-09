# URLMONRequest::~URLMONRequest(void)

- ea: `0x180084d74`
- end: `0x180084f9c`
- name: `??1URLMONRequest@@UEAA@XZ`
- size: `552`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180158af0`

## callees

- `0x180084d74`
- `0x180084fa4`
- `0x180084fe4`
- `0x1800bdad4`
- `0x1800bdb84`
- `0x1800c5394`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180084f19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180084f19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084efa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ec3`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
0x180084d74  mov     [rsp+arg_0], rbx
0x180084d79  push    rdi
0x180084d7a  sub     rsp, 20h
0x180084d7e  lea     rax, ??_7URLMONRequest@@6B@; const URLMONRequest::`vftable'
0x180084d85  mov     rbx, this
0x180084d88  mov     [this], rax
0x180084d8b  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180084d92  jz      short loc_180084DAD
0x180084d94  mov     edx, 0Ch; id
0x180084d99  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180084da0  mov     ecx, 403h; LevelKeyword
0x180084da5  mov     r9, rbx; _a1
0x180084da8  call    WPP_SF_q
0x180084dad  mov     this, [rbx+170h]
0x180084db4  xor     edi, edi
0x180084db6  test    this, this
0x180084db9  jz      short loc_180084DCE
0x180084dbb  mov     rax, [this]
0x180084dbe  mov     rax, [rax+10h]
0x180084dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084dc7  mov     [rbx+170h], rdi
0x180084dce  mov     this, [rbx+178h]
0x180084dd5  test    this, this
0x180084dd8  jz      short loc_180084DED
0x180084dda  mov     rax, [this]
0x180084ddd  mov     rax, [rax+10h]
0x180084de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084de6  mov     [rbx+178h], rdi
0x180084ded  mov     this, [rbx+180h]
0x180084df4  test    this, this
0x180084df7  jz      short loc_180084E0C
0x180084df9  mov     rax, [this]
0x180084dfc  mov     rax, [rax+10h]
0x180084e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e05  mov     [rbx+180h], rdi
0x180084e0c  mov     this, [rbx+188h]
0x180084e13  test    this, this
0x180084e16  jz      short loc_180084E2B
0x180084e18  mov     rax, [this]
0x180084e1b  mov     rax, [rax+10h]
0x180084e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e24  mov     [rbx+188h], rdi
0x180084e2b  mov     this, [rbx+210h]
0x180084e32  test    this, this
0x180084e35  jz      short loc_180084E4A
0x180084e37  mov     rax, [this]
0x180084e3a  mov     rax, [rax+10h]
0x180084e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e43  mov     [rbx+210h], rdi
0x180084e4a  mov     this, [rbx+218h]
0x180084e51  test    this, this
0x180084e54  jz      short loc_180084E69
0x180084e56  mov     rax, [this]
0x180084e59  mov     rax, [rax+10h]
0x180084e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e62  mov     [rbx+218h], rdi
0x180084e69  mov     this, [rbx+0C0h]
0x180084e70  test    this, this
0x180084e73  jz      short loc_180084E88
0x180084e75  mov     rax, [this]
0x180084e78  mov     rax, [rax+10h]
0x180084e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e81  mov     [rbx+0C0h], rdi
0x180084e88  mov     this, [rbx+0C8h]
0x180084e8f  mov     [rbx+220h], rdi
0x180084e96  test    this, this
0x180084e99  jz      short loc_180084EAE
0x180084e9b  mov     rax, [this]
0x180084e9e  mov     rax, [rax+10h]
0x180084ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ea7  mov     [rbx+0C8h], rdi
0x180084eae  mov     this, rbx; this
0x180084eb1  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x180084eb6  mov     this, [rbx+1E0h]; pv
0x180084ebd  mov     [rbx+1D8h], edi
0x180084ec3  call    cs:__imp_CoTaskMemFree
0x180084eca  nop     dword ptr [rax+rax+00h]
0x180084ecf  mov     this, [rbx+2A8h]; this
0x180084ed6  mov     [rbx+1E0h], rdi
0x180084edd  test    this, this
0x180084ee0  jz      short loc_180084EEE
0x180084ee2  call    ?Release@CCritSec@@QEAAKXZ; CCritSec::Release(void)
0x180084ee7  mov     [rbx+2A8h], rdi
0x180084eee  mov     this, [rbx+228h]; hObject
0x180084ef5  test    this, this
0x180084ef8  jz      short loc_180084F0D
0x180084efa  call    cs:__imp_CloseHandle
0x180084f01  nop     dword ptr [rax+rax+00h]
0x180084f06  mov     [rbx+228h], rdi
0x180084f0d  mov     this, [rbx+230h]; hLibModule
0x180084f14  test    this, this
0x180084f17  jz      short loc_180084F2C
0x180084f19  call    cs:__imp_FreeLibrary
0x180084f20  nop     dword ptr [rax+rax+00h]
0x180084f25  mov     [rbx+230h], rdi
0x180084f2c  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180084f33  jz      short loc_180084F4E
0x180084f35  mov     edx, 0Dh; id
0x180084f3a  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180084f41  mov     ecx, 403h; LevelKeyword
0x180084f46  xor     r9d, r9d; _a1
0x180084f49  call    WPP_SF_d
0x180084f4e  lea     this, [rbx+288h]; this
0x180084f55  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180084f5a  lea     this, [rbx+1B8h]; this
0x180084f61  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180084f66  lea     this, [rbx+1A0h]; this
0x180084f6d  call    ?reset@SecureString@@QEAAXXZ; SecureString::reset(void)
0x180084f72  lea     this, [rbx+120h]; this
0x180084f79  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x180084f7e  lea     this, [rbx+0D0h]; this
0x180084f85  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x180084f8a  mov     this, rbx
0x180084f8d  mov     rbx, [rsp+28h+arg_0]
0x180084f92  add     rsp, 20h
0x180084f96  pop     rdi
0x180084f97  jmp     ??1URLRequest@@UEAA@XZ; URLRequest::~URLRequest(void)
```
