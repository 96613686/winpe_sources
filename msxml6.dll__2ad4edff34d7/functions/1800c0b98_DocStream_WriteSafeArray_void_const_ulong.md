# DocStream::WriteSafeArray(void const *,ulong)

- ea: `0x1800c0b98`
- end: `0x1800c0c7e`
- name: `?WriteSafeArray@DocStream@@AEAAJPEBXK@Z`
- size: `230`
- prototype: `__int64 __fastcall(DocStream *this, char *pv, unsigned int cb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800759a0`

## callees

- `0x1800c0b98`
- `0x1800f0500`
- `0x180178528`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c0c14`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c0c14`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0c45`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0c45`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c0bcf`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c0bcf`

## pseudocode

```c
__int64 __fastcall DocStream::WriteSafeArray(DocStream *this, char *pv, unsigned int cb)
{
  unsigned int *p_dwBuffered; // rbx
  tagSAFEARRAY *Vector; // rax
  HRESULT v8; // esi
  int v9; // r15d
  tagSAFEARRAY *psa; // rcx
  unsigned int v11; // r14d
  tagSAFEARRAY *v12; // rcx
  unsigned __int8 *pB; // [rsp+50h] [rbp+8h] BYREF

  p_dwBuffered = &this->_dwBuffered;
  if ( this->_psa || (Vector = SafeArrayCreateVector(0x11u, 0, 0x1000u), this->_psa = Vector, *p_dwBuffered = 0, Vector) )
  {
    v9 = 0;
    v8 = 0;
    while ( cb )
    {
      psa = this->_psa;
      pB = 0;
      v11 = 4096 - *p_dwBuffered;
      if ( cb <= v11 )
        v11 = cb;
      v8 = SafeArrayAccessData(psa, (void **)&pB);
      if ( v8 < 0 )
        break;
      memcpy_0(&pB[*p_dwBuffered], &pv[v9], v11);
      v12 = this->_psa;
      *p_dwBuffered += v11;
      v12->rgsabound[0].cElements = *p_dwBuffered;
      SafeArrayUnaccessData(this->_psa);
      cb -= v11;
      v9 += v11;
      if ( *p_dwBuffered >= 0x1000 )
        DocStream::FlushSafeArray(this);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c0b98  mov     [rsp+arg_8], rbx
0x1800c0b9d  mov     [rsp+arg_10], rbp
0x1800c0ba2  push    rsi
0x1800c0ba3  push    rdi
0x1800c0ba4  push    r12
0x1800c0ba6  push    r14
0x1800c0ba8  push    r15
0x1800c0baa  sub     rsp, 20h
0x1800c0bae  cmp     qword ptr [this+50h], 0
0x1800c0bb3  lea     rbx, [this+58h]
0x1800c0bb7  mov     ebp, cb
0x1800c0bba  mov     r12, pv
0x1800c0bbd  mov     rdi, this
0x1800c0bc0  jnz     short loc_1800C0BEB
0x1800c0bc2  mov     ecx, 11h; vt
0x1800c0bc7  xor     edx, edx; lLbound
0x1800c0bc9  mov     cb, 1000h; cElements
0x1800c0bcf  call    cs:__imp_SafeArrayCreateVector
0x1800c0bd5  mov     [rdi+50h], rax
0x1800c0bd9  mov     dword ptr [rbx], 0
0x1800c0bdf  test    rax, rax
0x1800c0be2  jnz     short loc_1800C0BEB
0x1800c0be4  mov     esi, 8007000Eh
0x1800c0be9  jmp     short $CleanUp_172
0x1800c0beb  xor     r15d, r15d
0x1800c0bee  xor     esi, esi
0x1800c0bf0  jmp     short loc_1800C0C61
0x1800c0bf2  mov     this, [rdi+50h]; psa
0x1800c0bf6  lea     pv, [rsp+48h+pB]; ppvData
0x1800c0bfb  mov     r14d, 1000h
0x1800c0c01  mov     [rsp+48h+pB], 0
0x1800c0c0a  sub     r14d, [rbx]
0x1800c0c0d  cmp     ebp, r14d
0x1800c0c10  cmovbe  r14d, ebp
0x1800c0c14  call    cs:__imp_SafeArrayAccessData
0x1800c0c1a  mov     esi, eax
0x1800c0c1c  test    eax, eax
0x1800c0c1e  js      short $CleanUp_172
0x1800c0c20  mov     ecx, [rbx]
0x1800c0c22  add     this, [rsp+48h+pB]; void *
0x1800c0c27  mov     edx, r15d
0x1800c0c2a  add     pv, r12; Src
0x1800c0c2d  mov     cb, r14d; Size
0x1800c0c30  call    memcpy_0
0x1800c0c35  mov     this, [rdi+50h]
0x1800c0c39  add     [rbx], r14d
0x1800c0c3c  mov     edx, [rbx]
0x1800c0c3e  mov     [this+18h], edx
0x1800c0c41  mov     this, [rdi+50h]; psa
0x1800c0c45  call    cs:__imp_SafeArrayUnaccessData
0x1800c0c4b  sub     ebp, r14d
0x1800c0c4e  add     r15d, r14d
0x1800c0c51  cmp     dword ptr [rbx], 1000h
0x1800c0c57  jb      short loc_1800C0C61
0x1800c0c59  mov     this, rdi; this
0x1800c0c5c  call    ?FlushSafeArray@DocStream@@AEAAJXZ; DocStream::FlushSafeArray(void)
0x1800c0c61  test    ebp, ebp
0x1800c0c63  jnz     short loc_1800C0BF2
0x1800c0c65  mov     rbx, [rsp+48h+arg_8]
0x1800c0c6a  mov     eax, esi
0x1800c0c6c  mov     rbp, [rsp+48h+arg_10]
0x1800c0c71  add     rsp, 20h
0x1800c0c75  pop     r15
0x1800c0c77  pop     r14
0x1800c0c79  pop     r12
0x1800c0c7b  pop     rdi
0x1800c0c7c  pop     rsi
0x1800c0c7d  retn
```
