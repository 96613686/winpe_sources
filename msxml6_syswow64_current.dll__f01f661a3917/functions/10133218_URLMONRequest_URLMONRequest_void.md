# URLMONRequest::~URLMONRequest(void)

- ea: `0x10133218`
- end: `0x101333f9`
- name: `??1URLMONRequest@@UAE@XZ`
- size: `481`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10133400`

## callees

- `0x10067bc0`
- `0x1007de00`
- `0x10130dae`
- `0x10133218`
- `0x1013749b`
- `0x1013b22e`
- `0x1016bc87`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10133393`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10133393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013337c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013337c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133350`

## pseudocode

```c
void __thiscall URLMONRequest::~URLMONRequest(URLMONRequest *this)
{
  IStream *pstrmResponse; // ecx
  ISequentialStream *psstrmSeqResponse; // ecx
  ISequentialStream *pstrmCustom; // ecx
  ISequentialStream *psstrmCallback; // ecx
  IXMLHTTPRequest2Callback *pStatusCallback; // ecx
  IXMLHTTPRequest3Callback *pStatusCallback3; // ecx
  IUri *pUri; // ecx
  INotificationTransportSync *pTransportSync; // ecx
  CCritSec *pCritSec; // ecx
  unsigned __int8 *pbClientCert; // [esp-4h] [ebp-10h]

  this->__vftable = (URLMONRequest_vtbl *)URLMONRequest::`vftable';
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0xCu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  pstrmResponse = this->_pstrmResponse;
  if ( pstrmResponse )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pstrmResponse->Release)(
      pstrmResponse->Release,
      pstrmResponse);
    this->_pstrmResponse = 0;
  }
  psstrmSeqResponse = this->_psstrmSeqResponse;
  if ( psstrmSeqResponse )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))psstrmSeqResponse->Release)(
      psstrmSeqResponse->Release,
      this->_psstrmSeqResponse);
    this->_psstrmSeqResponse = 0;
  }
  pstrmCustom = this->_pstrmCustom;
  if ( pstrmCustom )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))pstrmCustom->Release)(
      pstrmCustom->Release,
      this->_pstrmCustom);
    this->_pstrmCustom = 0;
  }
  psstrmCallback = this->_psstrmCallback;
  if ( psstrmCallback )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))psstrmCallback->Release)(
      psstrmCallback->Release,
      this->_psstrmCallback);
    this->_psstrmCallback = 0;
  }
  pStatusCallback = this->_pStatusCallback;
  if ( pStatusCallback )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IXMLHTTPRequest2Callback *))pStatusCallback->Release)(
      pStatusCallback->Release,
      this->_pStatusCallback);
    this->_pStatusCallback = 0;
  }
  pStatusCallback3 = this->_pStatusCallback3;
  if ( pStatusCallback3 )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IXMLHTTPRequest3Callback *))pStatusCallback3->Release)(
      pStatusCallback3->Release,
      this->_pStatusCallback3);
    this->_pStatusCallback3 = 0;
  }
  pUri = this->_pUri;
  if ( pUri )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUri *))pUri->Release)(pUri->Release, this->_pUri);
    this->_pUri = 0;
  }
  pTransportSync = this->_pTransportSync;
  this->_pXhr2 = 0;
  if ( pTransportSync )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), INotificationTransportSync *))pTransportSync->Release)(
      pTransportSync->Release,
      pTransportSync);
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
  if ( this->_hStartComplete )
  {
    CloseHandle(this->_hStartComplete);
    this->_hStartComplete = 0;
  }
  if ( this->_hModule )
  {
    FreeLibrary(this->_hModule);
    this->_hModule = 0;
  }
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0xDu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
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
0x10133218  mov     edi, edi
0x1013321a  push    ebx
0x1013321b  push    esi
0x1013321c  push    edi
0x1013321d  mov     edi, this
0x1013321f  mov     dword ptr [edi], offset ??_7URLMONRequest@@6B@; const URLMONRequest::`vftable'
0x10133225  test    byte_101857A0, 8; __annotation("TMF:",
0x1013322c  jz      short loc_10133241
0x1013322e  push    edi; _a1
0x1013322f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10133234  push    0Ch
0x10133236  pop     edx; id
0x10133237  mov     this, 403h; LevelKeyword
0x1013323c  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10133241  mov     this, [edi+0CCh]
0x10133247  xor     ebx, ebx
0x10133249  test    this, this
0x1013324b  jz      short loc_10133263
0x1013324d  mov     eax, [this]
0x1013324f  push    this
0x10133250  mov     esi, [eax+8]
0x10133253  mov     this, esi; this
0x10133255  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013325b  call    esi
0x1013325d  mov     [edi+0CCh], ebx
0x10133263  mov     this, [edi+0D0h]
0x10133269  test    this, this
0x1013326b  jz      short loc_10133283
0x1013326d  mov     eax, [this]
0x1013326f  push    this
0x10133270  mov     esi, [eax+8]
0x10133273  mov     this, esi; this
0x10133275  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013327b  call    esi
0x1013327d  mov     [edi+0D0h], ebx
0x10133283  mov     this, [edi+0D4h]
0x10133289  test    this, this
0x1013328b  jz      short loc_101332A3
0x1013328d  mov     eax, [this]
0x1013328f  push    this
0x10133290  mov     esi, [eax+8]
0x10133293  mov     this, esi; this
0x10133295  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013329b  call    esi
0x1013329d  mov     [edi+0D4h], ebx
0x101332a3  mov     this, [edi+0D8h]
0x101332a9  test    this, this
0x101332ab  jz      short loc_101332C3
0x101332ad  mov     eax, [this]
0x101332af  push    this
0x101332b0  mov     esi, [eax+8]
0x101332b3  mov     this, esi; this
0x101332b5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101332bb  call    esi
0x101332bd  mov     [edi+0D8h], ebx
0x101332c3  mov     this, [edi+138h]
0x101332c9  test    this, this
0x101332cb  jz      short loc_101332E3
0x101332cd  mov     eax, [this]
0x101332cf  push    this
0x101332d0  mov     esi, [eax+8]
0x101332d3  mov     this, esi; this
0x101332d5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101332db  call    esi
0x101332dd  mov     [edi+138h], ebx
0x101332e3  mov     this, [edi+13Ch]
0x101332e9  test    this, this
0x101332eb  jz      short loc_10133303
0x101332ed  mov     eax, [this]
0x101332ef  push    this
0x101332f0  mov     esi, [eax+8]
0x101332f3  mov     this, esi; this
0x101332f5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101332fb  call    esi
0x101332fd  mov     [edi+13Ch], ebx
0x10133303  mov     this, [edi+6Ch]
0x10133306  test    this, this
0x10133308  jz      short loc_1013331D
0x1013330a  mov     eax, [this]
0x1013330c  push    this
0x1013330d  mov     esi, [eax+8]
0x10133310  mov     this, esi; this
0x10133312  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133318  call    esi
0x1013331a  mov     [edi+6Ch], ebx
0x1013331d  mov     this, [edi+70h]
0x10133320  mov     [edi+140h], ebx
0x10133326  test    this, this
0x10133328  jz      short loc_1013333D
0x1013332a  mov     eax, [this]
0x1013332c  push    this
0x1013332d  mov     esi, [eax+8]
0x10133330  mov     this, esi; this
0x10133332  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133338  call    esi
0x1013333a  mov     [edi+70h], ebx
0x1013333d  mov     this, edi; this
0x1013333f  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10133344  push    dword ptr [edi+110h]; pv
0x1013334a  mov     [edi+10Ch], ebx
0x10133350  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10133356  mov     this, [edi+1A0h]; this
0x1013335c  mov     [edi+110h], ebx
0x10133362  test    this, this
0x10133364  jz      short loc_10133371
0x10133366  call    ?Release@CCritSec@@QAEKXZ; CCritSec::Release(void)
0x1013336b  mov     [edi+1A0h], ebx
0x10133371  mov     eax, [edi+144h]
0x10133377  test    eax, eax
0x10133379  jz      short loc_10133388
0x1013337b  push    eax; hObject
0x1013337c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10133382  mov     [edi+144h], ebx
0x10133388  mov     eax, [edi+148h]
0x1013338e  test    eax, eax
0x10133390  jz      short loc_1013339F
0x10133392  push    eax; hLibModule
0x10133393  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10133399  mov     [edi+148h], ebx
0x1013339f  test    byte_101857A0, 8; __annotation("TMF:",
0x101333a6  jz      short loc_101333BB
0x101333a8  push    ebx; _a1
0x101333a9  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101333ae  push    0Dh
0x101333b0  pop     edx; id
0x101333b1  mov     this, 403h; LevelKeyword
0x101333b6  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101333bb  lea     this, [edi+190h]; this
0x101333c1  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101333c6  lea     this, [edi+0F8h]; this
0x101333cc  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101333d1  lea     this, [edi+0ECh]; this
0x101333d7  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101333dc  lea     this, [edi+0A0h]; this
0x101333e2  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x101333e7  lea     this, [edi+74h]; this
0x101333ea  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x101333ef  mov     this, edi; this
0x101333f1  pop     edi
0x101333f2  pop     esi
0x101333f3  pop     ebx
0x101333f4  jmp     ??1URLRequest@@UAE@XZ; URLRequest::~URLRequest(void)
```
