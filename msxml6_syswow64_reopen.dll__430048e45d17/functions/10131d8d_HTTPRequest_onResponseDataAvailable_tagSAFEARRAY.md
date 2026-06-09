# HTTPRequest::_onResponseDataAvailable(tagSAFEARRAY * *)

- ea: `0x10131d8d`
- end: `0x10131e6f`
- name: `?_onResponseDataAvailable@HTTPRequest@@IAEXPAPAUtagSAFEARRAY@@@Z`
- size: `226`
- prototype: `void __thiscall(HTTPRequest *this, tagSAFEARRAY **ppsaData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10131bb0`

## callees

- `0x100505bc`
- `0x10067b20`
- `0x10131d8d`
- `0x10131e75`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x10131e04`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x10131e04`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x10131df3`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x10131df3`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10131ddf`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10131ddf`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10131e59`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10131e59`

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
0x10131d8d  mov     edi, edi
0x10131d8f  push    ebp
0x10131d90  mov     ebp, esp
0x10131d92  sub     esp, 10h
0x10131d95  push    ebx
0x10131d96  push    esi
0x10131d97  push    edi
0x10131d98  mov     edi, this
0x10131d9a  lea     this, [ebp+_EnsureTls]; this
0x10131d9d  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10131da2  mov     this, [edi+48h]
0x10131da5  test    this, this
0x10131da7  jz      short loc_10131DC0
0x10131da9  mov     eax, [this]
0x10131dab  push    this
0x10131dac  mov     esi, [eax+8]
0x10131daf  mov     this, esi; this
0x10131db1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131db7  call    esi
0x10131db9  mov     dword ptr [edi+48h], 0
0x10131dc0  mov     eax, [ebp+ppsaData]
0x10131dc3  mov     [ebp+pb], 0
0x10131dca  mov     [ebp+lLBound], 0
0x10131dd1  mov     [ebp+lUBound], 0
0x10131dd8  mov     ebx, [eax]
0x10131dda  lea     eax, [ebp+pb]
0x10131ddd  push    eax; ppvData
0x10131dde  push    ebx; psa
0x10131ddf  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x10131de5  mov     [edi+4Ch], eax
0x10131de8  test    eax, eax
0x10131dea  js      short loc_10131E61
0x10131dec  lea     eax, [ebp+lLBound]
0x10131def  push    eax; plLbound
0x10131df0  push    1; nDim
0x10131df2  push    ebx; psa
0x10131df3  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x10131df9  test    eax, eax
0x10131dfb  js      short loc_10131E58
0x10131dfd  lea     eax, [ebp+lUBound]
0x10131e00  push    eax; plUbound
0x10131e01  push    1; nDim
0x10131e03  push    ebx; psa
0x10131e04  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x10131e0a  test    eax, eax
0x10131e0c  js      short loc_10131E58
0x10131e0e  mov     eax, [edi+5Ch]
0x10131e11  push    eax
0x10131e12  mov     this, [eax]
0x10131e14  mov     esi, [this+4]
0x10131e17  mov     this, esi; this
0x10131e19  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131e1f  call    esi
0x10131e21  mov     eax, [edi]
0x10131e23  push    0
0x10131e25  mov     esi, [eax+0B0h]
0x10131e2b  mov     this, esi; this
0x10131e2d  mov     eax, [ebp+lUBound]
0x10131e30  sub     eax, [ebp+lLBound]
0x10131e33  inc     eax
0x10131e34  push    eax
0x10131e35  push    [ebp+pb]
0x10131e38  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131e3e  mov     this, edi
0x10131e40  call    esi
0x10131e42  mov     [edi+4Ch], eax
0x10131e45  mov     eax, [edi+5Ch]
0x10131e48  push    eax
0x10131e49  mov     this, [eax]
0x10131e4b  mov     esi, [this+8]
0x10131e4e  mov     this, esi; this
0x10131e50  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10131e56  call    esi
0x10131e58  push    ebx; psa
0x10131e59  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x10131e5f  jmp     short loc_10131E68
0x10131e61  mov     this, edi; this
0x10131e63  call    ?_onResponseFinished@HTTPRequest@@IAEXXZ; HTTPRequest::_onResponseFinished(void)
0x10131e68  pop     edi
0x10131e69  pop     esi
0x10131e6a  pop     ebx
0x10131e6b  leave
0x10131e6c  retn    4
```
