# DocStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800f2ea0`
- end: `0x1800f301a`
- name: `?Stat@DocStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `378`
- prototype: `HRESULT __fastcall(DocStream *this, tagSTATSTG *pstatstg, unsigned int grfStatFlag)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180058ef4`
- `0x18005d2c4`
- `0x18009402c`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800cd3e4`
- `0x1800f2d80`
- `0x1800f2ea0`
- `0x18017c1d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f2fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f2fa1`

## pseudocode

```c
__int64 __fastcall DocStream::Stat(DocStream *this, tagSTATSTG *pstatstg, char grfStatFlag)
{
  unsigned int v7; // edi
  Document *p; // rax
  String *v9; // r14
  unsigned __int64 length; // rbx
  SIZE_T v11; // rcx
  wchar_t *v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 cb; // [rsp+78h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&cb);
  if ( !cb )
    return 2147500037LL;
  if ( pstatstg )
  {
    v7 = 0;
    memset_0(pstatstg, 0, sizeof(tagSTATSTG));
    pstatstg->type = 2;
    if ( this->_pDoc._p )
    {
      if ( !this->_pBytes )
      {
        v7 = DocStream::SaveDocument(this);
        if ( (v7 & 0x80000000) != 0 )
          return v7;
      }
    }
    pstatstg->cbSize.LowPart = this->_cbWritten;
    if ( (grfStatFlag & 1) != 0 )
      return v7;
    p = this->_pDoc._p;
    if ( !p )
      return v7;
    v9 = p->_pResolvedURLdoc._p;
    if ( !v9 )
      return v7;
    cb = 0;
    length = (unsigned int)v9->_length;
    if ( length + 1 < length )
    {
      cb = -1;
    }
    else
    {
      cb = length + 1;
      if ( ULongLongMult(length + 1, 2u, &cb) >= 0 )
      {
        v11 = cb;
        if ( cb <= 0x7FFFFFFF )
        {
          v7 = 0;
          goto LABEL_17;
        }
      }
    }
    v11 = 0;
    cb = 0;
    v7 = -2147024362;
LABEL_17:
    if ( (v7 & 0x80000000) == 0 )
    {
      v12 = (wchar_t *)CoTaskMemAlloc(v11);
      pstatstg->pwcsName = v12;
      if ( v12 )
      {
        v13 = length;
        memcpy_0(v12, v9->_pwsz, v13 * 2);
        pstatstg->pwcsName[v13] = 0;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    return v7;
  }
  return (unsigned int)-2147287031;
}

```

## disassembly

