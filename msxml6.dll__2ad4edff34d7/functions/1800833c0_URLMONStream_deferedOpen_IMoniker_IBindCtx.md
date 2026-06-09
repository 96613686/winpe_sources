# URLMONStream::deferedOpen(IMoniker *,IBindCtx *)

- ea: `0x1800833c0`
- end: `0x18008360c`
- name: `?deferedOpen@URLMONStream@@UEAAJPEAUIMoniker@@PEAUIBindCtx@@@Z`
- size: `588`
- prototype: `HRESULT __fastcall(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009490`
- `0x18000d7d0`
- `0x1800833c0`
- `0x1800837b4`
- `0x1800c0360`
- `0x18015bbdc`
- `0x180188010`

## import_xrefs

- `urlmon!RegisterBindStatusCallback` at `0x180083554`
- `urlmon!RegisterBindStatusCallback` at `0x180083554`
- `urlmon!RevokeBindStatusCallback` at `0x18008348b`
- `urlmon!RevokeBindStatusCallback` at `0x18008348b`
- `urlmon!CreateURLMonikerEx` at `0x180083577`
- `urlmon!CreateURLMonikerEx` at `0x180083577`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180083459`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180083459`

## pseudocode

```c
HRESULT __fastcall URLMONStream::deferedOpen(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)
{
  wchar_t *resolvedURL; // rcx
  HRESULT result; // eax
  HRESULT BindCtx; // ebx
  IBindCtx *v9; // rcx
  HRESULT ulStatus; // ecx
  IBindStatusCallback *p; // rcx
  IMoniker *v12; // rcx
  IStream *v13; // rcx
  IStream *pStream; // [rsp+30h] [rbp-10h] BYREF
  _reference<IBindCtx> pbc; // [rsp+60h] [rbp+20h] BYREF
  IMoniker *pmk; // [rsp+78h] [rbp+38h] BYREF

  pmk = 0;
  resolvedURL = this->_resolvedURL;
  pStream = 0;
  result = URL::IsSafeScheme(resolvedURL);
  if ( result < 0 )
    return result;
  result = URL::accessAllowed(this->_fSecure, this->_pSecMgr._p, this->_resolvedURL, 0, this->_secureBaseURL, 0);
  if ( result < 0 )
    return result;
  if ( this->_fDTD && (int)URLStream::OpenPreloadResource(this, this->_resolvedURL) >= 0 )
    return 0;
  pbc._p = 0;
  if ( lpbc )
  {
    assign(&pbc._p, lpbc);
  }
  else
  {
    BindCtx = CreateBindCtx(0, &pbc._p);
    if ( BindCtx < 0 )
      goto LABEL_8;
  }
  p = this->_pbs._p;
  if ( p )
  {
    this->_pbs._p = 0;
    p->Release(p);
  }
  assign(&this->_pbc._p, pbc._p);
  BindCtx = RegisterBindStatusCallback(
              pbc._p,
              (IBindStatusCallback *)((unsigned __int64)&this->IBindStatusCallback
                                    & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
              &this->_pbs._p,
              0);
  if ( BindCtx < 0 )
    goto LABEL_8;
  if ( pMoniker )
  {
    pmk = pMoniker;
    pMoniker->AddRef(pMoniker);
  }
  else
  {
    BindCtx = CreateURLMonikerEx(0, this->_resolvedURL, &pmk, 1u);
    if ( BindCtx < 0 )
      goto LABEL_8;
  }
  v12 = pmk;
  this->_ulStatus = -2147483638;
  BindCtx = v12->BindToStorage(v12, pbc._p, 0, &IID_IStream, (void **)&pStream);
  if ( BindCtx >= 0 )
  {
    v13 = pStream;
    BindCtx = 0;
    if ( pStream )
    {
      if ( !this->_pStream._p )
      {
        assign(&this->_pStream._p, pStream);
        v13 = pStream;
      }
      v13->Release(v13);
    }
    goto LABEL_10;
  }
LABEL_8:
  v9 = this->_pbc._p;
  if ( v9 )
  {
    RevokeBindStatusCallback(
      v9,
      (IBindStatusCallback *)((unsigned __int64)&this->IBindStatusCallback
                            & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
    assign(&this->_pbc._p, 0);
  }
LABEL_10:
  ulStatus = this->_ulStatus;
  if ( (int)(ulStatus + 0x80000000) >= 0 && ulStatus != -2147483638 )
    BindCtx = this->_ulStatus;
  if ( BindCtx == -2146697211 )
    BindCtx = -2146697210;
  if ( pmk )
  {
    ((void (*)(void))pmk->Release)();
    pmk = 0;
  }
  release(&pbc._p);
  return BindCtx;
}

```

