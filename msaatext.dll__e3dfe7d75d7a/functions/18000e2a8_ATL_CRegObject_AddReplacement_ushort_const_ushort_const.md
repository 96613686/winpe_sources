# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000e2a8`
- end: `0x18000e3ee`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `326`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180012314`

## callees

- `0x180001370`
- `0x180001f56`
- `0x18000e2a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e396`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e3d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e396`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e3d2`
- `msvcrt!realloc` at `0x18000e375`
- `msvcrt!realloc` at `0x18000e375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c9`

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
0x18000e2a8  push    rbx
0x18000e2aa  push    rbp
0x18000e2ab  push    rsi
0x18000e2ac  push    rdi
0x18000e2ad  push    r12
0x18000e2af  push    r14
0x18000e2b1  push    r15
0x18000e2b3  sub     rsp, 20h
0x18000e2b7  mov     rbx, rcx
0x18000e2ba  mov     r14, r8
0x18000e2bd  mov     ecx, 10h; Size
0x18000e2c2  mov     rbp, rdx
0x18000e2c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2ca  xor     r12d, r12d
0x18000e2cd  mov     rdi, rax
0x18000e2d0  test    rax, rax
0x18000e2d3  jz      loc_18000E3D8
0x18000e2d9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e2dd  test    rbp, rbp
0x18000e2e0  jnz     short loc_18000E2E7
0x18000e2e2  mov     eax, r12d
0x18000e2e5  jmp     short loc_18000E2F5
0x18000e2e7  mov     rax, rsi
0x18000e2ea  inc     rax
0x18000e2ed  cmp     [rbp+rax*2+0], r12w
0x18000e2f3  jnz     short loc_18000E2EA
0x18000e2f5  test    r14, r14
0x18000e2f8  jnz     short loc_18000E2FF
0x18000e2fa  mov     esi, r12d
0x18000e2fd  jmp     short loc_18000E309
0x18000e2ff  inc     rsi
0x18000e302  cmp     [r14+rsi*2], r12w
0x18000e307  jnz     short loc_18000E2FF
0x18000e309  lea     eax, ds:2[rax*2]
0x18000e310  mov     ecx, eax; cb
0x18000e312  mov     r15d, eax
0x18000e315  call    cs:__imp_CoTaskMemAlloc
0x18000e31b  mov     [rdi], rax
0x18000e31e  lea     eax, ds:2[rsi*2]
0x18000e325  mov     ecx, eax; cb
0x18000e327  mov     esi, eax
0x18000e329  call    cs:__imp_CoTaskMemAlloc
0x18000e32f  mov     rcx, [rdi]; pv
0x18000e332  mov     [rdi+8], rax
0x18000e336  test    rcx, rcx
0x18000e339  jz      loc_18000E3BF
0x18000e33f  test    rax, rax
0x18000e342  jz      short loc_18000E3BF
0x18000e344  mov     r8d, r15d; Size
0x18000e347  mov     rdx, rbp; Src
0x18000e34a  call    memcpy_0
0x18000e34f  mov     rcx, [rdi+8]; void *
0x18000e353  mov     r8d, esi; Size
0x18000e356  mov     rdx, r14; Src
0x18000e359  call    memcpy_0
0x18000e35e  mov     eax, [rbx+0Ch]
0x18000e361  cmp     [rbx+8], eax
0x18000e364  jnz     short loc_18000E3AC
0x18000e366  mov     rcx, [rbx]; Block
0x18000e369  add     eax, eax
0x18000e36b  movsxd  rdx, eax
0x18000e36e  shl     rdx, 3; Size
0x18000e372  mov     [rbx+0Ch], eax
0x18000e375  call    cs:__imp_realloc
0x18000e37b  test    rax, rax
0x18000e37e  jnz     short loc_18000E3A9
0x18000e380  mov     rcx, [rdi]; pv
0x18000e383  call    cs:__imp_CoTaskMemFree
0x18000e389  mov     rcx, [rdi+8]; pv
0x18000e38d  call    cs:__imp_CoTaskMemFree
0x18000e393  mov     rcx, rdi
0x18000e396  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e39c  mov     eax, [rbx+0Ch]
0x18000e39f  cdq
0x18000e3a0  sub     eax, edx
0x18000e3a2  sar     eax, 1
0x18000e3a4  mov     [rbx+0Ch], eax
0x18000e3a7  jmp     short loc_18000E3D8
0x18000e3a9  mov     [rbx], rax
0x18000e3ac  movsxd  rcx, dword ptr [rbx+8]
0x18000e3b0  mov     edx, r12d
0x18000e3b3  mov     rax, [rbx]
0x18000e3b6  mov     [rax+rcx*8], rdi
0x18000e3ba  inc     dword ptr [rbx+8]
0x18000e3bd  jmp     short loc_18000E3DD
0x18000e3bf  call    cs:__imp_CoTaskMemFree
0x18000e3c5  mov     rcx, [rdi+8]; pv
0x18000e3c9  call    cs:__imp_CoTaskMemFree
0x18000e3cf  mov     rcx, rdi
0x18000e3d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e3d8  mov     edx, 8007000Eh
0x18000e3dd  mov     eax, edx
0x18000e3df  add     rsp, 20h
0x18000e3e3  pop     r15
0x18000e3e5  pop     r14
0x18000e3e7  pop     r12
0x18000e3e9  pop     rdi
0x18000e3ea  pop     rsi
0x18000e3eb  pop     rbp
0x18000e3ec  pop     rbx
0x18000e3ed  retn
```
