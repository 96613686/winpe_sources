# RtlMemoryStream::WriteString(ushort const *,ushort const *)

- ea: `0x18001614c`
- end: `0x180016371`
- name: `?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z`
- size: `549`
- prototype: `int(RtlMemoryStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800174a4`

## callees

- `0x1800027d6`
- `0x18001614c`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800161f6`
- `KERNEL32!HeapAlloc` at `0x1800162cc`
- `KERNEL32!HeapAlloc` at `0x1800161f6`
- `KERNEL32!HeapAlloc` at `0x1800162cc`
- `KERNEL32!HeapReAlloc` at `0x180016216`
- `KERNEL32!HeapReAlloc` at `0x1800162fd`
- `KERNEL32!HeapReAlloc` at `0x180016216`
- `KERNEL32!HeapReAlloc` at `0x1800162fd`

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
  void *v17; // rax
  LPVOID v18; // rbp
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
  void *v32; // rax
  LPVOID v33; // rbp
  _QWORD *v34; // rax
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
        return 160;
      if ( v11 <= *((_QWORD *)this + 2) )
      {
        v20 = v9;
      }
      else
      {
        v12 = *((_QWORD *)this + 3) - 1LL;
        v13 = v12 + v11;
        if ( v12 + v11 < v11 )
          return 534;
        v14 = (void *)*((_QWORD *)this + 5);
        v15 = *(void **)this;
        v16 = v13 & ~v12;
        if ( v14 )
        {
          v18 = HeapReAlloc(v15, 0, v14, v16);
        }
        else
        {
          v17 = HeapAlloc(v15, 0, v16);
          v18 = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( !v18 )
          return 14;
        *((_QWORD *)this + 5) = v18;
        v20 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v16;
      }
      memcpy_0((void *)(*((_QWORD *)this + 5) + *v20), a2, v8);
      v21 = *v9 + v8;
      if ( v21 < *v9 )
      {
        *v9 = -1;
        return 534;
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
            return 534;
          v29 = (void *)*((_QWORD *)this + 5);
          v30 = *(void **)this;
          v31 = v28 & ~v27;
          if ( v29 )
          {
            v33 = HeapReAlloc(v30, 0, v29, v31);
          }
          else
          {
            v32 = HeapAlloc(v30, 0, v31);
            v33 = v32;
            if ( v32 )
              memset_0(v32, 0, v31);
          }
          if ( !v33 )
            return 14;
          *((_QWORD *)this + 5) = v33;
          v34 = (_QWORD *)((char *)this + 32);
          *((_QWORD *)this + 2) = v31;
        }
        memcpy_0((void *)(*v34 + *((_QWORD *)this + 5)), a3, v23);
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
        return 534;
      }
      return 160;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001614c  push    rbx
0x18001614e  push    rbp
0x18001614f  push    rsi
0x180016150  push    rdi
0x180016151  push    r12
0x180016153  push    r13
0x180016155  push    r14
0x180016157  push    r15
0x180016159  sub     rsp, 28h
0x18001615d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016161  xor     ebp, ebp
0x180016163  mov     r13, r8
0x180016166  mov     r12, rdx
0x180016169  mov     rbx, rcx
0x18001616c  test    r8, r8
0x18001616f  jz      short loc_18001618C
0x180016171  mov     rdi, rsi
0x180016174  inc     rdi
0x180016177  cmp     [r8+rdi*2], bp
0x18001617c  jnz     short loc_180016174
0x18001617e  mov     eax, 1
0x180016183  cmp     rdi, rax
0x180016186  cmovb   rdi, rax
0x18001618a  jmp     short loc_18001618F
0x18001618c  mov     rdi, rbp
0x18001618f  test    r12, r12
0x180016192  jz      loc_180016279
0x180016198  mov     rax, rsi
0x18001619b  inc     rax
0x18001619e  cmp     [rdx+rax*2], bp
0x1800161a2  jnz     short loc_18001619B
0x1800161a4  lea     r15, [rax+rax]
0x1800161a8  test    r15, r15
0x1800161ab  jz      loc_180016279
0x1800161b1  lea     r14, [rcx+20h]
0x1800161b5  mov     rax, [r14]
0x1800161b8  lea     rcx, [rax+r15]
0x1800161bc  cmp     rcx, rax
0x1800161bf  jb      loc_1800162F3
0x1800161c5  cmp     rcx, [rbx+10h]
0x1800161c9  jbe     short loc_180016242
0x1800161cb  mov     rsi, [rbx+18h]
0x1800161cf  dec     rsi
0x1800161d2  lea     rax, [rsi+rcx]
0x1800161d6  cmp     rax, rcx
0x1800161d9  jb      loc_1800162EC
0x1800161df  mov     r8, [rbx+28h]; lpMem
0x1800161e3  not     rsi
0x1800161e6  mov     rcx, [rbx]; hHeap
0x1800161e9  and     rsi, rax
0x1800161ec  xor     edx, edx; dwFlags
0x1800161ee  test    r8, r8
0x1800161f1  jnz     short loc_180016213
0x1800161f3  mov     r8, rsi; dwBytes
0x1800161f6  call    cs:__imp_HeapAlloc
0x1800161fc  mov     rbp, rax
0x1800161ff  test    rax, rax
0x180016202  jz      short loc_18001621F
0x180016204  mov     r8, rsi; Size
0x180016207  xor     edx, edx; Val
0x180016209  mov     rcx, rax; void *
0x18001620c  call    memset_0
0x180016211  jmp     short loc_18001621F
0x180016213  mov     r9, rsi; dwBytes
0x180016216  call    cs:__imp_HeapReAlloc
0x18001621c  mov     rbp, rax
0x18001621f  test    rbp, rbp
0x180016222  jnz     short loc_18001622E
0x180016224  mov     eax, 0Eh
0x180016229  jmp     loc_180016354
0x18001622e  mov     [rbx+28h], rbp
0x180016232  lea     rcx, [rbx+20h]
0x180016236  xor     ebp, ebp
0x180016238  mov     [rbx+10h], rsi
0x18001623c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016240  jmp     short loc_180016245
0x180016242  mov     rcx, r14
0x180016245  mov     rcx, [rcx]
0x180016248  mov     r8, r15; Size
0x18001624b  add     rcx, [rbx+28h]; void *
0x18001624f  mov     rdx, r12; Src
0x180016252  call    memcpy_0
0x180016257  mov     rax, [r14]
0x18001625a  lea     rcx, [rax+r15]
0x18001625e  cmp     rcx, rax
0x180016261  jb      loc_1800162E9
0x180016267  mov     [r14], rcx
0x18001626a  mov     rax, [rbx+8]
0x18001626e  cmp     rax, rcx
0x180016271  cmovbe  rax, rcx
0x180016275  mov     [rbx+8], rax
0x180016279  test    r13, r13
0x18001627c  jz      loc_180016352
0x180016282  lea     r14, [rdi+rdi]
0x180016286  test    r14, r14
0x180016289  jz      loc_180016352
0x18001628f  lea     rsi, [rbx+20h]
0x180016293  mov     rax, [rsi]
0x180016296  lea     rcx, [rax+r14]
0x18001629a  cmp     rcx, rax
0x18001629d  jb      short loc_1800162F3
0x18001629f  cmp     rcx, [rbx+10h]
0x1800162a3  jbe     short loc_18001631F
0x1800162a5  mov     rdi, [rbx+18h]
0x1800162a9  dec     rdi
0x1800162ac  lea     rax, [rcx+rdi]
0x1800162b0  cmp     rax, rcx
0x1800162b3  jb      short loc_1800162EC
0x1800162b5  mov     r8, [rbx+28h]; lpMem
0x1800162b9  not     rdi
0x1800162bc  mov     rcx, [rbx]; hHeap
0x1800162bf  and     rdi, rax
0x1800162c2  xor     edx, edx; dwFlags
0x1800162c4  test    r8, r8
0x1800162c7  jnz     short loc_1800162FA
0x1800162c9  mov     r8, rdi; dwBytes
0x1800162cc  call    cs:__imp_HeapAlloc
0x1800162d2  mov     rbp, rax
0x1800162d5  test    rax, rax
0x1800162d8  jz      short loc_180016306
0x1800162da  mov     r8, rdi; Size
0x1800162dd  xor     edx, edx; Val
0x1800162df  mov     rcx, rax; void *
0x1800162e2  call    memset_0
0x1800162e7  jmp     short loc_180016306
0x1800162e9  mov     [r14], rsi
0x1800162ec  mov     eax, 216h
0x1800162f1  jmp     short loc_180016354
0x1800162f3  mov     eax, 0A0h
0x1800162f8  jmp     short loc_180016354
0x1800162fa  mov     r9, rdi; dwBytes
0x1800162fd  call    cs:__imp_HeapReAlloc
0x180016303  mov     rbp, rax
0x180016306  test    rbp, rbp
0x180016309  jz      loc_180016224
0x18001630f  mov     [rbx+28h], rbp
0x180016313  lea     rax, [rbx+20h]
0x180016317  xor     ebp, ebp
0x180016319  mov     [rbx+10h], rdi
0x18001631d  jmp     short loc_180016322
0x18001631f  mov     rax, rsi
0x180016322  mov     rcx, [rbx+28h]
0x180016326  mov     r8, r14; Size
0x180016329  add     rcx, [rax]; void *
0x18001632c  mov     rdx, r13; Src
0x18001632f  call    memcpy_0
0x180016334  mov     rax, [rsi]
0x180016337  lea     rcx, [r14+rax]
0x18001633b  cmp     rcx, rax
0x18001633e  jb      short loc_180016365
0x180016340  mov     [rsi], rcx
0x180016343  mov     rax, [rbx+8]
0x180016347  cmp     rax, rcx
0x18001634a  cmovbe  rax, rcx
0x18001634e  mov     [rbx+8], rax
0x180016352  mov     eax, ebp
0x180016354  add     rsp, 28h
0x180016358  pop     r15
0x18001635a  pop     r14
0x18001635c  pop     r13
0x18001635e  pop     r12
0x180016360  pop     rdi
0x180016361  pop     rsi
0x180016362  pop     rbp
0x180016363  pop     rbx
0x180016364  retn
0x180016365  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18001636c  jmp     loc_1800162EC
```
