# HTTPRequest::_onResponseDataAvailable(tagSAFEARRAY * *)

- ea: `0x10131c7d`
- end: `0x10131d5f`
- name: `?_onResponseDataAvailable@HTTPRequest@@IAEXPAPAUtagSAFEARRAY@@@Z`
- size: `226`
- prototype: `void __thiscall(HTTPRequest *this, tagSAFEARRAY **ppsaData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10131aa0`

## callees

- `0x1005064c`
- `0x10067bc0`
- `0x10131c7d`
- `0x10131d65`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x10131cf4`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x10131cf4`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x10131ce3`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x10131ce3`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10131ccf`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10131ccf`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10131d49`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10131d49`

## pseudocode

```c
void __thiscall HTTPRequest::_onResponseDataAvailable(HTTPRequest *this, tagSAFEARRAY **ppsaData)
{
  IStream *pstrmRequest; // ecx
  SAFEARRAY *v4; // ebx
  int v5; // eax
  EnsureTls _EnsureTls; // [esp+Ch] [ebp-10h] BYREF
  unsigned __int8 *pb; // [esp+10h] [ebp-Ch] BYREF
  int lLBound; // [esp+14h] [ebp-8h] BYREF
  int lUBound; // [esp+18h] [ebp-4h] BYREF

  EnsureTls::EnsureTls(&_EnsureTls);
  pstrmRequest = this->_pstrmRequest;
  if ( pstrmRequest )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pstrmRequest->Release)(
      pstrmRequest->Release,
      this->_pstrmRequest);
    this->_pstrmRequest = 0;
  }
  pb = 0;
  lLBound = 0;
  lUBound = 0;
  v4 = *ppsaData;
  v5 = SafeArrayAccessData(*ppsaData, (void **)&pb);
  this->_hrResult = v5;
  if ( v5 < 0 )
  {
    HTTPRequest::_onResponseFinished(this);
  }
  else
  {
    if ( SafeArrayGetLBound(v4, 1u, &lLBound) >= 0 && SafeArrayGetUBound(v4, 1u, &lUBound) >= 0 )
    {
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IURLRequestSite *))this->_pRequestSite->AddRef)(
        this->_pRequestSite->AddRef,
        this->_pRequestSite);
      this->_hrResult = this->OnResponseDataAvailable(this, pb, lUBound - lLBound + 1, 0);
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IURLRequestSite *))this->_pRequestSite->Release)(
        this->_pRequestSite->Release,
        this->_pRequestSite);
    }
    SafeArrayUnaccessData(v4);
  }
}

```

## disassembly

```asm
0x10131c7d  mov     edi, edi
0x10131c7f  push    ebp
0x10131c80  mov     ebp, esp
0x10131c82  sub     esp, 10h
0x10131c85  push    ebx
0x10131c86  push    esi
0x10131c87  push    edi
0x10131c88  mov     edi, this
0x10131c8a  lea     this, [ebp+_EnsureTls]; this
0x10131c8d  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10131c92  mov     this, [edi+48h]
0x10131c95  test    this, this
0x10131c97  jz      short loc_10131CB0
0x10131c99  mov     eax, [this]
0x10131c9b  push    this
0x10131c9c  mov     esi, [eax+8]
0x10131c9f  mov     this, esi; this
0x10131ca1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131ca7  call    esi
0x10131ca9  mov     dword ptr [edi+48h], 0
0x10131cb0  mov     eax, [ebp+ppsaData]
0x10131cb3  mov     [ebp+pb], 0
0x10131cba  mov     [ebp+lLBound], 0
0x10131cc1  mov     [ebp+lUBound], 0
0x10131cc8  mov     ebx, [eax]
0x10131cca  lea     eax, [ebp+pb]
0x10131ccd  push    eax; ppvData
0x10131cce  push    ebx; psa
0x10131ccf  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x10131cd5  mov     [edi+4Ch], eax
0x10131cd8  test    eax, eax
0x10131cda  js      short loc_10131D51
0x10131cdc  lea     eax, [ebp+lLBound]
0x10131cdf  push    eax; plLbound
0x10131ce0  push    1; nDim
0x10131ce2  push    ebx; psa
0x10131ce3  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x10131ce9  test    eax, eax
0x10131ceb  js      short loc_10131D48
0x10131ced  lea     eax, [ebp+lUBound]
0x10131cf0  push    eax; plUbound
0x10131cf1  push    1; nDim
0x10131cf3  push    ebx; psa
0x10131cf4  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x10131cfa  test    eax, eax
0x10131cfc  js      short loc_10131D48
0x10131cfe  mov     eax, [edi+5Ch]
0x10131d01  push    eax
0x10131d02  mov     this, [eax]
0x10131d04  mov     esi, [this+4]
0x10131d07  mov     this, esi; this
0x10131d09  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131d0f  call    esi
0x10131d11  mov     eax, [edi]
0x10131d13  push    0
0x10131d15  mov     esi, [eax+0B0h]
0x10131d1b  mov     this, esi; this
0x10131d1d  mov     eax, [ebp+lUBound]
0x10131d20  sub     eax, [ebp+lLBound]
0x10131d23  inc     eax
0x10131d24  push    eax
0x10131d25  push    [ebp+pb]
0x10131d28  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131d2e  mov     this, edi
0x10131d30  call    esi
0x10131d32  mov     [edi+4Ch], eax
0x10131d35  mov     eax, [edi+5Ch]
0x10131d38  push    eax
0x10131d39  mov     this, [eax]
0x10131d3b  mov     esi, [this+8]
0x10131d3e  mov     this, esi; this
0x10131d40  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131d46  call    esi
0x10131d48  push    ebx; psa
0x10131d49  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x10131d4f  jmp     short loc_10131D58
0x10131d51  mov     this, edi; this
0x10131d53  call    ?_onResponseFinished@HTTPRequest@@IAEXXZ; HTTPRequest::_onResponseFinished(void)
0x10131d58  pop     edi
0x10131d59  pop     esi
0x10131d5a  pop     ebx
0x10131d5b  leave
0x10131d5c  retn    4
```
