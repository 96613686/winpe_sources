# RtlMemoryStream::WriteString(ushort const *,ushort const *)

- ea: `0x140005c70`
- end: `0x140005e95`
- name: `?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z`
- size: `549`
- prototype: `__int64 __fastcall(RtlMemoryStream *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140006460`

## callees

- `0x140001fe6`
- `0x14000233f`
- `0x140005c70`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x140005d3a`
- `ntdll!RtlReAllocateHeap` at `0x140005e21`
- `ntdll!RtlReAllocateHeap` at `0x140005d3a`
- `ntdll!RtlReAllocateHeap` at `0x140005e21`
- `ntdll!RtlAllocateHeap` at `0x140005d1a`
- `ntdll!RtlAllocateHeap` at `0x140005df0`
- `ntdll!RtlAllocateHeap` at `0x140005d1a`
- `ntdll!RtlAllocateHeap` at `0x140005df0`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteString(
        RtlMemoryStream *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  size_t v8; // r15
  size_t *v9; // r14
  size_t v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rsi
  unsigned __int64 v13; // rax
  void *v14; // r8
  void *v15; // rcx
  SIZE_T v16; // rsi
  PVOID v17; // rax
  PVOID Heap; // rbp
  size_t *v20; // rcx
  size_t v21; // rcx
  size_t v22; // rax
  size_t v23; // r14
  size_t *v24; // rsi
  size_t v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rdi
  unsigned __int64 v28; // rax
  void *v29; // r8
  void *v30; // rcx
  SIZE_T v31; // rdi
  PVOID v32; // rax
  PVOID v33; // rbp
  _QWORD *v34; // rcx
  size_t v35; // rcx
  size_t v36; // rax

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
    v8 = 2 * v7;
    if ( 2 * v7 )
    {
      v9 = (size_t *)((char *)this + 32);
      v10 = *((_QWORD *)this + 4);
      v11 = v10 + v8;
      if ( v10 + v8 < v10 )
        return 3221225485LL;
      if ( v11 <= *((_QWORD *)this + 2) )
      {
        v20 = v9;
      }
      else
      {
        v12 = *((_QWORD *)this + 3) - 1LL;
        v13 = v12 + v11;
        if ( v12 + v11 < v11 )
          return 3221225621LL;
        v14 = (void *)*((_QWORD *)this + 5);
        v15 = *(void **)this;
        v16 = v13 & ~v12;
        if ( v14 )
        {
          Heap = RtlReAllocateHeap(v15, 0, v14, v16);
        }
        else
        {
          v17 = RtlAllocateHeap(v15, 0, v16);
          Heap = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( !Heap )
          return 3221225495LL;
        *((_QWORD *)this + 5) = Heap;
        v20 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v16;
      }
      memcpy_0((void *)(*((_QWORD *)this + 5) + *v20), a2, v8);
      v21 = *v9 + v8;
      if ( v21 < *v9 )
      {
        *v9 = -1;
        return 3221225621LL;
      }
      *v9 = v21;
      v22 = *((_QWORD *)this + 1);
      if ( v22 <= v21 )
        v22 = v21;
      *((_QWORD *)this + 1) = v22;
    }
  }
  if ( a3 )
  {
    v23 = 2 * v6;
    if ( 2 * v6 )
    {
      v24 = (size_t *)((char *)this + 32);
      v25 = *((_QWORD *)this + 4);
      v26 = v25 + v23;
      if ( v25 + v23 >= v25 )
      {
        if ( v26 <= *((_QWORD *)this + 2) )
        {
          v34 = (_QWORD *)((char *)this + 32);
        }
        else
        {
          v27 = *((_QWORD *)this + 3) - 1LL;
          v28 = v26 + v27;
          if ( v26 + v27 < v26 )
            return 3221225621LL;
          v29 = (void *)*((_QWORD *)this + 5);
          v30 = *(void **)this;
          v31 = v28 & ~v27;
          if ( v29 )
          {
            v33 = RtlReAllocateHeap(v30, 0, v29, v31);
          }
          else
          {
            v32 = RtlAllocateHeap(v30, 0, v31);
            v33 = v32;
            if ( v32 )
              memset_0(v32, 0, v31);
          }
          if ( !v33 )
            return 3221225495LL;
          *((_QWORD *)this + 5) = v33;
          v34 = (_QWORD *)((char *)this + 32);
          *((_QWORD *)this + 2) = v31;
        }
        memcpy_0((void *)(*((_QWORD *)this + 5) + *v34), a3, v23);
        v35 = v23 + *v24;
        if ( v35 >= *v24 )
        {
          *v24 = v35;
          v36 = *((_QWORD *)this + 1);
          if ( v36 <= v35 )
            v36 = v35;
          *((_QWORD *)this + 1) = v36;
          return 0;
        }
        *v24 = -1;
        return 3221225621LL;
      }
      return 3221225485LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005c70  push    rbx
0x140005c72  push    rbp
0x140005c73  push    rsi
0x140005c74  push    rdi
0x140005c75  push    r12
0x140005c77  push    r13
0x140005c79  push    r14
0x140005c7b  push    r15
0x140005c7d  sub     rsp, 28h
0x140005c81  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140005c85  xor     ebp, ebp
0x140005c87  mov     r13, r8
0x140005c8a  mov     r12, rdx
0x140005c8d  mov     rbx, rcx
0x140005c90  test    r8, r8
0x140005c93  jz      short loc_140005CB0
0x140005c95  mov     rdi, rsi
0x140005c98  inc     rdi
0x140005c9b  cmp     [r8+rdi*2], bp
0x140005ca0  jnz     short loc_140005C98
0x140005ca2  mov     eax, 1
0x140005ca7  cmp     rdi, rax
0x140005caa  cmovb   rdi, rax
0x140005cae  jmp     short loc_140005CB3
0x140005cb0  mov     rdi, rbp
0x140005cb3  test    r12, r12
0x140005cb6  jz      loc_140005D9D
0x140005cbc  mov     rax, rsi
0x140005cbf  inc     rax
0x140005cc2  cmp     [rdx+rax*2], bp
0x140005cc6  jnz     short loc_140005CBF
0x140005cc8  lea     r15, [rax+rax]
0x140005ccc  test    r15, r15
0x140005ccf  jz      loc_140005D9D
0x140005cd5  lea     r14, [rcx+20h]
0x140005cd9  mov     rax, [r14]
0x140005cdc  lea     rcx, [rax+r15]
0x140005ce0  cmp     rcx, rax
0x140005ce3  jb      loc_140005E17
0x140005ce9  cmp     rcx, [rbx+10h]
0x140005ced  jbe     short loc_140005D66
0x140005cef  mov     rsi, [rbx+18h]
0x140005cf3  dec     rsi
0x140005cf6  lea     rax, [rsi+rcx]
0x140005cfa  cmp     rax, rcx
0x140005cfd  jb      loc_140005E10
0x140005d03  mov     r8, [rbx+28h]; Ptr
0x140005d07  not     rsi
0x140005d0a  mov     rcx, [rbx]; Heap
0x140005d0d  and     rsi, rax
0x140005d10  xor     edx, edx; Flags
0x140005d12  test    r8, r8
0x140005d15  jnz     short loc_140005D37
0x140005d17  mov     r8, rsi; Size
0x140005d1a  call    cs:__imp_RtlAllocateHeap
0x140005d20  mov     rbp, rax
0x140005d23  test    rax, rax
0x140005d26  jz      short loc_140005D43
0x140005d28  mov     r8, rsi; Size
0x140005d2b  xor     edx, edx; Val
0x140005d2d  mov     rcx, rax; void *
0x140005d30  call    memset_0
0x140005d35  jmp     short loc_140005D43
0x140005d37  mov     r9, rsi; Size
0x140005d3a  call    cs:__imp_RtlReAllocateHeap
0x140005d40  mov     rbp, rax
0x140005d43  test    rbp, rbp
0x140005d46  jnz     short loc_140005D52
0x140005d48  mov     eax, 0C0000017h
0x140005d4d  jmp     loc_140005E78
0x140005d52  mov     [rbx+28h], rbp
0x140005d56  lea     rcx, [rbx+20h]
0x140005d5a  xor     ebp, ebp
0x140005d5c  mov     [rbx+10h], rsi
0x140005d60  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140005d64  jmp     short loc_140005D69
0x140005d66  mov     rcx, r14
0x140005d69  mov     rcx, [rcx]
0x140005d6c  mov     r8, r15; Size
0x140005d6f  add     rcx, [rbx+28h]; void *
0x140005d73  mov     rdx, r12; Src
0x140005d76  call    memcpy_0
0x140005d7b  mov     rax, [r14]
0x140005d7e  lea     rcx, [rax+r15]
0x140005d82  cmp     rcx, rax
0x140005d85  jb      loc_140005E0D
0x140005d8b  mov     [r14], rcx
0x140005d8e  mov     rax, [rbx+8]
0x140005d92  cmp     rax, rcx
0x140005d95  cmovbe  rax, rcx
0x140005d99  mov     [rbx+8], rax
0x140005d9d  test    r13, r13
0x140005da0  jz      loc_140005E76
0x140005da6  lea     r14, [rdi+rdi]
0x140005daa  test    r14, r14
0x140005dad  jz      loc_140005E76
0x140005db3  lea     rsi, [rbx+20h]
0x140005db7  mov     rax, [rsi]
0x140005dba  lea     rcx, [rax+r14]
0x140005dbe  cmp     rcx, rax
0x140005dc1  jb      short loc_140005E17
0x140005dc3  cmp     rcx, [rbx+10h]
0x140005dc7  jbe     short loc_140005E43
0x140005dc9  mov     rdi, [rbx+18h]
0x140005dcd  dec     rdi
0x140005dd0  lea     rax, [rcx+rdi]
0x140005dd4  cmp     rax, rcx
0x140005dd7  jb      short loc_140005E10
0x140005dd9  mov     r8, [rbx+28h]; Ptr
0x140005ddd  not     rdi
0x140005de0  mov     rcx, [rbx]; Heap
0x140005de3  and     rdi, rax
0x140005de6  xor     edx, edx; Flags
0x140005de8  test    r8, r8
0x140005deb  jnz     short loc_140005E1E
0x140005ded  mov     r8, rdi; Size
0x140005df0  call    cs:__imp_RtlAllocateHeap
0x140005df6  mov     rbp, rax
0x140005df9  test    rax, rax
0x140005dfc  jz      short loc_140005E2A
0x140005dfe  mov     r8, rdi; Size
0x140005e01  xor     edx, edx; Val
0x140005e03  mov     rcx, rax; void *
0x140005e06  call    memset_0
0x140005e0b  jmp     short loc_140005E2A
0x140005e0d  mov     [r14], rsi
0x140005e10  mov     eax, 0C0000095h
0x140005e15  jmp     short loc_140005E78
0x140005e17  mov     eax, 0C000000Dh
0x140005e1c  jmp     short loc_140005E78
0x140005e1e  mov     r9, rdi; Size
0x140005e21  call    cs:__imp_RtlReAllocateHeap
0x140005e27  mov     rbp, rax
0x140005e2a  test    rbp, rbp
0x140005e2d  jz      loc_140005D48
0x140005e33  mov     [rbx+28h], rbp
0x140005e37  lea     rcx, [rbx+20h]
0x140005e3b  xor     ebp, ebp
0x140005e3d  mov     [rbx+10h], rdi
0x140005e41  jmp     short loc_140005E46
0x140005e43  mov     rcx, rsi
0x140005e46  mov     rcx, [rcx]
0x140005e49  mov     r8, r14; Size
0x140005e4c  add     rcx, [rbx+28h]; void *
0x140005e50  mov     rdx, r13; Src
0x140005e53  call    memcpy_0
0x140005e58  mov     rax, [rsi]
0x140005e5b  lea     rcx, [r14+rax]
0x140005e5f  cmp     rcx, rax
0x140005e62  jb      short loc_140005E89
0x140005e64  mov     [rsi], rcx
0x140005e67  mov     rax, [rbx+8]
0x140005e6b  cmp     rax, rcx
0x140005e6e  cmovbe  rax, rcx
0x140005e72  mov     [rbx+8], rax
0x140005e76  mov     eax, ebp
0x140005e78  add     rsp, 28h
0x140005e7c  pop     r15
0x140005e7e  pop     r14
0x140005e80  pop     r13
0x140005e82  pop     r12
0x140005e84  pop     rdi
0x140005e85  pop     rsi
0x140005e86  pop     rbp
0x140005e87  pop     rbx
0x140005e88  retn
0x140005e89  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140005e90  jmp     loc_140005E10
```
