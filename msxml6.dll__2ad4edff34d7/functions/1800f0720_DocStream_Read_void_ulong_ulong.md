# DocStream::Read(void *,ulong,ulong *)

- ea: `0x1800f0720`
- end: `0x1800f0814`
- name: `?Read@DocStream@@UEAAJPEAXKPEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(DocStream *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180056bdc`
- `0x1800f0720`
- `0x1800f0938`
- `0x180178528`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f079c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f079c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f07f2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f07f2`

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
    v8 = this->_dwState == NO_VARIABLES;
    pBytes = this->_pBytes;
    pB = pBytes;
    if ( !v8 )
    {
      v10 = 0;
      this->_dwState = NO_CURRENT;
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
0x1800f0720  push    rbx
0x1800f0722  push    rbp
0x1800f0723  push    rsi
0x1800f0724  push    rdi
0x1800f0725  push    r14
0x1800f0727  sub     rsp, 30h
0x1800f072b  mov     rbx, this
0x1800f072e  mov     r14, pcbRead
0x1800f0731  lea     this, [rsp+58h+_EnsureTls]; this
0x1800f0736  mov     esi, cb
0x1800f0739  mov     rbp, pv
0x1800f073c  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f0741  cmp     [rsp+58h+_EnsureTls._tlsdata], 0
0x1800f0747  jz      loc_1800F0804
0x1800f074d  cmp     dword ptr [rbx+18h], 2
0x1800f0751  mov     this, [rbx+38h]
0x1800f0755  mov     [rsp+58h+pB], this
0x1800f075a  jz      loc_1800F0804
0x1800f0760  xor     edi, edi
0x1800f0762  mov     dword ptr [rbx+18h], 1
0x1800f0769  cmp     [rbx+20h], rdi
0x1800f076d  jnz     short loc_1800F0779
0x1800f076f  cmp     [rbx+50h], rdi
0x1800f0773  jnz     short loc_1800F0779
0x1800f0775  xor     esi, esi
0x1800f0777  jmp     short $Done_7
0x1800f0779  test    rbp, rbp
0x1800f077c  jnz     short loc_1800F0789
0x1800f077e  test    esi, esi
0x1800f0780  jz      short $Done_7
0x1800f0782  mov     edi, 80030009h
0x1800f0787  jmp     short $CleanUp_212
0x1800f0789  test    esi, esi
0x1800f078b  jz      short $Done_7
0x1800f078d  cmp     [rbx+50h], rdi
0x1800f0791  jz      short loc_1800F07AF
0x1800f0793  mov     this, [rbx+50h]; psa
0x1800f0797  lea     pv, [rsp+58h+pB]; ppvData
0x1800f079c  call    cs:__imp_SafeArrayAccessData
0x1800f07a2  mov     edi, eax
0x1800f07a4  test    eax, eax
0x1800f07a6  js      short $CleanUp_212
0x1800f07a8  mov     this, [rsp+58h+pB]
0x1800f07ad  jmp     short loc_1800F07CB
0x1800f07af  test    this, this
0x1800f07b2  jnz     short loc_1800F07CB
0x1800f07b4  mov     this, rbx; this
0x1800f07b7  call    ?SaveDocument@DocStream@@AEAAJXZ; DocStream::SaveDocument(void)
0x1800f07bc  mov     edi, eax
0x1800f07be  test    eax, eax
0x1800f07c0  js      short $CleanUp_212
0x1800f07c2  mov     this, [rbx+38h]
0x1800f07c6  mov     [rsp+58h+pB], this
0x1800f07cb  mov     edx, [rbx+40h]
0x1800f07ce  mov     eax, [rbx+30h]
0x1800f07d1  sub     eax, edx
0x1800f07d3  cmp     esi, eax
0x1800f07d5  cmova   esi, eax
0x1800f07d8  add     pv, this; Src
0x1800f07db  mov     cb, esi; Size
0x1800f07de  mov     this, rbp; void *
0x1800f07e1  call    memcpy_0
0x1800f07e6  mov     this, [rbx+50h]; psa
0x1800f07ea  add     [rbx+40h], esi
0x1800f07ed  test    this, this
0x1800f07f0  jz      short $Done_7
0x1800f07f2  call    cs:__imp_SafeArrayUnaccessData
0x1800f07f8  test    r14, r14
0x1800f07fb  jz      short $CleanUp_212
0x1800f07fd  mov     [r14], esi
0x1800f0800  mov     eax, edi
0x1800f0802  jmp     short loc_1800F0809
0x1800f0804  mov     eax, 80004005h
0x1800f0809  add     rsp, 30h
0x1800f080d  pop     r14
0x1800f080f  pop     rdi
0x1800f0810  pop     rsi
0x1800f0811  pop     rbp
0x1800f0812  pop     rbx
0x1800f0813  retn
```
