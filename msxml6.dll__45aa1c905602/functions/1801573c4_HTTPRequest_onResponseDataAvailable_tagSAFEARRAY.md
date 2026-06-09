# HTTPRequest::_onResponseDataAvailable(tagSAFEARRAY * *)

- ea: `0x1801573c4`
- end: `0x1801574ea`
- name: `?_onResponseDataAvailable@HTTPRequest@@IEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `294`
- prototype: `void __fastcall(HTTPRequest *this, tagSAFEARRAY **ppsaData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180157200`

## callees

- `0x180058ef4`
- `0x1801573c4`
- `0x1801574f0`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180157466`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180157466`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180157449`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180157449`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180157422`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180157422`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801574cc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801574cc`

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
0x1801573c4  push    rbx
0x1801573c6  push    rdi
0x1801573c7  sub     rsp, 38h
0x1801573cb  mov     rbx, this
0x1801573ce  mov     rdi, ppsaData
0x1801573d1  lea     this, [rsp+48h+_EnsureTls]; this
0x1801573d6  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1801573db  mov     this, [rbx+80h]
0x1801573e2  test    this, this
0x1801573e5  jz      short loc_1801573FE
0x1801573e7  mov     rax, [this]
0x1801573ea  mov     rax, [rax+10h]
0x1801573ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801573f3  mov     qword ptr [rbx+80h], 0
0x1801573fe  mov     rdi, [rdi]
0x180157401  lea     ppsaData, [rsp+48h+pb]; ppvData
0x180157406  mov     this, rdi; psa
0x180157409  mov     [rsp+48h+pb], 0
0x180157412  mov     [rsp+48h+lLBound], 0
0x18015741a  mov     [rsp+48h+lUBound], 0
0x180157422  call    cs:__imp_SafeArrayAccessData
0x180157429  nop     dword ptr [rax+rax+00h]
0x18015742e  mov     [rbx+88h], eax
0x180157434  test    eax, eax
0x180157436  js      loc_1801574DA
0x18015743c  lea     r8, [rsp+48h+lLBound]; plLbound
0x180157441  mov     edx, 1; nDim
0x180157446  mov     this, rdi; psa
0x180157449  call    cs:__imp_SafeArrayGetLBound
0x180157450  nop     dword ptr [rax+rax+00h]
0x180157455  test    eax, eax
0x180157457  js      short loc_1801574C9
0x180157459  lea     r8, [rsp+48h+lUBound]; plUbound
0x18015745e  mov     edx, 1; nDim
0x180157463  mov     this, rdi; psa
0x180157466  call    cs:__imp_SafeArrayGetUBound
0x18015746d  nop     dword ptr [rax+rax+00h]
0x180157472  test    eax, eax
0x180157474  js      short loc_1801574C9
0x180157476  mov     this, [rbx+0A0h]
0x18015747d  mov     rax, [this]
0x180157480  mov     rax, [rax+8]
0x180157484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157489  mov     rax, [rbx]
0x18015748c  xor     r9d, r9d
0x18015748f  mov     r8d, [rsp+48h+lUBound]
0x180157494  mov     this, rbx
0x180157497  sub     r8d, [rsp+48h+lLBound]
0x18015749c  mov     ppsaData, [rsp+48h+pb]
0x1801574a1  inc     r8d
0x1801574a4  mov     rax, [rax+160h]
0x1801574ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801574b0  mov     this, [rbx+0A0h]
0x1801574b7  mov     [rbx+88h], eax
0x1801574bd  mov     rax, [this]
0x1801574c0  mov     rax, [rax+10h]
0x1801574c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801574c9  mov     this, rdi; psa
0x1801574cc  call    cs:__imp_SafeArrayUnaccessData
0x1801574d3  nop     dword ptr [rax+rax+00h]
0x1801574d8  jmp     short loc_1801574E2
0x1801574da  mov     this, rbx; this
0x1801574dd  call    ?_onResponseFinished@HTTPRequest@@IEAAXXZ; HTTPRequest::_onResponseFinished(void)
0x1801574e2  add     rsp, 38h
0x1801574e6  pop     rdi
0x1801574e7  pop     rbx
0x1801574e8  retn
```
