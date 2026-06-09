# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002e9c`
- end: `0x180002fe2`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `326`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180006374`

## callees

- `0x180001140`
- `0x180001d06`
- `0x180002e9c`

## import_xrefs

- `msvcrt!realloc` at `0x180002f69`
- `msvcrt!realloc` at `0x180002f69`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002fc6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002fc6`
- `ole32!CoTaskMemAlloc` at `0x180002f09`
- `ole32!CoTaskMemAlloc` at `0x180002f1d`
- `ole32!CoTaskMemAlloc` at `0x180002f09`
- `ole32!CoTaskMemAlloc` at `0x180002f1d`
- `ole32!CoTaskMemFree` at `0x180002f77`
- `ole32!CoTaskMemFree` at `0x180002f81`
- `ole32!CoTaskMemFree` at `0x180002fb3`
- `ole32!CoTaskMemFree` at `0x180002fbd`
- `ole32!CoTaskMemFree` at `0x180002f77`
- `ole32!CoTaskMemFree` at `0x180002f81`
- `ole32!CoTaskMemFree` at `0x180002fb3`
- `ole32!CoTaskMemFree` at `0x180002fbd`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  SIZE_T v9; // r15
  unsigned int v10; // esi
  LPVOID v11; // rax
  void *v12; // rcx
  int v13; // eax
  void *v14; // rcx
  int v15; // eax
  void *v16; // rax
  unsigned int v17; // edx

  v6 = (void **)operator new(0x10u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = -1;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( a3 )
  {
    do
      ++v7;
    while ( a3[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v9 = (unsigned int)(2 * v8 + 2);
  *v6 = CoTaskMemAlloc(v9);
  v10 = 2 * v7 + 2;
  v11 = CoTaskMemAlloc(v10);
  v12 = *v6;
  v6[1] = v11;
  if ( !v12 || !v11 )
  {
    CoTaskMemFree(v12);
    CoTaskMemFree(v6[1]);
    operator delete(v6);
    return (unsigned int)-2147024882;
  }
  memcpy_0(v12, a2, (unsigned int)v9);
  memcpy_0(v6[1], a3, v10);
  v13 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == v13 )
  {
    v14 = *(void **)this;
    v15 = 2 * v13;
    *((_DWORD *)this + 3) = v15;
    v16 = realloc(v14, 8LL * v15);
    if ( !v16 )
    {
      CoTaskMemFree(*v6);
      CoTaskMemFree(v6[1]);
      operator delete(v6);
      *((int *)this + 3) /= 2;
      return (unsigned int)-2147024882;
    }
    *(_QWORD *)this = v16;
  }
  v17 = 0;
  *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
  return v17;
}

```

## disassembly

```asm
0x180002e9c  push    rbx
0x180002e9e  push    rbp
0x180002e9f  push    rsi
0x180002ea0  push    rdi
0x180002ea1  push    r12
0x180002ea3  push    r14
0x180002ea5  push    r15
0x180002ea7  sub     rsp, 20h
0x180002eab  mov     rbx, rcx
0x180002eae  mov     r14, r8
0x180002eb1  mov     ecx, 10h; Size
0x180002eb6  mov     rbp, rdx
0x180002eb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ebe  xor     r12d, r12d
0x180002ec1  mov     rdi, rax
0x180002ec4  test    rax, rax
0x180002ec7  jz      loc_180002FCC
0x180002ecd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002ed1  test    rbp, rbp
0x180002ed4  jnz     short loc_180002EDB
0x180002ed6  mov     eax, r12d
0x180002ed9  jmp     short loc_180002EE9
0x180002edb  mov     rax, rsi
0x180002ede  inc     rax
0x180002ee1  cmp     [rbp+rax*2+0], r12w
0x180002ee7  jnz     short loc_180002EDE
0x180002ee9  test    r14, r14
0x180002eec  jnz     short loc_180002EF3
0x180002eee  mov     esi, r12d
0x180002ef1  jmp     short loc_180002EFD
0x180002ef3  inc     rsi
0x180002ef6  cmp     [r14+rsi*2], r12w
0x180002efb  jnz     short loc_180002EF3
0x180002efd  lea     eax, ds:2[rax*2]
0x180002f04  mov     ecx, eax; cb
0x180002f06  mov     r15d, eax
0x180002f09  call    cs:__imp_CoTaskMemAlloc
0x180002f0f  mov     [rdi], rax
0x180002f12  lea     eax, ds:2[rsi*2]
0x180002f19  mov     ecx, eax; cb
0x180002f1b  mov     esi, eax
0x180002f1d  call    cs:__imp_CoTaskMemAlloc
0x180002f23  mov     rcx, [rdi]; pv
0x180002f26  mov     [rdi+8], rax
0x180002f2a  test    rcx, rcx
0x180002f2d  jz      loc_180002FB3
0x180002f33  test    rax, rax
0x180002f36  jz      short loc_180002FB3
0x180002f38  mov     r8d, r15d; Size
0x180002f3b  mov     rdx, rbp; Src
0x180002f3e  call    memcpy_0
0x180002f43  mov     rcx, [rdi+8]; void *
0x180002f47  mov     r8d, esi; Size
0x180002f4a  mov     rdx, r14; Src
0x180002f4d  call    memcpy_0
0x180002f52  mov     eax, [rbx+0Ch]
0x180002f55  cmp     [rbx+8], eax
0x180002f58  jnz     short loc_180002FA0
0x180002f5a  mov     rcx, [rbx]; Block
0x180002f5d  add     eax, eax
0x180002f5f  movsxd  rdx, eax
0x180002f62  shl     rdx, 3; Size
0x180002f66  mov     [rbx+0Ch], eax
0x180002f69  call    cs:__imp_realloc
0x180002f6f  test    rax, rax
0x180002f72  jnz     short loc_180002F9D
0x180002f74  mov     rcx, [rdi]; pv
0x180002f77  call    cs:__imp_CoTaskMemFree
0x180002f7d  mov     rcx, [rdi+8]; pv
0x180002f81  call    cs:__imp_CoTaskMemFree
0x180002f87  mov     rcx, rdi
0x180002f8a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f90  mov     eax, [rbx+0Ch]
0x180002f93  cdq
0x180002f94  sub     eax, edx
0x180002f96  sar     eax, 1
0x180002f98  mov     [rbx+0Ch], eax
0x180002f9b  jmp     short loc_180002FCC
0x180002f9d  mov     [rbx], rax
0x180002fa0  movsxd  rcx, dword ptr [rbx+8]
0x180002fa4  mov     edx, r12d
0x180002fa7  mov     rax, [rbx]
0x180002faa  mov     [rax+rcx*8], rdi
0x180002fae  inc     dword ptr [rbx+8]
0x180002fb1  jmp     short loc_180002FD1
0x180002fb3  call    cs:__imp_CoTaskMemFree
0x180002fb9  mov     rcx, [rdi+8]; pv
0x180002fbd  call    cs:__imp_CoTaskMemFree
0x180002fc3  mov     rcx, rdi
0x180002fc6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002fcc  mov     edx, 8007000Eh
0x180002fd1  mov     eax, edx
0x180002fd3  add     rsp, 20h
0x180002fd7  pop     r15
0x180002fd9  pop     r14
0x180002fdb  pop     r12
0x180002fdd  pop     rdi
0x180002fde  pop     rsi
0x180002fdf  pop     rbp
0x180002fe0  pop     rbx
0x180002fe1  retn
```
