# URLMONRequest::recycle(void)

- ea: `0x10139a70`
- end: `0x10139d2b`
- name: `?recycle@URLMONRequest@@UAEXXZ`
- size: `699`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x10067bc0`
- `0x1006b8c3`
- `0x1007ebe4`
- `0x1013749b`
- `0x10139a70`
- `0x1013c5d0`
- `0x1016bc87`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10139cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10139cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10139c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10139c30`

## pseudocode

```c
void __thiscall URLMONRequest::recycle(URLMONRequest *this)
{
  IStream *pstrmResponse; // ecx
  ISequentialStream *psstrmSeqResponse; // ecx
  ISequentialStream *psstrmCallback; // ecx
  ISequentialStream *pstrmCustom; // ecx
  IXMLHTTPRequest2Callback *pStatusCallback; // ecx
  IXMLHTTPRequest3Callback *pStatusCallback3; // ecx
  IUri *pUri; // ecx
  INotificationTransportSync *pTransportSync; // ecx
  IInternetProtocol *pIInternetProtocol; // ecx
  void *hStartComplete; // eax
  URLMONRequest_vtbl *v12; // eax
  wchar_t *pwszResult; // [esp-8h] [ebp-18h]
  unsigned __int8 *pbClientCert; // [esp-4h] [ebp-14h]
  char v15; // [esp+Fh] [ebp-1h]

  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x22u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  this->Lock(this);
  if ( this->_fAborted || (v15 = 0, this->_fAbortPending) )
    v15 = 1;
  URLRequest::recycle(this);
  HTTPHeaders::reset(&this->_requestHeaders);
  HTTPHeaders::reset(&this->_responseHeaders);
  *(_DWORD *)&this->_fEndOfStream = 0;
  this->_dwAuth = 0;
  this->_dwTimeout = 0;
  *(_WORD *)&this->_fProxyUserNameAndPassword = 0;
  *(_WORD *)&this->_fNoCache = 0;
  this->_fQueryStringInUtf8 = 0;
  this->_dwIgnoreCertMask = 0;
  SecureString::reset(&this->_ssProxyPassword);
  SecureString::reset(&this->_ssProxyUserName);
  pstrmResponse = this->_pstrmResponse;
  if ( pstrmResponse )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pstrmResponse->Release)(
      pstrmResponse->Release,
      this->_pstrmResponse);
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
  psstrmCallback = this->_psstrmCallback;
  if ( psstrmCallback )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))psstrmCallback->Release)(
      psstrmCallback->Release,
      this->_psstrmCallback);
    this->_psstrmCallback = 0;
  }
  pstrmCustom = this->_pstrmCustom;
  if ( pstrmCustom )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))pstrmCustom->Release)(
      pstrmCustom->Release,
      this->_pstrmCustom);
    this->_pstrmCustom = 0;
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
  this->_pbClientCert = 0;
  this->_fBindStatusUsingCachedCopy = 0;
  this->_fInvokedCallOnServerCert = 0;
  this->_fInvokedCallOnClientCert = 0;
  if ( !v15 )
  {
    pIInternetProtocol = this->_pIInternetProtocol;
    if ( pIInternetProtocol )
    {
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IInternetProtocol *))pIInternetProtocol->Release)(
        pIInternetProtocol->Release,
        this->_pIInternetProtocol);
      this->_pIInternetProtocol = 0;
    }
  }
  pwszResult = this->_PendingResultCallback.pwszResult;
  this->_dwError = 0;
  this->_dwUrlmonCallbackThread = 0;
  this->_dwPendingDataCallback = 0;
  operator delete(pwszResult, (const std::nothrow_t *)2);
  this->_PendingResultCallback.fPending = 0;
  this->_PendingResultCallback.hrResult = 0;
  this->_PendingResultCallback.dwError = 0;
  this->_PendingResultCallback.pwszResult = 0;
  hStartComplete = this->_hStartComplete;
  this->_fFinished = 0;
  this->_fHTTPS = 0;
  this->_fDropConnectBody = 0;
  if ( hStartComplete )
  {
    CloseHandle(hStartComplete);
    this->_hStartComplete = 0;
  }
  LODWORD(this->_ullOnDataThreshold) = 0;
  HIDWORD(this->_ullOnDataThreshold) = 0;
  LODWORD(this->_ullDataSinceOnData) = 0;
  HIDWORD(this->_ullDataSinceOnData) = 0;
  SecureString::reset(&this->_ssEDPClaim);
  v12 = this->__vftable;
  this->_dwMaxConns = 0;
  v12->Unlock(this);
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x23u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x10139a70  mov     edi, edi
0x10139a72  push    ebp
0x10139a73  mov     ebp, esp
0x10139a75  push    this
0x10139a76  push    ebx
0x10139a77  push    esi
0x10139a78  push    edi
0x10139a79  mov     ebx, this
0x10139a7b  test    byte_101857A0, 8; __annotation("TMF:",
0x10139a82  jz      short loc_10139A97
0x10139a84  push    ebx; _a1
0x10139a85  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139a8a  push    22h ; '"'
0x10139a8c  pop     edx; id
0x10139a8d  mov     this, 403h; LevelKeyword
0x10139a92  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139a97  mov     eax, [ebx]
0x10139a99  mov     esi, [eax+7Ch]
0x10139a9c  mov     this, esi; this
0x10139a9e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139aa4  mov     this, ebx
0x10139aa6  call    esi
0x10139aa8  cmp     byte ptr [ebx+0Ah], 0
0x10139aac  jnz     short loc_10139ABB
0x10139aae  cmp     dword ptr [ebx+168h], 0
0x10139ab5  mov     [ebp+var_1], 0
0x10139ab9  jz      short loc_10139ABF
0x10139abb  mov     [ebp+var_1], 1
0x10139abf  mov     this, ebx; this
0x10139ac1  call    ?recycle@URLRequest@@UAEXXZ; URLRequest::recycle(void)
0x10139ac6  lea     this, [ebx+74h]; this
0x10139ac9  call    ?reset@HTTPHeaders@@QAEXXZ; HTTPHeaders::reset(void)
0x10139ace  lea     this, [ebx+0A0h]; this
0x10139ad4  call    ?reset@HTTPHeaders@@QAEXXZ; HTTPHeaders::reset(void)
0x10139ad9  xor     eax, eax
0x10139adb  lea     this, [ebx+0F8h]; this
0x10139ae1  mov     [ebx+0E0h], eax
0x10139ae7  mov     [ebx+0DCh], eax
0x10139aed  mov     [ebx+104h], eax
0x10139af3  mov     [ebx+0E7h], ax
0x10139afa  mov     [ebx+0E4h], ax
0x10139b01  mov     [ebx+0E6h], al
0x10139b07  mov     [ebx+108h], eax
0x10139b0d  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139b12  lea     this, [ebx+0ECh]; this
0x10139b18  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139b1d  mov     this, [ebx+0CCh]
0x10139b23  test    this, this
0x10139b25  jz      short loc_10139B41
0x10139b27  mov     eax, [this]
0x10139b29  push    this
0x10139b2a  mov     esi, [eax+8]
0x10139b2d  mov     this, esi; this
0x10139b2f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139b35  call    esi
0x10139b37  xor     edi, edi
0x10139b39  mov     [ebx+0CCh], edi
0x10139b3f  jmp     short loc_10139B43
0x10139b41  xor     edi, edi
0x10139b43  mov     this, [ebx+0D0h]
0x10139b49  test    this, this
0x10139b4b  jz      short loc_10139B63
0x10139b4d  mov     eax, [this]
0x10139b4f  push    this
0x10139b50  mov     esi, [eax+8]
0x10139b53  mov     this, esi; this
0x10139b55  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139b5b  call    esi
0x10139b5d  mov     [ebx+0D0h], edi
0x10139b63  mov     this, [ebx+0D8h]
0x10139b69  test    this, this
0x10139b6b  jz      short loc_10139B83
0x10139b6d  mov     eax, [this]
0x10139b6f  push    this
0x10139b70  mov     esi, [eax+8]
0x10139b73  mov     this, esi; this
0x10139b75  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139b7b  call    esi
0x10139b7d  mov     [ebx+0D8h], edi
0x10139b83  mov     this, [ebx+0D4h]
0x10139b89  test    this, this
0x10139b8b  jz      short loc_10139BA3
0x10139b8d  mov     eax, [this]
0x10139b8f  push    this
0x10139b90  mov     esi, [eax+8]
0x10139b93  mov     this, esi; this
0x10139b95  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139b9b  call    esi
0x10139b9d  mov     [ebx+0D4h], edi
0x10139ba3  mov     this, [ebx+138h]
0x10139ba9  test    this, this
0x10139bab  jz      short loc_10139BC3
0x10139bad  mov     eax, [this]
0x10139baf  push    this
0x10139bb0  mov     esi, [eax+8]
0x10139bb3  mov     this, esi; this
0x10139bb5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139bbb  call    esi
0x10139bbd  mov     [ebx+138h], edi
0x10139bc3  mov     this, [ebx+13Ch]
0x10139bc9  test    this, this
0x10139bcb  jz      short loc_10139BE3
0x10139bcd  mov     eax, [this]
0x10139bcf  push    this
0x10139bd0  mov     esi, [eax+8]
0x10139bd3  mov     this, esi; this
0x10139bd5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139bdb  call    esi
0x10139bdd  mov     [ebx+13Ch], edi
0x10139be3  mov     this, [ebx+6Ch]
0x10139be6  test    this, this
0x10139be8  jz      short loc_10139BFD
0x10139bea  mov     eax, [this]
0x10139bec  push    this
0x10139bed  mov     esi, [eax+8]
0x10139bf0  mov     this, esi; this
0x10139bf2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139bf8  call    esi
0x10139bfa  mov     [ebx+6Ch], edi
0x10139bfd  mov     this, [ebx+70h]
0x10139c00  mov     [ebx+140h], edi
0x10139c06  test    this, this
0x10139c08  jz      short loc_10139C1D
0x10139c0a  mov     eax, [this]
0x10139c0c  push    this
0x10139c0d  mov     esi, [eax+8]
0x10139c10  mov     this, esi; this
0x10139c12  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139c18  call    esi
0x10139c1a  mov     [ebx+70h], edi
0x10139c1d  mov     this, ebx; this
0x10139c1f  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10139c24  push    dword ptr [ebx+110h]; pv
0x10139c2a  mov     [ebx+10Ch], edi
0x10139c30  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10139c36  xor     eax, eax
0x10139c38  mov     [ebx+110h], eax
0x10139c3e  mov     [ebx+114h], eax
0x10139c44  mov     [ebx+178h], eax
0x10139c4a  mov     [ebx+17Ch], eax
0x10139c50  cmp     [ebp+var_1], al
0x10139c53  jnz     short loc_10139C71
0x10139c55  mov     this, [ebx+68h]
0x10139c58  test    this, this
0x10139c5a  jz      short loc_10139C71
0x10139c5c  mov     eax, [this]
0x10139c5e  push    this
0x10139c5f  mov     esi, [eax+8]
0x10139c62  mov     this, esi; this
0x10139c64  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139c6a  call    esi
0x10139c6c  xor     eax, eax
0x10139c6e  mov     [ebx+68h], eax
0x10139c71  push    2; __formal
0x10139c73  push    dword ptr [ebx+15Ch]; block
0x10139c79  mov     [ebx+11Ch], eax
0x10139c7f  mov     [ebx+160h], eax
0x10139c85  mov     [ebx+14Ch], eax
0x10139c8b  call    ??3@YAXPAXABUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x10139c90  xor     eax, eax
0x10139c92  lea     edi, [ebx+150h]
0x10139c98  stosd
0x10139c99  pop     this
0x10139c9a  pop     this
0x10139c9b  xor     this, this
0x10139c9d  stosd
0x10139c9e  stosd
0x10139c9f  stosd
0x10139ca0  mov     eax, [ebx+144h]
0x10139ca6  mov     [ebx+0E9h], cl
0x10139cac  mov     [ebx+170h], this
0x10139cb2  mov     [ebx+174h], this
0x10139cb8  test    eax, eax
0x10139cba  jz      short loc_10139CCB
0x10139cbc  push    eax; hObject
0x10139cbd  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10139cc3  xor     this, this
0x10139cc5  mov     [ebx+144h], this
0x10139ccb  mov     [ebx+180h], this
0x10139cd1  mov     [ebx+184h], this
0x10139cd7  mov     [ebx+188h], this
0x10139cdd  mov     [ebx+18Ch], this
0x10139ce3  lea     this, [ebx+190h]; this
0x10139ce9  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139cee  mov     eax, [ebx]
0x10139cf0  xor     edi, edi
0x10139cf2  mov     [ebx+19Ch], edi
0x10139cf8  mov     esi, [eax+80h]
0x10139cfe  mov     this, esi; this
0x10139d00  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139d06  mov     this, ebx
0x10139d08  call    esi
0x10139d0a  test    byte_101857A0, 8; __annotation("TMF:",
0x10139d11  jz      short loc_10139D26
0x10139d13  push    edi; _a1
0x10139d14  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139d19  push    23h ; '#'
0x10139d1b  pop     edx; id
0x10139d1c  mov     this, 403h; LevelKeyword
0x10139d21  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139d26  pop     edi
0x10139d27  pop     esi
0x10139d28  pop     ebx
0x10139d29  leave
0x10139d2a  retn
```
