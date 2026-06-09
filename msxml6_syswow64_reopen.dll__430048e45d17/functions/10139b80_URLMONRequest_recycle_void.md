# URLMONRequest::recycle(void)

- ea: `0x10139b80`
- end: `0x10139e3b`
- name: `?recycle@URLMONRequest@@UAEXXZ`
- size: `699`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x10067b20`
- `0x1006b823`
- `0x1007ec24`
- `0x101375ab`
- `0x10139b80`
- `0x1013c6e0`
- `0x1016bd77`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10139dcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10139dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10139d40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10139d40`

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

  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x23u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x10139b80  mov     edi, edi
0x10139b82  push    ebp
0x10139b83  mov     ebp, esp
0x10139b85  push    this
0x10139b86  push    ebx
0x10139b87  push    esi
0x10139b88  push    edi
0x10139b89  mov     ebx, this
0x10139b8b  test    byte_10185760, 8; __annotation("TMF:",
0x10139b92  jz      short loc_10139BA7
0x10139b94  push    ebx; _a1
0x10139b95  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139b9a  push    22h ; '"'
0x10139b9c  pop     edx; id
0x10139b9d  mov     this, 403h; LevelKeyword
0x10139ba2  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139ba7  mov     eax, [ebx]
0x10139ba9  mov     esi, [eax+7Ch]
0x10139bac  mov     this, esi; this
0x10139bae  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139bb4  mov     this, ebx
0x10139bb6  call    esi
0x10139bb8  cmp     byte ptr [ebx+0Ah], 0
0x10139bbc  jnz     short loc_10139BCB
0x10139bbe  cmp     dword ptr [ebx+168h], 0
0x10139bc5  mov     [ebp+var_1], 0
0x10139bc9  jz      short loc_10139BCF
0x10139bcb  mov     [ebp+var_1], 1
0x10139bcf  mov     this, ebx; this
0x10139bd1  call    ?recycle@URLRequest@@UAEXXZ; URLRequest::recycle(void)
0x10139bd6  lea     this, [ebx+74h]; this
0x10139bd9  call    ?reset@HTTPHeaders@@QAEXXZ; HTTPHeaders::reset(void)
0x10139bde  lea     this, [ebx+0A0h]; this
0x10139be4  call    ?reset@HTTPHeaders@@QAEXXZ; HTTPHeaders::reset(void)
0x10139be9  xor     eax, eax
0x10139beb  lea     this, [ebx+0F8h]; this
0x10139bf1  mov     [ebx+0E0h], eax
0x10139bf7  mov     [ebx+0DCh], eax
0x10139bfd  mov     [ebx+104h], eax
0x10139c03  mov     [ebx+0E7h], ax
0x10139c0a  mov     [ebx+0E4h], ax
0x10139c11  mov     [ebx+0E6h], al
0x10139c17  mov     [ebx+108h], eax
0x10139c1d  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139c22  lea     this, [ebx+0ECh]; this
0x10139c28  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139c2d  mov     this, [ebx+0CCh]
0x10139c33  test    this, this
0x10139c35  jz      short loc_10139C51
0x10139c37  mov     eax, [this]
0x10139c39  push    this
0x10139c3a  mov     esi, [eax+8]
0x10139c3d  mov     this, esi; this
0x10139c3f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139c45  call    esi
0x10139c47  xor     edi, edi
0x10139c49  mov     [ebx+0CCh], edi
0x10139c4f  jmp     short loc_10139C53
0x10139c51  xor     edi, edi
0x10139c53  mov     this, [ebx+0D0h]
0x10139c59  test    this, this
0x10139c5b  jz      short loc_10139C73
0x10139c5d  mov     eax, [this]
0x10139c5f  push    this
0x10139c60  mov     esi, [eax+8]
0x10139c63  mov     this, esi; this
0x10139c65  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139c6b  call    esi
0x10139c6d  mov     [ebx+0D0h], edi
0x10139c73  mov     this, [ebx+0D8h]
0x10139c79  test    this, this
0x10139c7b  jz      short loc_10139C93
0x10139c7d  mov     eax, [this]
0x10139c7f  push    this
0x10139c80  mov     esi, [eax+8]
0x10139c83  mov     this, esi; this
0x10139c85  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139c8b  call    esi
0x10139c8d  mov     [ebx+0D8h], edi
0x10139c93  mov     this, [ebx+0D4h]
0x10139c99  test    this, this
0x10139c9b  jz      short loc_10139CB3
0x10139c9d  mov     eax, [this]
0x10139c9f  push    this
0x10139ca0  mov     esi, [eax+8]
0x10139ca3  mov     this, esi; this
0x10139ca5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139cab  call    esi
0x10139cad  mov     [ebx+0D4h], edi
0x10139cb3  mov     this, [ebx+138h]
0x10139cb9  test    this, this
0x10139cbb  jz      short loc_10139CD3
0x10139cbd  mov     eax, [this]
0x10139cbf  push    this
0x10139cc0  mov     esi, [eax+8]
0x10139cc3  mov     this, esi; this
0x10139cc5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139ccb  call    esi
0x10139ccd  mov     [ebx+138h], edi
0x10139cd3  mov     this, [ebx+13Ch]
0x10139cd9  test    this, this
0x10139cdb  jz      short loc_10139CF3
0x10139cdd  mov     eax, [this]
0x10139cdf  push    this
0x10139ce0  mov     esi, [eax+8]
0x10139ce3  mov     this, esi; this
0x10139ce5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139ceb  call    esi
0x10139ced  mov     [ebx+13Ch], edi
0x10139cf3  mov     this, [ebx+6Ch]
0x10139cf6  test    this, this
0x10139cf8  jz      short loc_10139D0D
0x10139cfa  mov     eax, [this]
0x10139cfc  push    this
0x10139cfd  mov     esi, [eax+8]
0x10139d00  mov     this, esi; this
0x10139d02  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139d08  call    esi
0x10139d0a  mov     [ebx+6Ch], edi
0x10139d0d  mov     this, [ebx+70h]
0x10139d10  mov     [ebx+140h], edi
0x10139d16  test    this, this
0x10139d18  jz      short loc_10139D2D
0x10139d1a  mov     eax, [this]
0x10139d1c  push    this
0x10139d1d  mov     esi, [eax+8]
0x10139d20  mov     this, esi; this
0x10139d22  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139d28  call    esi
0x10139d2a  mov     [ebx+70h], edi
0x10139d2d  mov     this, ebx; this
0x10139d2f  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10139d34  push    dword ptr [ebx+110h]; pv
0x10139d3a  mov     [ebx+10Ch], edi
0x10139d40  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10139d46  xor     eax, eax
0x10139d48  mov     [ebx+110h], eax
0x10139d4e  mov     [ebx+114h], eax
0x10139d54  mov     [ebx+178h], eax
0x10139d5a  mov     [ebx+17Ch], eax
0x10139d60  cmp     [ebp+var_1], al
0x10139d63  jnz     short loc_10139D81
0x10139d65  mov     this, [ebx+68h]
0x10139d68  test    this, this
0x10139d6a  jz      short loc_10139D81
0x10139d6c  mov     eax, [this]
0x10139d6e  push    this
0x10139d6f  mov     esi, [eax+8]
0x10139d72  mov     this, esi; this
0x10139d74  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139d7a  call    esi
0x10139d7c  xor     eax, eax
0x10139d7e  mov     [ebx+68h], eax
0x10139d81  push    2; __formal
0x10139d83  push    dword ptr [ebx+15Ch]; block
0x10139d89  mov     [ebx+11Ch], eax
0x10139d8f  mov     [ebx+160h], eax
0x10139d95  mov     [ebx+14Ch], eax
0x10139d9b  call    ??3@YAXPAXABUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x10139da0  xor     eax, eax
0x10139da2  lea     edi, [ebx+150h]
0x10139da8  stosd
0x10139da9  pop     this
0x10139daa  pop     this
0x10139dab  xor     this, this
0x10139dad  stosd
0x10139dae  stosd
0x10139daf  stosd
0x10139db0  mov     eax, [ebx+144h]
0x10139db6  mov     [ebx+0E9h], cl
0x10139dbc  mov     [ebx+170h], this
0x10139dc2  mov     [ebx+174h], this
0x10139dc8  test    eax, eax
0x10139dca  jz      short loc_10139DDB
0x10139dcc  push    eax; hObject
0x10139dcd  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10139dd3  xor     this, this
0x10139dd5  mov     [ebx+144h], this
0x10139ddb  mov     [ebx+180h], this
0x10139de1  mov     [ebx+184h], this
0x10139de7  mov     [ebx+188h], this
0x10139ded  mov     [ebx+18Ch], this
0x10139df3  lea     this, [ebx+190h]; this
0x10139df9  call    ?reset@SecureString@@QAEXXZ; SecureString::reset(void)
0x10139dfe  mov     eax, [ebx]
0x10139e00  xor     edi, edi
0x10139e02  mov     [ebx+19Ch], edi
0x10139e08  mov     esi, [eax+80h]
0x10139e0e  mov     this, esi; this
0x10139e10  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139e16  mov     this, ebx
0x10139e18  call    esi
0x10139e1a  test    byte_10185760, 8; __annotation("TMF:",
0x10139e21  jz      short loc_10139E36
0x10139e23  push    edi; _a1
0x10139e24  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139e29  push    23h ; '#'
0x10139e2b  pop     edx; id
0x10139e2c  mov     this, 403h; LevelKeyword
0x10139e31  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139e36  pop     edi
0x10139e37  pop     esi
0x10139e38  pop     ebx
0x10139e39  leave
0x10139e3a  retn
```