## disassembly

```asm
0x1800833c0  mov     [rsp-18h+arg_8], rbx
0x1800833c5  push    rbp
0x1800833c6  push    rsi
0x1800833c7  push    rdi
0x1800833c8  mov     rbp, rsp
0x1800833cb  sub     rsp, 40h
0x1800833cf  mov     rdi, this
0x1800833d2  mov     [rbp+pmk], 0
0x1800833da  mov     this, [this+18h]; pwszUrl
0x1800833de  mov     rbx, lpbc
0x1800833e1  mov     rsi, pMoniker
0x1800833e4  mov     [rbp+pStream], 0
0x1800833ec  call    ?IsSafeScheme@URL@@SAJPEBG@Z; URL::IsSafeScheme(ushort const *)
0x1800833f1  test    eax, eax
0x1800833f3  js      loc_1800834EC
0x1800833f9  mov     rax, [rdi+30h]
0x1800833fd  xor     r9d, r9d; pwszBaseUrl
0x180083400  mov     lpbc, [rdi+18h]; pwszReqUrl
0x180083404  mov     pMoniker, [rdi+10h]; pSecMgr
0x180083408  mov     cl, [rdi+40h]; fSecure
0x18008340b  mov     [rsp+40h+fZoneRelaxed], 0; fZoneRelaxed
0x180083410  mov     [rsp+40h+pwszSecureUrl], rax; pwszSecureUrl
0x180083415  call    ?accessAllowed@URL@@SAJ_NPEAUIInternetSecurityManager@@PEBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x18008341a  test    eax, eax
0x18008341c  js      loc_1800834EC
0x180083422  cmp     byte ptr [rdi+0D8h], 0
0x180083429  jz      short loc_180083442
0x18008342b  mov     pMoniker, [rdi+18h]; _resolvedURL
0x18008342f  mov     this, rdi; this
0x180083432  call    ?OpenPreloadResource@URLStream@@IEAAJPEBG@Z; URLStream::OpenPreloadResource(ushort const *)
0x180083437  test    eax, eax
0x180083439  js      short loc_180083442
0x18008343b  xor     eax, eax
0x18008343d  jmp     loc_1800834EC
0x180083442  mov     [rbp+pbc._p], 0
0x18008344a  test    rbx, rbx
0x18008344d  jnz     loc_1800834F9
0x180083453  lea     pMoniker, [rbp+pbc]; ppbc
0x180083457  xor     ecx, ecx; reserved
0x180083459  call    cs:__imp_CreateBindCtx
0x18008345f  mov     ebx, eax
0x180083461  test    eax, eax
0x180083463  jns     loc_180083505
0x180083469  lea     rsi, [rdi+0B8h]
0x180083470  mov     this, [rsi]; pBC
0x180083473  test    this, this
0x180083476  jz      short loc_18008349B
0x180083478  lea     lpbc, [rdi+0A0h]
0x18008347f  mov     rax, rdi
0x180083482  neg     rax
0x180083485  sbb     pMoniker, pMoniker
0x180083488  and     pMoniker, lpbc; pBSCb
0x18008348b  call    cs:__imp_RevokeBindStatusCallback
0x180083491  xor     edx, edx; pref
0x180083493  mov     this, rsi; ppref
0x180083496  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18008349b  mov     ecx, [rdi+98h]
0x1800834a1  mov     edx, 80000000h
0x1800834a6  lea     eax, [this+pMoniker]
0x1800834a9  test    edx, eax
0x1800834ab  jnz     short loc_1800834B6
0x1800834ad  cmp     ecx, 8000000Ah
0x1800834b3  cmovnz  ebx, ecx
0x1800834b6  mov     this, [rbp+pmk]
0x1800834ba  cmp     ebx, 800C0005h
0x1800834c0  mov     eax, 800C0006h
0x1800834c5  cmovz   ebx, eax
0x1800834c8  test    this, this
0x1800834cb  jz      short loc_1800834E1
0x1800834cd  mov     pMoniker, [this]
0x1800834d0  mov     rax, [pMoniker+10h]
0x1800834d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800834d9  mov     [rbp+pmk], 0
0x1800834e1  lea     this, [rbp+pbc]; ppref
0x1800834e5  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800834ea  mov     eax, ebx
0x1800834ec  mov     rbx, [rsp+40h+arg_8]
0x1800834f1  add     rsp, 40h
0x1800834f5  pop     rdi
0x1800834f6  pop     rsi
0x1800834f7  pop     rbp
0x1800834f8  retn
0x1800834f9  mov     pMoniker, rbx; pref
0x1800834fc  lea     this, [rbp+pbc]; ppref
0x180083500  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180083505  lea     rbx, [rdi+0C0h]
0x18008350c  mov     this, [rbx]
0x18008350f  test    this, this
0x180083512  jz      short loc_180083527
0x180083514  mov     qword ptr [rbx], 0
0x18008351b  mov     rax, [this]
0x18008351e  mov     rax, [rax+10h]
0x180083522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083527  mov     pMoniker, [rbp+pbc._p]; pref
0x18008352b  lea     this, [rdi+0B8h]; ppref
0x180083532  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180083537  mov     this, [rbp+pbc._p]; pBC
0x18008353b  lea     r9, [rdi+0A0h]
0x180083542  mov     rax, rdi
0x180083545  mov     lpbc, rbx; ppBSCBPrev
0x180083548  neg     rax
0x18008354b  sbb     pMoniker, pMoniker
0x18008354e  and     pMoniker, r9; pBSCb
0x180083551  xor     r9d, r9d; dwReserved
0x180083554  call    cs:__imp_RegisterBindStatusCallback
0x18008355a  mov     ebx, eax
0x18008355c  test    eax, eax
0x18008355e  js      loc_180083469
0x180083564  test    rsi, rsi
0x180083567  jnz     short loc_180083588
0x180083569  mov     pMoniker, [rdi+18h]; szURL
0x18008356d  lea     r9d, [rsi+1]; dwFlags
0x180083571  lea     lpbc, [rbp+pmk]; ppmk
0x180083575  xor     ecx, ecx; pMkCtx
0x180083577  call    cs:__imp_CreateURLMonikerEx
0x18008357d  mov     ebx, eax
0x18008357f  test    eax, eax
0x180083581  jns     short loc_18008359B
0x180083583  jmp     loc_180083469
0x180083588  mov     [rbp+pmk], rsi
0x18008358c  mov     this, rsi
0x18008358f  mov     rax, [rsi]
0x180083592  mov     rax, [rax+8]
0x180083596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008359b  mov     this, [rbp+pmk]
0x18008359f  lea     pMoniker, [rbp+pStream]
0x1800835a3  mov     dword ptr [rdi+98h], 8000000Ah
0x1800835ad  lea     r9, IID_IStream
0x1800835b4  mov     [rsp+40h+pwszSecureUrl], pMoniker
0x1800835b9  xor     r8d, r8d
0x1800835bc  mov     pMoniker, [rbp+pbc._p]
0x1800835c0  mov     rax, [this]
0x1800835c3  mov     rax, [rax+48h]
0x1800835c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800835cc  mov     ebx, eax
0x1800835ce  test    eax, eax
0x1800835d0  js      loc_180083469
0x1800835d6  mov     this, [rbp+pStream]
0x1800835da  xor     ebx, ebx
0x1800835dc  test    this, this
0x1800835df  jz      loc_18008349B
0x1800835e5  cmp     [rdi+48h], rbx
0x1800835e9  jnz     short loc_1800835FB
0x1800835eb  mov     pMoniker, this; pref
0x1800835ee  lea     this, [rdi+48h]; ppref
0x1800835f2  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800835f7  mov     this, [rbp+pStream]
0x1800835fb  mov     rax, [this]
0x1800835fe  mov     rax, [rax+10h]
0x180083602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083607  jmp     loc_18008349B
```
