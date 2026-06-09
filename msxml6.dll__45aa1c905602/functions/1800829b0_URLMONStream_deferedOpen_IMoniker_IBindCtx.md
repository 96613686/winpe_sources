# URLMONStream::deferedOpen(IMoniker *,IBindCtx *)

- ea: `0x1800829b0`
- end: `0x180082c15`
- name: `?deferedOpen@URLMONStream@@UEAAJPEAUIMoniker@@PEAUIBindCtx@@@Z`
- size: `613`
- prototype: `HRESULT __fastcall(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180015a80`
- `0x180019e20`
- `0x1800829b0`
- `0x180082dd0`
- `0x1800c1908`
- `0x18015f3f4`
- `0x18018c010`

## import_xrefs

- `urlmon!RegisterBindStatusCallback` at `0x180082b51`
- `urlmon!RegisterBindStatusCallback` at `0x180082b51`
- `urlmon!RevokeBindStatusCallback` at `0x180082a81`
- `urlmon!RevokeBindStatusCallback` at `0x180082a81`
- `urlmon!CreateURLMonikerEx` at `0x180082b7a`
- `urlmon!CreateURLMonikerEx` at `0x180082b7a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180082a49`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180082a49`

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
  if ( this->_fDTD && URLStream::OpenPreloadResource(this, this->_resolvedURL) >= 0 )
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
0x1800829b0  mov     [rsp-18h+arg_8], rbx
0x1800829b5  push    rbp
0x1800829b6  push    rsi
0x1800829b7  push    rdi
0x1800829b8  mov     rbp, rsp
0x1800829bb  sub     rsp, 40h
0x1800829bf  mov     rdi, this
0x1800829c2  mov     [rbp+pmk], 0
0x1800829ca  mov     this, [this+18h]; pwszUrl
0x1800829ce  mov     rbx, lpbc
0x1800829d1  mov     rsi, pMoniker
0x1800829d4  mov     [rbp+pStream], 0
0x1800829dc  call    ?IsSafeScheme@URL@@SAJPEBG@Z; URL::IsSafeScheme(ushort const *)
0x1800829e1  test    eax, eax
0x1800829e3  js      loc_180082AE8
0x1800829e9  mov     rax, [rdi+30h]
0x1800829ed  xor     r9d, r9d; pwszBaseUrl
0x1800829f0  mov     lpbc, [rdi+18h]; pwszReqUrl
0x1800829f4  mov     pMoniker, [rdi+10h]; pSecMgr
0x1800829f8  mov     cl, [rdi+40h]; fSecure
0x1800829fb  mov     [rsp+40h+fZoneRelaxed], 0; fZoneRelaxed
0x180082a00  mov     [rsp+40h+pwszSecureUrl], rax; pwszSecureUrl
0x180082a05  call    ?accessAllowed@URL@@SAJ_NPEAUIInternetSecurityManager@@PEBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x180082a0a  test    eax, eax
0x180082a0c  js      loc_180082AE8
0x180082a12  cmp     byte ptr [rdi+0D8h], 0
0x180082a19  jz      short loc_180082A32
0x180082a1b  mov     pMoniker, [rdi+18h]; _resolvedURL
0x180082a1f  mov     this, rdi; this
0x180082a22  call    ?OpenPreloadResource@URLStream@@IEAAJPEBG@Z; URLStream::OpenPreloadResource(ushort const *)
0x180082a27  test    eax, eax
0x180082a29  js      short loc_180082A32
0x180082a2b  xor     eax, eax
0x180082a2d  jmp     loc_180082AE8
0x180082a32  mov     [rbp+pbc._p], 0
0x180082a3a  test    rbx, rbx
0x180082a3d  jnz     loc_180082AF6
0x180082a43  lea     pMoniker, [rbp+pbc]; ppbc
0x180082a47  xor     ecx, ecx; reserved
0x180082a49  call    cs:__imp_CreateBindCtx
0x180082a50  nop     dword ptr [rax+rax+00h]
0x180082a55  mov     ebx, eax
0x180082a57  test    eax, eax
0x180082a59  jns     loc_180082B02
0x180082a5f  lea     rsi, [rdi+0B8h]
0x180082a66  mov     this, [rsi]; pBC
0x180082a69  test    this, this
0x180082a6c  jz      short loc_180082A97
0x180082a6e  lea     lpbc, [rdi+0A0h]
0x180082a75  mov     rax, rdi
0x180082a78  neg     rax
0x180082a7b  sbb     pMoniker, pMoniker
0x180082a7e  and     pMoniker, lpbc; pBSCb
0x180082a81  call    cs:__imp_RevokeBindStatusCallback
0x180082a88  nop     dword ptr [rax+rax+00h]
0x180082a8d  xor     edx, edx; pref
0x180082a8f  mov     this, rsi; ppref
0x180082a92  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180082a97  mov     ecx, [rdi+98h]
0x180082a9d  mov     edx, 80000000h
0x180082aa2  lea     eax, [this+pMoniker]
0x180082aa5  test    edx, eax
0x180082aa7  jnz     short loc_180082AB2
0x180082aa9  cmp     ecx, 8000000Ah
0x180082aaf  cmovnz  ebx, ecx
0x180082ab2  mov     this, [rbp+pmk]
0x180082ab6  cmp     ebx, 800C0005h
0x180082abc  mov     eax, 800C0006h
0x180082ac1  cmovz   ebx, eax
0x180082ac4  test    this, this
0x180082ac7  jz      short loc_180082ADD
0x180082ac9  mov     pMoniker, [this]
0x180082acc  mov     rax, [pMoniker+10h]
0x180082ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ad5  mov     [rbp+pmk], 0
0x180082add  lea     this, [rbp+pbc]; ppref
0x180082ae1  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180082ae6  mov     eax, ebx
0x180082ae8  mov     rbx, [rsp+40h+arg_8]
0x180082aed  add     rsp, 40h
0x180082af1  pop     rdi
0x180082af2  pop     rsi
0x180082af3  pop     rbp
0x180082af4  retn
0x180082af6  mov     pMoniker, rbx; pref
0x180082af9  lea     this, [rbp+pbc]; ppref
0x180082afd  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180082b02  lea     rbx, [rdi+0C0h]
0x180082b09  mov     this, [rbx]
0x180082b0c  test    this, this
0x180082b0f  jz      short loc_180082B24
0x180082b11  mov     qword ptr [rbx], 0
0x180082b18  mov     rax, [this]
0x180082b1b  mov     rax, [rax+10h]
0x180082b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b24  mov     pMoniker, [rbp+pbc._p]; pref
0x180082b28  lea     this, [rdi+0B8h]; ppref
0x180082b2f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180082b34  mov     this, [rbp+pbc._p]; pBC
0x180082b38  lea     r9, [rdi+0A0h]
0x180082b3f  mov     rax, rdi
0x180082b42  mov     lpbc, rbx; ppBSCBPrev
0x180082b45  neg     rax
0x180082b48  sbb     pMoniker, pMoniker
0x180082b4b  and     pMoniker, r9; pBSCb
0x180082b4e  xor     r9d, r9d; dwReserved
0x180082b51  call    cs:__imp_RegisterBindStatusCallback
0x180082b58  nop     dword ptr [rax+rax+00h]
0x180082b5d  mov     ebx, eax
0x180082b5f  test    eax, eax
0x180082b61  js      loc_180082A5F
0x180082b67  test    rsi, rsi
0x180082b6a  jnz     short loc_180082B91
0x180082b6c  mov     pMoniker, [rdi+18h]; szURL
0x180082b70  lea     r9d, [rsi+1]; dwFlags
0x180082b74  lea     lpbc, [rbp+pmk]; ppmk
0x180082b78  xor     ecx, ecx; pMkCtx
0x180082b7a  call    cs:__imp_CreateURLMonikerEx
0x180082b81  nop     dword ptr [rax+rax+00h]
0x180082b86  mov     ebx, eax
0x180082b88  test    eax, eax
0x180082b8a  jns     short loc_180082BA4
0x180082b8c  jmp     loc_180082A5F
0x180082b91  mov     [rbp+pmk], rsi
0x180082b95  mov     this, rsi
0x180082b98  mov     rax, [rsi]
0x180082b9b  mov     rax, [rax+8]
0x180082b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ba4  mov     this, [rbp+pmk]
0x180082ba8  lea     pMoniker, [rbp+pStream]
0x180082bac  mov     dword ptr [rdi+98h], 8000000Ah
0x180082bb6  lea     r9, IID_IStream
0x180082bbd  mov     [rsp+40h+pwszSecureUrl], pMoniker
0x180082bc2  xor     r8d, r8d
0x180082bc5  mov     pMoniker, [rbp+pbc._p]
0x180082bc9  mov     rax, [this]
0x180082bcc  mov     rax, [rax+48h]
0x180082bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bd5  mov     ebx, eax
0x180082bd7  test    eax, eax
0x180082bd9  js      loc_180082A5F
0x180082bdf  mov     this, [rbp+pStream]
0x180082be3  xor     ebx, ebx
0x180082be5  test    this, this
0x180082be8  jz      loc_180082A97
0x180082bee  cmp     [rdi+48h], rbx
0x180082bf2  jnz     short loc_180082C04
0x180082bf4  mov     pMoniker, this; pref
0x180082bf7  lea     this, [rdi+48h]; ppref
0x180082bfb  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180082c00  mov     this, [rbp+pStream]
0x180082c04  mov     rax, [this]
0x180082c07  mov     rax, [rax+10h]
0x180082c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c10  jmp     loc_180082A97
```
