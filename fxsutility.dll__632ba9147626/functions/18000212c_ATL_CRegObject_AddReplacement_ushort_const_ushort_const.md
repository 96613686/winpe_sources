# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000212c`
- end: `0x18000226c`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `320`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180004680`

## callees

- `0x180001284`
- `0x1800012d0`
- `0x18000212c`
- `0x180015cb2`

## import_xrefs

- `msvcrt!realloc` at `0x1800021f5`
- `msvcrt!realloc` at `0x1800021f5`
- `ole32!CoTaskMemFree` at `0x180002203`
- `ole32!CoTaskMemFree` at `0x18000220d`
- `ole32!CoTaskMemFree` at `0x18000223e`
- `ole32!CoTaskMemFree` at `0x180002248`
- `ole32!CoTaskMemFree` at `0x180002203`
- `ole32!CoTaskMemFree` at `0x18000220d`
- `ole32!CoTaskMemFree` at `0x18000223e`
- `ole32!CoTaskMemFree` at `0x180002248`
- `ole32!CoTaskMemAlloc` at `0x180002199`
- `ole32!CoTaskMemAlloc` at `0x1800021ad`
- `ole32!CoTaskMemAlloc` at `0x180002199`
- `ole32!CoTaskMemAlloc` at `0x1800021ad`

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
0x18000212c  push    rbx
0x18000212e  push    rbp
0x18000212f  push    rsi
0x180002130  push    rdi
0x180002131  push    r12
0x180002133  push    r14
0x180002135  push    r15
0x180002137  sub     rsp, 20h
0x18000213b  mov     rbx, rcx
0x18000213e  mov     r14, r8
0x180002141  mov     ecx, 10h; Size
0x180002146  mov     rbp, rdx
0x180002149  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000214e  xor     r12d, r12d
0x180002151  mov     rdi, rax
0x180002154  test    rax, rax
0x180002157  jz      loc_180002256
0x18000215d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002161  test    rbp, rbp
0x180002164  jnz     short loc_18000216B
0x180002166  mov     eax, r12d
0x180002169  jmp     short loc_180002179
0x18000216b  mov     rax, rsi
0x18000216e  inc     rax
0x180002171  cmp     [rbp+rax*2+0], r12w
0x180002177  jnz     short loc_18000216E
0x180002179  test    r14, r14
0x18000217c  jnz     short loc_180002183
0x18000217e  mov     esi, r12d
0x180002181  jmp     short loc_18000218D
0x180002183  inc     rsi
0x180002186  cmp     [r14+rsi*2], r12w
0x18000218b  jnz     short loc_180002183
0x18000218d  lea     eax, ds:2[rax*2]
0x180002194  mov     ecx, eax; cb
0x180002196  mov     r15d, eax
0x180002199  call    cs:__imp_CoTaskMemAlloc
0x18000219f  mov     [rdi], rax
0x1800021a2  lea     eax, ds:2[rsi*2]
0x1800021a9  mov     ecx, eax; cb
0x1800021ab  mov     esi, eax
0x1800021ad  call    cs:__imp_CoTaskMemAlloc
0x1800021b3  mov     rcx, [rdi]; void *
0x1800021b6  mov     [rdi+8], rax
0x1800021ba  test    rcx, rcx
0x1800021bd  jz      short loc_18000223E
0x1800021bf  test    rax, rax
0x1800021c2  jz      short loc_18000223E
0x1800021c4  mov     r8d, r15d; Size
0x1800021c7  mov     rdx, rbp; Src
0x1800021ca  call    memcpy_0
0x1800021cf  mov     rcx, [rdi+8]; void *
0x1800021d3  mov     r8d, esi; Size
0x1800021d6  mov     rdx, r14; Src
0x1800021d9  call    memcpy_0
0x1800021de  mov     eax, [rbx+0Ch]
0x1800021e1  cmp     [rbx+8], eax
0x1800021e4  jnz     short loc_18000222B
0x1800021e6  mov     rcx, [rbx]; Block
0x1800021e9  add     eax, eax
0x1800021eb  movsxd  rdx, eax
0x1800021ee  shl     rdx, 3; Size
0x1800021f2  mov     [rbx+0Ch], eax
0x1800021f5  call    cs:__imp_realloc
0x1800021fb  test    rax, rax
0x1800021fe  jnz     short loc_180002228
0x180002200  mov     rcx, [rdi]; pv
0x180002203  call    cs:__imp_CoTaskMemFree
0x180002209  mov     rcx, [rdi+8]; pv
0x18000220d  call    cs:__imp_CoTaskMemFree
0x180002213  mov     rcx, rdi; Block
0x180002216  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000221b  mov     eax, [rbx+0Ch]
0x18000221e  cdq
0x18000221f  sub     eax, edx
0x180002221  sar     eax, 1
0x180002223  mov     [rbx+0Ch], eax
0x180002226  jmp     short loc_180002256
0x180002228  mov     [rbx], rax
0x18000222b  movsxd  rcx, dword ptr [rbx+8]
0x18000222f  mov     edx, r12d
0x180002232  mov     rax, [rbx]
0x180002235  mov     [rax+rcx*8], rdi
0x180002239  inc     dword ptr [rbx+8]
0x18000223c  jmp     short loc_18000225B
0x18000223e  call    cs:__imp_CoTaskMemFree
0x180002244  mov     rcx, [rdi+8]; pv
0x180002248  call    cs:__imp_CoTaskMemFree
0x18000224e  mov     rcx, rdi; Block
0x180002251  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002256  mov     edx, 8007000Eh
0x18000225b  mov     eax, edx
0x18000225d  add     rsp, 20h
0x180002261  pop     r15
0x180002263  pop     r14
0x180002265  pop     r12
0x180002267  pop     rdi
0x180002268  pop     rsi
0x180002269  pop     rbp
0x18000226a  pop     rbx
0x18000226b  retn
```