```asm
0x1800f2ea0  push    rbx
0x1800f2ea2  push    rsi
0x1800f2ea3  push    rdi
0x1800f2ea4  push    r14
0x1800f2ea6  sub     rsp, 38h
0x1800f2eaa  mov     r14d, grfStatFlag
0x1800f2ead  mov     rsi, pstatstg
0x1800f2eb0  mov     rbx, this
0x1800f2eb3  lea     this, [rsp+58h+cb]; this
0x1800f2eb8  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f2ebd  cmp     [rsp+58h+cb], 0
0x1800f2ec3  jnz     short loc_1800F2ECF
0x1800f2ec5  mov     eax, 80004005h
0x1800f2eca  jmp     loc_1800F300F
0x1800f2ecf  test    rsi, rsi
0x1800f2ed2  jnz     short loc_1800F2EDE
0x1800f2ed4  mov     edi, 80030009h
0x1800f2ed9  jmp     $CleanUp_214
0x1800f2ede  xor     edi, edi
0x1800f2ee0  xor     edx, edx; Val
0x1800f2ee2  lea     grfStatFlag, [rdi+50h]; Size
0x1800f2ee6  mov     this, rsi; void *
0x1800f2ee9  call    memset_0
0x1800f2eee  mov     dword ptr [rsi+8], 2
0x1800f2ef5  cmp     [rbx+20h], rdi
0x1800f2ef9  jz      short loc_1800F2F17
0x1800f2efb  cmp     [rbx+38h], rdi
0x1800f2eff  jnz     short loc_1800F2F17
0x1800f2f01  mov     this, rbx; this
0x1800f2f04  call    ?SaveDocument@DocStream@@AEAAJXZ; DocStream::SaveDocument(void)
0x1800f2f09  mov     edi, eax
0x1800f2f0b  mov     [rsp+58h+hr], eax
0x1800f2f0f  test    eax, eax
0x1800f2f11  js      $CleanUp_214
0x1800f2f17  mov     eax, [rbx+30h]
0x1800f2f1a  mov     [rsi+10h], eax
0x1800f2f1d  test    r14b, 1
0x1800f2f21  jnz     loc_1800F2FDB
0x1800f2f27  mov     rax, [rbx+20h]
0x1800f2f2b  test    rax, rax
0x1800f2f2e  jz      loc_1800F2FDB
0x1800f2f34  mov     r14, [rax+100h]
0x1800f2f3b  test    r14, r14
0x1800f2f3e  jz      loc_1800F2FDB
0x1800f2f44  mov     [rsp+58h+cb], 0
0x1800f2f4d  mov     ebx, [r14+10h]
0x1800f2f51  lea     this, [rbx+1]; ullMultiplicand
0x1800f2f55  cmp     this, rbx
0x1800f2f58  jb      short loc_1800F2F84
0x1800f2f5a  mov     [rsp+58h+cb], this
0x1800f2f5f  lea     r8, [rsp+58h+cb]; pullResult
0x1800f2f64  mov     edx, 2; ullMultiplier
0x1800f2f69  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f2f6e  test    eax, eax
0x1800f2f70  js      short loc_1800F2F8D
0x1800f2f72  mov     this, [rsp+58h+cb]
0x1800f2f77  cmp     this, 7FFFFFFFh
0x1800f2f7e  ja      short loc_1800F2F8D
0x1800f2f80  xor     edi, edi
0x1800f2f82  jmp     short loc_1800F2F99
0x1800f2f84  mov     [rsp+58h+cb], 0FFFFFFFFFFFFFFFFh
0x1800f2f8d  xor     ecx, ecx; cb
0x1800f2f8f  mov     [rsp+58h+cb], this
0x1800f2f94  mov     edi, 80070216h
0x1800f2f99  mov     [rsp+58h+hr], edi
0x1800f2f9d  test    edi, edi
0x1800f2f9f  js      short $CleanUp_214
0x1800f2fa1  call    cs:__imp_CoTaskMemAlloc
0x1800f2fa8  nop     dword ptr [rax+rax+00h]
0x1800f2fad  mov     [rsi], rax
0x1800f2fb0  test    rax, rax
0x1800f2fb3  jnz     short loc_1800F2FC0
0x1800f2fb5  mov     edi, 8007000Eh
0x1800f2fba  mov     [rsp+58h+hr], edi
0x1800f2fbe  jmp     short loc_1800F2FDB
0x1800f2fc0  add     rbx, rbx
0x1800f2fc3  mov     r8, rbx; Size
0x1800f2fc6  mov     pstatstg, [r14+18h]; Src
0x1800f2fca  mov     this, rax; void *
0x1800f2fcd  call    memcpy_0
0x1800f2fd2  mov     this, [rsi]
0x1800f2fd5  xor     eax, eax
0x1800f2fd7  mov     [rbx+this], ax
0x1800f2fdb  jmp     short $CleanUp_214
0x1800f2fdd  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800f2fe2  mov     ecx, cs:_tls_index
0x1800f2fe8  mov     rax, gs:58h
0x1800f2ff1  mov     edx, 8
0x1800f2ff6  mov     rax, [rax+this*8]
0x1800f2ffa  mov     this, [rax+pstatstg]
0x1800f2ffe  mov     this, [this+8]; e
0x1800f3002  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800f3007  mov     edi, eax
0x1800f3009  mov     [rsp+58h+hr], eax
0x1800f300d  mov     eax, edi
0x1800f300f  add     rsp, 38h
0x1800f3013  pop     r14
0x1800f3015  pop     rdi
0x1800f3016  pop     rsi
0x1800f3017  pop     rbx
0x1800f3018  retn
0x18018197e  push    rbp
0x180181980  sub     rsp, 20h
0x180181984  mov     rbp, rdx
0x180181987  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18018198c  nop
0x18018198d  add     rsp, 20h
0x180181991  pop     rbp
0x180181992  retn
```
