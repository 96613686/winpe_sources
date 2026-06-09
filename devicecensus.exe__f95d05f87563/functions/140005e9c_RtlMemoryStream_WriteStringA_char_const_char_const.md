# RtlMemoryStream::WriteStringA(char const *,char const *)

- ea: `0x140005e9c`
- end: `0x1400060ab`
- name: `?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z`
- size: `527`
- prototype: `__int64 __fastcall(RtlMemoryStream *this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140006460`

## callees

- `0x140001fe6`
- `0x14000233f`
- `0x140005e9c`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x140005f5f`
- `ntdll!RtlReAllocateHeap` at `0x14000603c`
- `ntdll!RtlReAllocateHeap` at `0x140005f5f`
- `ntdll!RtlReAllocateHeap` at `0x14000603c`
- `ntdll!RtlAllocateHeap` at `0x140005f3f`
- `ntdll!RtlAllocateHeap` at `0x14000600b`
- `ntdll!RtlAllocateHeap` at `0x140005f3f`
- `ntdll!RtlAllocateHeap` at `0x14000600b`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteStringA(RtlMemoryStream *this, const char *a2, const char *a3)
{
  size_t v6; // rdi
  size_t v7; // rsi
  size_t *v8; // r15
  size_t v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  void *v13; // r8
  void *v14; // rcx
  SIZE_T v15; // r14
  PVOID v16; // rax
  PVOID Heap; // rbp
  size_t *v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  size_t *v22; // r14
  size_t v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rsi
  unsigned __int64 v26; // rax
  void *v27; // r8
  void *v28; // rcx
  SIZE_T v29; // rsi
  PVOID v30; // rax
  PVOID v31; // rbp
  _QWORD *v32; // rax
  size_t v33; // rcx
  size_t v34; // rax

  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    if ( !v6 )
      v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 )
    {
      v8 = (size_t *)((char *)this + 32);
      v9 = *((_QWORD *)this + 4);
      v10 = v9 + v7;
      if ( v9 + v7 < v9 )
        return 3221225485LL;
      if ( v10 <= *((_QWORD *)this + 2) )
      {
        v19 = v8;
      }
      else
      {
        v11 = *((_QWORD *)this + 3) - 1LL;
        v12 = v11 + v10;
        if ( v11 + v10 < v10 )
          return 3221225621LL;
        v13 = (void *)*((_QWORD *)this + 5);
        v14 = *(void **)this;
        v15 = v12 & ~v11;
        if ( v13 )
        {
          Heap = RtlReAllocateHeap(v14, 0, v13, v15);
        }
        else
        {
          v16 = RtlAllocateHeap(v14, 0, v15);
          Heap = v16;
          if ( v16 )
            memset_0(v16, 0, v15);
        }
        if ( !Heap )
          return 3221225495LL;
        *((_QWORD *)this + 5) = Heap;
        v19 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v15;
      }
      memcpy_0((void *)(*v19 + *((_QWORD *)this + 5)), a2, v7);
      v20 = *v8 + v7;
      if ( v20 < *v8 )
      {
        *v8 = -1;
        return 3221225621LL;
      }
      *v8 = v20;
      v21 = *((_QWORD *)this + 1);
      if ( v21 <= v20 )
        v21 = v20;
      *((_QWORD *)this + 1) = v21;
    }
  }
  if ( a3 && v6 )
  {
    v22 = (size_t *)((char *)this + 32);
    v23 = *((_QWORD *)this + 4);
    v24 = v23 + v6;
    if ( v23 + v6 >= v23 )
    {
      if ( v24 <= *((_QWORD *)this + 2) )
      {
        v32 = (_QWORD *)((char *)this + 32);
      }
      else
      {
        v25 = *((_QWORD *)this + 3) - 1LL;
        v26 = v24 + v25;
        if ( v24 + v25 < v24 )
          return 3221225621LL;
        v27 = (void *)*((_QWORD *)this + 5);
        v28 = *(void **)this;
        v29 = v26 & ~v25;
        if ( v27 )
        {
          v31 = RtlReAllocateHeap(v28, 0, v27, v29);
        }
        else
        {
          v30 = RtlAllocateHeap(v28, 0, v29);
          v31 = v30;
          if ( v30 )
            memset_0(v30, 0, v29);
        }
        if ( !v31 )
          return 3221225495LL;
        *((_QWORD *)this + 5) = v31;
        v32 = (_QWORD *)((char *)this + 32);
        *((_QWORD *)this + 2) = v29;
      }
      memcpy_0((void *)(*v32 + *((_QWORD *)this + 5)), a3, v6);
      v33 = *v22 + v6;
      if ( v33 >= *v22 )
      {
        *v22 = v33;
        v34 = *((_QWORD *)this + 1);
        if ( v34 <= v33 )
          v34 = v33;
        *((_QWORD *)this + 1) = v34;
        return 0;
      }
      *v22 = -1;
      return 3221225621LL;
    }
    return 3221225485LL;
  }
  return 0;
}

```

