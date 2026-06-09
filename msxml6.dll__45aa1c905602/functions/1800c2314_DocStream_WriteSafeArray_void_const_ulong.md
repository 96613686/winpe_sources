# DocStream::WriteSafeArray(void const *,ulong)

- ea: `0x1800c2314`
- end: `0x1800c2410`
- name: `?WriteSafeArray@DocStream@@AEAAJPEBXK@Z`
- size: `252`
- prototype: `HRESULT __fastcall(DocStream *this, const void *pv, unsigned int cb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800756a0`

## callees

- `0x1800c2314`
- `0x1800f2920`
- `0x18017c1d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c2399`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c2399`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c23d0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c23d0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c234b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c234b`

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
0x1800c2314  mov     [rsp+arg_8], rbx
0x1800c2319  mov     [rsp+arg_10], rbp
0x1800c231e  push    rsi
0x1800c231f  push    rdi
0x1800c2320  push    r12
0x1800c2322  push    r14
0x1800c2324  push    r15
0x1800c2326  sub     rsp, 20h
0x1800c232a  cmp     qword ptr [this+50h], 0
0x1800c232f  lea     rbx, [this+58h]
0x1800c2333  mov     ebp, cb
0x1800c2336  mov     r12, pv
0x1800c2339  mov     rdi, this
0x1800c233c  jnz     short loc_1800C2370
0x1800c233e  mov     ecx, 11h; vt
0x1800c2343  xor     edx, edx; lLbound
0x1800c2345  mov     cb, 1000h; cElements
0x1800c234b  call    cs:__imp_SafeArrayCreateVector
0x1800c2352  nop     dword ptr [rax+rax+00h]
0x1800c2357  mov     [rdi+50h], rax
0x1800c235b  mov     dword ptr [rbx], 0
0x1800c2361  test    rax, rax
0x1800c2364  jnz     short loc_1800C2370
0x1800c2366  mov     esi, 8007000Eh
0x1800c236b  jmp     $CleanUp_172
0x1800c2370  xor     r15d, r15d
0x1800c2373  xor     esi, esi
0x1800c2375  jmp     short loc_1800C23F2
0x1800c2377  mov     this, [rdi+50h]; psa
0x1800c237b  lea     pv, [rsp+48h+pB]; ppvData
0x1800c2380  mov     r14d, 1000h
0x1800c2386  mov     [rsp+48h+pB], 0
0x1800c238f  sub     r14d, [rbx]
0x1800c2392  cmp     ebp, r14d
0x1800c2395  cmovbe  r14d, ebp
0x1800c2399  call    cs:__imp_SafeArrayAccessData
0x1800c23a0  nop     dword ptr [rax+rax+00h]
0x1800c23a5  mov     esi, eax
0x1800c23a7  test    eax, eax
0x1800c23a9  js      short $CleanUp_172
0x1800c23ab  mov     ecx, [rbx]
0x1800c23ad  add     this, [rsp+48h+pB]; void *
0x1800c23b2  mov     edx, r15d
0x1800c23b5  add     pv, r12; Src
0x1800c23b8  mov     cb, r14d; Size
0x1800c23bb  call    memcpy_0
0x1800c23c0  mov     this, [rdi+50h]
0x1800c23c4  add     [rbx], r14d
0x1800c23c7  mov     edx, [rbx]
0x1800c23c9  mov     [this+18h], edx
0x1800c23cc  mov     this, [rdi+50h]; psa
0x1800c23d0  call    cs:__imp_SafeArrayUnaccessData
0x1800c23d7  nop     dword ptr [rax+rax+00h]
0x1800c23dc  sub     ebp, r14d
0x1800c23df  add     r15d, r14d
0x1800c23e2  cmp     dword ptr [rbx], 1000h
0x1800c23e8  jb      short loc_1800C23F2
0x1800c23ea  mov     this, rdi; this
0x1800c23ed  call    ?FlushSafeArray@DocStream@@AEAAJXZ; DocStream::FlushSafeArray(void)
0x1800c23f2  test    ebp, ebp
0x1800c23f4  jnz     short loc_1800C2377
0x1800c23f6  mov     rbx, [rsp+48h+arg_8]
0x1800c23fb  mov     eax, esi
0x1800c23fd  mov     rbp, [rsp+48h+arg_10]
0x1800c2402  add     rsp, 20h
0x1800c2406  pop     r15
0x1800c2408  pop     r14
0x1800c240a  pop     r12
0x1800c240c  pop     rdi
0x1800c240d  pop     rsi
0x1800c240e  retn
```
