# HTTPRequest::_onResponseDataAvailable(tagSAFEARRAY * *)

- ea: `0x180153e44`
- end: `0x180153f51`
- name: `?_onResponseDataAvailable@HTTPRequest@@IEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `269`
- prototype: `void __fastcall(HTTPRequest *this, tagSAFEARRAY **ppsaData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180153c80`

## callees

- `0x180056bdc`
- `0x180153e44`
- `0x180153f58`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180153eda`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180153eda`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180153ec3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180153ec3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180153ea2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180153ea2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180153f3a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180153f3a`

## pseudocode

```c
void __fastcall HTTPRequest::_onResponseDataAvailable(HTTPRequest *this, tagSAFEARRAY **ppsaData)
{
  IStream *pstrmRequest; // rcx
  SAFEARRAY *v5; // rdi
  int v6; // eax
  HRESULT v7; // eax
  IURLRequestSite *pRequestSite; // rcx
  int lUBound; // [rsp+50h] [rbp+8h] BYREF
  int lLBound; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 *pb; // [rsp+60h] [rbp+18h] BYREF
  EnsureTls _EnsureTls; // [rsp+68h] [rbp+20h] BYREF

  EnsureTls::EnsureTls(&_EnsureTls);
  pstrmRequest = this->_pstrmRequest;
  if ( pstrmRequest )
  {
    pstrmRequest->Release(pstrmRequest);
    this->_pstrmRequest = 0;
  }
  v5 = *ppsaData;
  pb = 0;
  lLBound = 0;
  lUBound = 0;
  v6 = SafeArrayAccessData(v5, (void **)&pb);
  this->_hrResult = v6;
  if ( v6 < 0 )
  {
    HTTPRequest::_onResponseFinished(this);
  }
  else
  {
    if ( SafeArrayGetLBound(v5, 1u, &lLBound) >= 0 && SafeArrayGetUBound(v5, 1u, &lUBound) >= 0 )
    {
      this->_pRequestSite->AddRef(this->_pRequestSite);
      v7 = this->OnResponseDataAvailable(this, pb, lUBound - lLBound + 1, 0);
      pRequestSite = this->_pRequestSite;
      this->_hrResult = v7;
      pRequestSite->Release(pRequestSite);
    }
    SafeArrayUnaccessData(v5);
  }
}

```

## disassembly

```asm
0x180153e44  push    rbx
0x180153e46  push    rdi
0x180153e47  sub     rsp, 38h
0x180153e4b  mov     rbx, this
0x180153e4e  mov     rdi, ppsaData
0x180153e51  lea     this, [rsp+48h+_EnsureTls]; this
0x180153e56  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180153e5b  mov     this, [rbx+80h]
0x180153e62  test    this, this
0x180153e65  jz      short loc_180153E7E
0x180153e67  mov     rax, [this]
0x180153e6a  mov     rax, [rax+10h]
0x180153e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153e73  mov     qword ptr [rbx+80h], 0
0x180153e7e  mov     rdi, [rdi]
0x180153e81  lea     ppsaData, [rsp+48h+pb]; ppvData
0x180153e86  mov     this, rdi; psa
0x180153e89  mov     [rsp+48h+pb], 0
0x180153e92  mov     [rsp+48h+lLBound], 0
0x180153e9a  mov     [rsp+48h+lUBound], 0
0x180153ea2  call    cs:__imp_SafeArrayAccessData
0x180153ea8  mov     [rbx+88h], eax
0x180153eae  test    eax, eax
0x180153eb0  js      loc_180153F42
0x180153eb6  lea     r8, [rsp+48h+lLBound]; plLbound
0x180153ebb  mov     edx, 1; nDim
0x180153ec0  mov     this, rdi; psa
0x180153ec3  call    cs:__imp_SafeArrayGetLBound
0x180153ec9  test    eax, eax
0x180153ecb  js      short loc_180153F37
0x180153ecd  lea     r8, [rsp+48h+lUBound]; plUbound
0x180153ed2  mov     edx, 1; nDim
0x180153ed7  mov     this, rdi; psa
0x180153eda  call    cs:__imp_SafeArrayGetUBound
0x180153ee0  test    eax, eax
0x180153ee2  js      short loc_180153F37
0x180153ee4  mov     this, [rbx+0A0h]
0x180153eeb  mov     rax, [this]
0x180153eee  mov     rax, [rax+8]
0x180153ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153ef7  mov     rax, [rbx]
0x180153efa  xor     r9d, r9d
0x180153efd  mov     r8d, [rsp+48h+lUBound]
0x180153f02  mov     this, rbx
0x180153f05  sub     r8d, [rsp+48h+lLBound]
0x180153f0a  mov     ppsaData, [rsp+48h+pb]
0x180153f0f  inc     r8d
0x180153f12  mov     rax, [rax+160h]
0x180153f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153f1e  mov     this, [rbx+0A0h]
0x180153f25  mov     [rbx+88h], eax
0x180153f2b  mov     rax, [this]
0x180153f2e  mov     rax, [rax+10h]
0x180153f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153f37  mov     this, rdi; psa
0x180153f3a  call    cs:__imp_SafeArrayUnaccessData
0x180153f40  jmp     short loc_180153F4A
0x180153f42  mov     this, rbx; this
0x180153f45  call    ?_onResponseFinished@HTTPRequest@@IEAAXXZ; HTTPRequest::_onResponseFinished(void)
0x180153f4a  add     rsp, 38h
0x180153f4e  pop     rdi
0x180153f4f  pop     rbx
0x180153f50  retn
```