## disassembly

```asm
0x140005e9c  push    rbx
0x140005e9e  push    rbp
0x140005e9f  push    rsi
0x140005ea0  push    rdi
0x140005ea1  push    r12
0x140005ea3  push    r13
0x140005ea5  push    r14
0x140005ea7  push    r15
0x140005ea9  sub     rsp, 28h
0x140005ead  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140005eb1  mov     r13, r8
0x140005eb4  mov     r12, rdx
0x140005eb7  mov     rbx, rcx
0x140005eba  test    r8, r8
0x140005ebd  jz      short loc_140005EDA
0x140005ebf  mov     rdi, rbp
0x140005ec2  inc     rdi
0x140005ec5  cmp     byte ptr [rdi+r8], 0
0x140005eca  jnz     short loc_140005EC2
0x140005ecc  mov     eax, 1
0x140005ed1  cmp     rdi, rax
0x140005ed4  cmovb   rdi, rax
0x140005ed8  jmp     short loc_140005EDC
0x140005eda  xor     edi, edi
0x140005edc  test    r12, r12
0x140005edf  jz      loc_140005FBC
0x140005ee5  mov     rsi, rbp
0x140005ee8  inc     rsi
0x140005eeb  cmp     byte ptr [rdx+rsi], 0
0x140005eef  jnz     short loc_140005EE8
0x140005ef1  test    rsi, rsi
0x140005ef4  jz      loc_140005FBC
0x140005efa  lea     r15, [rcx+20h]
0x140005efe  mov     rax, [r15]
0x140005f01  lea     rcx, [rax+rsi]
0x140005f05  cmp     rcx, rax
0x140005f08  jb      loc_140006032
0x140005f0e  cmp     rcx, [rbx+10h]
0x140005f12  jbe     short loc_140005F89
0x140005f14  mov     r14, [rbx+18h]
0x140005f18  dec     r14
0x140005f1b  lea     rax, [r14+rcx]
0x140005f1f  cmp     rax, rcx
0x140005f22  jb      loc_14000602B
0x140005f28  mov     r8, [rbx+28h]; Ptr
0x140005f2c  not     r14
0x140005f2f  mov     rcx, [rbx]; Heap
0x140005f32  and     r14, rax
0x140005f35  xor     edx, edx; Flags
0x140005f37  test    r8, r8
0x140005f3a  jnz     short loc_140005F5C
0x140005f3c  mov     r8, r14; Size
0x140005f3f  call    cs:__imp_RtlAllocateHeap
0x140005f45  mov     rbp, rax
0x140005f48  test    rax, rax
0x140005f4b  jz      short loc_140005F68
0x140005f4d  mov     r8, r14; Size
0x140005f50  xor     edx, edx; Val
0x140005f52  mov     rcx, rax; void *
0x140005f55  call    memset_0
0x140005f5a  jmp     short loc_140005F68
0x140005f5c  mov     r9, r14; Size
0x140005f5f  call    cs:__imp_RtlReAllocateHeap
0x140005f65  mov     rbp, rax
0x140005f68  test    rbp, rbp
0x140005f6b  jnz     short loc_140005F77
0x140005f6d  mov     eax, 0C0000017h
0x140005f72  jmp     loc_140006091
0x140005f77  mov     [rbx+28h], rbp
0x140005f7b  lea     rax, [rbx+20h]
0x140005f7f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140005f83  mov     [rbx+10h], r14
0x140005f87  jmp     short loc_140005F8C
0x140005f89  mov     rax, r15
0x140005f8c  mov     rcx, [rbx+28h]
0x140005f90  mov     r8, rsi; Size
0x140005f93  add     rcx, [rax]; void *
0x140005f96  mov     rdx, r12; Src
0x140005f99  call    memcpy_0
0x140005f9e  mov     rax, [r15]
0x140005fa1  lea     rcx, [rax+rsi]
0x140005fa5  cmp     rcx, rax
0x140005fa8  jb      short loc_140006028
0x140005faa  mov     [r15], rcx
0x140005fad  mov     rax, [rbx+8]
0x140005fb1  cmp     rax, rcx
0x140005fb4  cmovbe  rax, rcx
0x140005fb8  mov     [rbx+8], rax
0x140005fbc  test    r13, r13
0x140005fbf  jz      loc_14000608F
0x140005fc5  test    rdi, rdi
0x140005fc8  jz      loc_14000608F
0x140005fce  lea     r14, [rbx+20h]
0x140005fd2  mov     rax, [r14]
0x140005fd5  lea     rcx, [rax+rdi]
0x140005fd9  cmp     rcx, rax
0x140005fdc  jb      short loc_140006032
0x140005fde  cmp     rcx, [rbx+10h]
0x140005fe2  jbe     short loc_14000605C
0x140005fe4  mov     rsi, [rbx+18h]
0x140005fe8  dec     rsi
0x140005feb  lea     rax, [rcx+rsi]
0x140005fef  cmp     rax, rcx
0x140005ff2  jb      short loc_14000602B
0x140005ff4  mov     r8, [rbx+28h]; Ptr
0x140005ff8  not     rsi
0x140005ffb  mov     rcx, [rbx]; Heap
0x140005ffe  and     rsi, rax
0x140006001  xor     edx, edx; Flags
0x140006003  test    r8, r8
0x140006006  jnz     short loc_140006039
0x140006008  mov     r8, rsi; Size
0x14000600b  call    cs:__imp_RtlAllocateHeap
0x140006011  mov     rbp, rax
0x140006014  test    rax, rax
0x140006017  jz      short loc_140006045
0x140006019  mov     r8, rsi; Size
0x14000601c  xor     edx, edx; Val
0x14000601e  mov     rcx, rax; void *
0x140006021  call    memset_0
0x140006026  jmp     short loc_140006045
0x140006028  mov     [r15], rbp
0x14000602b  mov     eax, 0C0000095h
0x140006030  jmp     short loc_140006091
0x140006032  mov     eax, 0C000000Dh
0x140006037  jmp     short loc_140006091
0x140006039  mov     r9, rsi; Size
0x14000603c  call    cs:__imp_RtlReAllocateHeap
0x140006042  mov     rbp, rax
0x140006045  test    rbp, rbp
0x140006048  jz      loc_140005F6D
0x14000604e  mov     [rbx+28h], rbp
0x140006052  lea     rax, [rbx+20h]
0x140006056  mov     [rbx+10h], rsi
0x14000605a  jmp     short loc_14000605F
0x14000605c  mov     rax, r14
0x14000605f  mov     rcx, [rbx+28h]
0x140006063  mov     r8, rdi; Size
0x140006066  add     rcx, [rax]; void *
0x140006069  mov     rdx, r13; Src
0x14000606c  call    memcpy_0
0x140006071  mov     rax, [r14]
0x140006074  lea     rcx, [rax+rdi]
0x140006078  cmp     rcx, rax
0x14000607b  jb      short loc_1400060A2
0x14000607d  mov     [r14], rcx
0x140006080  mov     rax, [rbx+8]
0x140006084  cmp     rax, rcx
0x140006087  cmovbe  rax, rcx
0x14000608b  mov     [rbx+8], rax
0x14000608f  xor     eax, eax
0x140006091  add     rsp, 28h
0x140006095  pop     r15
0x140006097  pop     r14
0x140006099  pop     r13
0x14000609b  pop     r12
0x14000609d  pop     rdi
0x14000609e  pop     rsi
0x14000609f  pop     rbp
0x1400060a0  pop     rbx
0x1400060a1  retn
0x1400060a2  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1400060a9  jmp     short loc_14000602B
```
