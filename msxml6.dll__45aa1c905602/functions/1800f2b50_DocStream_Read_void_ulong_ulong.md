# DocStream::Read(void *,ulong,ulong *)

- ea: `0x1800f2b50`
- end: `0x1800f2c5b`
- name: `?Read@DocStream@@UEAAJPEAXKPEAK@Z`
- size: `267`
- prototype: `HRESULT __fastcall(DocStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180058ef4`
- `0x1800f2b50`
- `0x1800f2d80`
- `0x18017c1d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f2bd6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f2bd6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f2c32`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f2c32`

## pseudocode

```c
__int64 __fastcall DocStream::Read(DocStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)
{
  bool v8; // zf
  unsigned __int8 *pBytes; // rcx
  HRESULT v10; // edi
  __int64 cbRead; // rdx
  tagSAFEARRAY *psa; // rcx
  unsigned __int8 *pB; // [rsp+20h] [rbp-38h] BYREF
  EnsureTls _EnsureTls; // [rsp+28h] [rbp-30h] BYREF

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( _EnsureTls._tlsdata )
  {
    v8 = this->_dwState == ATTRIBUTE;
    pBytes = this->_pBytes;
    pB = pBytes;
    if ( !v8 )
    {
      v10 = 0;
      this->_dwState = ELEMENT;
      if ( !this->_pDoc._p && !this->_psa )
      {
        cb = 0;
        goto $Done_7;
      }
      if ( pv )
      {
        if ( cb )
        {
          if ( this->_psa )
          {
            v10 = SafeArrayAccessData(this->_psa, (void **)&pB);
            if ( v10 < 0 )
              return (unsigned int)v10;
            pBytes = pB;
          }
          else if ( !pBytes )
          {
            v10 = DocStream::SaveDocument(this);
            if ( v10 < 0 )
              return (unsigned int)v10;
            pBytes = this->_pBytes;
            pB = pBytes;
          }
          cbRead = this->_cbRead;
          if ( cb > this->_cbWritten - (int)cbRead )
            cb = this->_cbWritten - cbRead;
          memcpy_0(pv, &pBytes[cbRead], cb);
          psa = this->_psa;
          this->_cbRead += cb;
          if ( psa )
            SafeArrayUnaccessData(psa);
        }
      }
      else if ( cb )
      {
        return (unsigned int)-2147287031;
      }
$Done_7:
      if ( pcbRead )
        *pcbRead = cb;
      return (unsigned int)v10;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800f2b50  push    rbx
0x1800f2b52  push    rbp
0x1800f2b53  push    rsi
0x1800f2b54  push    rdi
0x1800f2b55  push    r14
0x1800f2b57  sub     rsp, 30h
0x1800f2b5b  mov     rbx, this
0x1800f2b5e  mov     r14, pcbRead
0x1800f2b61  lea     this, [rsp+58h+_EnsureTls]; this
0x1800f2b66  mov     esi, cb
0x1800f2b69  mov     rbp, pv
0x1800f2b6c  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f2b71  cmp     [rsp+58h+_EnsureTls._tlsdata], 0
0x1800f2b77  jz      loc_1800F2C4A
0x1800f2b7d  cmp     dword ptr [rbx+18h], 2
0x1800f2b81  mov     this, [rbx+38h]
0x1800f2b85  mov     [rsp+58h+pB], this
0x1800f2b8a  jz      loc_1800F2C4A
0x1800f2b90  xor     edi, edi
0x1800f2b92  mov     dword ptr [rbx+18h], 1
0x1800f2b99  cmp     [rbx+20h], rdi
0x1800f2b9d  jnz     short loc_1800F2BAC
0x1800f2b9f  cmp     [rbx+50h], rdi
0x1800f2ba3  jnz     short loc_1800F2BAC
0x1800f2ba5  xor     esi, esi
0x1800f2ba7  jmp     $Done_7
0x1800f2bac  test    rbp, rbp
0x1800f2baf  jnz     short loc_1800F2BC3
0x1800f2bb1  test    esi, esi
0x1800f2bb3  jz      $Done_7
0x1800f2bb9  mov     edi, 80030009h
0x1800f2bbe  jmp     $CleanUp_212
0x1800f2bc3  test    esi, esi
0x1800f2bc5  jz      short $Done_7
0x1800f2bc7  cmp     [rbx+50h], rdi
0x1800f2bcb  jz      short loc_1800F2BEF
0x1800f2bcd  mov     this, [rbx+50h]; psa
0x1800f2bd1  lea     pv, [rsp+58h+pB]; ppvData
0x1800f2bd6  call    cs:__imp_SafeArrayAccessData
0x1800f2bdd  nop     dword ptr [rax+rax+00h]
0x1800f2be2  mov     edi, eax
0x1800f2be4  test    eax, eax
0x1800f2be6  js      short $CleanUp_212
0x1800f2be8  mov     this, [rsp+58h+pB]
0x1800f2bed  jmp     short loc_1800F2C0B
0x1800f2bef  test    this, this
0x1800f2bf2  jnz     short loc_1800F2C0B
0x1800f2bf4  mov     this, rbx; this
0x1800f2bf7  call    ?SaveDocument@DocStream@@AEAAJXZ; DocStream::SaveDocument(void)
0x1800f2bfc  mov     edi, eax
0x1800f2bfe  test    eax, eax
0x1800f2c00  js      short $CleanUp_212
0x1800f2c02  mov     this, [rbx+38h]
0x1800f2c06  mov     [rsp+58h+pB], this
0x1800f2c0b  mov     edx, [rbx+40h]
0x1800f2c0e  mov     eax, [rbx+30h]
0x1800f2c11  sub     eax, edx
0x1800f2c13  cmp     esi, eax
0x1800f2c15  cmova   esi, eax
0x1800f2c18  add     pv, this; Src
0x1800f2c1b  mov     cb, esi; Size
0x1800f2c1e  mov     this, rbp; void *
0x1800f2c21  call    memcpy_0
0x1800f2c26  mov     this, [rbx+50h]; psa
0x1800f2c2a  add     [rbx+40h], esi
0x1800f2c2d  test    this, this
0x1800f2c30  jz      short $Done_7
0x1800f2c32  call    cs:__imp_SafeArrayUnaccessData
0x1800f2c39  nop     dword ptr [rax+rax+00h]
0x1800f2c3e  test    r14, r14
0x1800f2c41  jz      short $CleanUp_212
0x1800f2c43  mov     [r14], esi
0x1800f2c46  mov     eax, edi
0x1800f2c48  jmp     short loc_1800F2C4F
0x1800f2c4a  mov     eax, 80004005h
0x1800f2c4f  add     rsp, 30h
0x1800f2c53  pop     r14
0x1800f2c55  pop     rdi
0x1800f2c56  pop     rsi
0x1800f2c57  pop     rbp
0x1800f2c58  pop     rbx
0x1800f2c59  retn
```
