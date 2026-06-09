# URLMONRequest::~URLMONRequest(void)

- ea: `0x10133328`
- end: `0x10133509`
- name: `??1URLMONRequest@@UAE@XZ`
- size: `481`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10133510`

## callees

- `0x10067b20`
- `0x1007de40`
- `0x10130ebe`
- `0x10133328`
- `0x101375ab`
- `0x1013b33e`
- `0x1016bd77`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101334a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101334a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013348c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013348c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10133460`

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
  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[0] & 8) != 0 )
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
0x10133328  mov     edi, edi
0x1013332a  push    ebx
0x1013332b  push    esi
0x1013332c  push    edi
0x1013332d  mov     edi, this
0x1013332f  mov     dword ptr [edi], offset ??_7URLMONRequest@@6B@; const URLMONRequest::`vftable'
0x10133335  test    byte_10185760, 8; __annotation("TMF:",
0x1013333c  jz      short loc_10133351
0x1013333e  push    edi; _a1
0x1013333f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10133344  push    0Ch
0x10133346  pop     edx; id
0x10133347  mov     this, 403h; LevelKeyword
0x1013334c  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10133351  mov     this, [edi+0CCh]
0x10133357  xor     ebx, ebx
0x10133359  test    this, this
0x1013335b  jz      short loc_10133373
0x1013335d  mov     eax, [this]
0x1013335f  push    this
0x10133360  mov     esi, [eax+8]
0x10133363  mov     this, esi; this
0x10133365  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013336b  call    esi
0x1013336d  mov     [edi+0CCh], ebx
0x10133373  mov     this, [edi+0D0h]
0x10133379  test    this, this
0x1013337b  jz      short loc_10133393
0x1013337d  mov     eax, [this]
0x1013337f  push    this
0x10133380  mov     esi, [eax+8]
0x10133383  mov     this, esi; this
0x10133385  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013338b  call    esi
0x1013338d  mov     [edi+0D0h], ebx
0x10133393  mov     this, [edi+0D4h]
0x10133399  test    this, this
0x1013339b  jz      short loc_101333B3
0x1013339d  mov     eax, [this]
0x1013339f  push    this
0x101333a0  mov     esi, [eax+8]
0x101333a3  mov     this, esi; this
0x101333a5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101333ab  call    esi
0x101333ad  mov     [edi+0D4h], ebx
0x101333b3  mov     this, [edi+0D8h]
0x101333b9  test    this, this
0x101333bb  jz      short loc_101333D3
0x101333bd  mov     eax, [this]
0x101333bf  push    this
0x101333c0  mov     esi, [eax+8]
0x101333c3  mov     this, esi; this
0x101333c5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101333cb  call    esi
0x101333cd  mov     [edi+0D8h], ebx
0x101333d3  mov     this, [edi+138h]
0x101333d9  test    this, this
0x101333db  jz      short loc_101333F3
0x101333dd  mov     eax, [this]
0x101333df  push    this
0x101333e0  mov     esi, [eax+8]
0x101333e3  mov     this, esi; this
0x101333e5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101333eb  call    esi
0x101333ed  mov     [edi+138h], ebx
0x101333f3  mov     this, [edi+13Ch]
0x101333f9  test    this, this
0x101333fb  jz      short loc_10133413
0x101333fd  mov     eax, [this]
0x101333ff  push    this
0x10133400  mov     esi, [eax+8]
0x10133403  mov     this, esi; this
0x10133405  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013340b  call    esi
0x1013340d  mov     [edi+13Ch], ebx
0x10133413  mov     this, [edi+6Ch]
0x10133416  test    this, this
0x10133418  jz      short loc_1013342D
0x1013341a  mov     eax, [this]
0x1013341c  push    this
0x1013341d  mov     esi, [eax+8]
0x10133420  mov     this, esi; this
0x10133422  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133428  call    esi
0x1013342a  mov     [edi+6Ch], ebx
0x1013342d  mov     this, [edi+70h]
0x10133430  mov     [edi+140h], ebx
0x10133436  test    this, this
0x10133438  jz      short loc_1013344D
0x1013343a  mov     eax, [this]
0x1013343c  push    this
0x1013343d  mov     esi, [eax+8]
0x10133440  mov     this, esi; this
0x10133442  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133448  call    esi
0x1013344a  mov     [edi+70h], ebx
0x1013344d  mov     this, edi; this
0x1013344f  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10133454  push    dword ptr [edi+110h]; pv
0x1013345a  mov     [edi+10Ch], ebx
0x10133460  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10133466  mov     this, [edi+1A0h]; this
0x1013346c  mov     [edi+110h], ebx
0x10133472  test    this, this
0x10133474  jz      short loc_10133481
0x10133476  call    ?Release@CCritSec@@QAEKXZ; CCritSec::Release(void)
0x1013347b  mov     [edi+1A0h], ebx
0x10133481  mov     eax, [edi+144h]
0x10133487  test    eax, eax
0x10133489  jz      short loc_10133498
0x1013348b  push    eax; hObject
0x1013348c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10133492  mov     [edi+144h], ebx
0x10133498  mov     eax, [edi+148h]
0x1013349e  test    eax, eax
0x101334a0  jz      short loc_101334AF
0x101334a2  push    eax; hLibModule
0x101334a3  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x101334a9  mov     [edi+148h], ebx
0x101334af  test    byte_10185760, 8; __annotation("TMF:",
0x101334b6  jz      short loc_101334CB
0x101334b8  push    ebx; _a1
0x101334b9  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101334be  push    0Dh
0x101334c0  pop     edx; id
0x101334c1  mov     this, 403h; LevelKeyword
0x101334c6  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101334cb  lea     this, [edi+190h]; this
0x101334d1  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101334d6  lea     this, [edi+0F8h]; this
0x101334dc  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101334e1  lea     this, [edi+0ECh]; this
0x101334e7  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x101334ec  lea     this, [edi+0A0h]; this
0x101334f2  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x101334f7  lea     this, [edi+74h]; this
0x101334fa  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x101334ff  mov     this, edi; this
0x10133501  pop     edi
0x10133502  pop     esi
0x10133503  pop     ebx
0x10133504  jmp     ??1URLRequest@@UAE@XZ; URLRequest::~URLRequest(void)
```
