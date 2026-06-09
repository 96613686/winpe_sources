# RtlMemoryStream::WriteString(ushort const *,ushort const *)

- ea: `0x1800098ac`
- end: `0x180009ad1`
- name: `?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z`
- size: `549`
- prototype: `int(RtlMemoryStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003560`

## callees

- `0x1800098ac`
- `0x18000bfe6`
- `0x18000bffe`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009956`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009956`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009976`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009a5d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009976`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009a5d`

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
0x1800098ac  push    rbx
0x1800098ae  push    rbp
0x1800098af  push    rsi
0x1800098b0  push    rdi
0x1800098b1  push    r12
0x1800098b3  push    r13
0x1800098b5  push    r14
0x1800098b7  push    r15
0x1800098b9  sub     rsp, 28h
0x1800098bd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800098c1  xor     ebp, ebp
0x1800098c3  mov     r13, r8
0x1800098c6  mov     r12, rdx
0x1800098c9  mov     rbx, rcx
0x1800098cc  test    r8, r8
0x1800098cf  jz      short loc_1800098EC
0x1800098d1  mov     rdi, rsi
0x1800098d4  inc     rdi
0x1800098d7  cmp     [r8+rdi*2], bp
0x1800098dc  jnz     short loc_1800098D4
0x1800098de  mov     eax, 1
0x1800098e3  cmp     rdi, rax
0x1800098e6  cmovb   rdi, rax
0x1800098ea  jmp     short loc_1800098EF
0x1800098ec  mov     rdi, rbp
0x1800098ef  test    r12, r12
0x1800098f2  jz      loc_1800099D9
0x1800098f8  mov     rax, rsi
0x1800098fb  inc     rax
0x1800098fe  cmp     [rdx+rax*2], bp
0x180009902  jnz     short loc_1800098FB
0x180009904  lea     r15, [rax+rax]
0x180009908  test    r15, r15
0x18000990b  jz      loc_1800099D9
0x180009911  lea     r14, [rcx+20h]
0x180009915  mov     rax, [r14]
0x180009918  lea     rcx, [rax+r15]
0x18000991c  cmp     rcx, rax
0x18000991f  jb      loc_180009A53
0x180009925  cmp     rcx, [rbx+10h]
0x180009929  jbe     short loc_1800099A2
0x18000992b  mov     rsi, [rbx+18h]
0x18000992f  dec     rsi
0x180009932  lea     rax, [rsi+rcx]
0x180009936  cmp     rax, rcx
0x180009939  jb      loc_180009A4C
0x18000993f  mov     r8, [rbx+28h]; lpMem
0x180009943  not     rsi
0x180009946  mov     rcx, [rbx]; hHeap
0x180009949  and     rsi, rax
0x18000994c  xor     edx, edx; dwFlags
0x18000994e  test    r8, r8
0x180009951  jnz     short loc_180009973
0x180009953  mov     r8, rsi; dwBytes
0x180009956  call    cs:__imp_HeapAlloc
0x18000995c  mov     rbp, rax
0x18000995f  test    rax, rax
0x180009962  jz      short loc_18000997F
0x180009964  mov     r8, rsi; Size
0x180009967  xor     edx, edx; Val
0x180009969  mov     rcx, rax; void *
0x18000996c  call    memset_0
0x180009971  jmp     short loc_18000997F
0x180009973  mov     r9, rsi; dwBytes
0x180009976  call    cs:__imp_HeapReAlloc
0x18000997c  mov     rbp, rax
0x18000997f  test    rbp, rbp
0x180009982  jnz     short loc_18000998E
0x180009984  mov     eax, 0Eh
0x180009989  jmp     loc_180009AB4
0x18000998e  mov     [rbx+28h], rbp
0x180009992  lea     rcx, [rbx+20h]
0x180009996  xor     ebp, ebp
0x180009998  mov     [rbx+10h], rsi
0x18000999c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800099a0  jmp     short loc_1800099A5
0x1800099a2  mov     rcx, r14
0x1800099a5  mov     rcx, [rcx]
0x1800099a8  mov     r8, r15; Size
0x1800099ab  add     rcx, [rbx+28h]; void *
0x1800099af  mov     rdx, r12; Src
0x1800099b2  call    memcpy_0
0x1800099b7  mov     rax, [r14]
0x1800099ba  lea     rcx, [rax+r15]
0x1800099be  cmp     rcx, rax
0x1800099c1  jb      loc_180009A49
0x1800099c7  mov     [r14], rcx
0x1800099ca  mov     rax, [rbx+8]
0x1800099ce  cmp     rax, rcx
0x1800099d1  cmovbe  rax, rcx
0x1800099d5  mov     [rbx+8], rax
0x1800099d9  test    r13, r13
0x1800099dc  jz      loc_180009AB2
0x1800099e2  lea     r14, [rdi+rdi]
0x1800099e6  test    r14, r14
0x1800099e9  jz      loc_180009AB2
0x1800099ef  lea     rsi, [rbx+20h]
0x1800099f3  mov     rax, [rsi]
0x1800099f6  lea     rcx, [rax+r14]
0x1800099fa  cmp     rcx, rax
0x1800099fd  jb      short loc_180009A53
0x1800099ff  cmp     rcx, [rbx+10h]
0x180009a03  jbe     short loc_180009A7F
0x180009a05  mov     rdi, [rbx+18h]
0x180009a09  dec     rdi
0x180009a0c  lea     rax, [rcx+rdi]
0x180009a10  cmp     rax, rcx
0x180009a13  jb      short loc_180009A4C
0x180009a15  mov     r8, [rbx+28h]; lpMem
0x180009a19  not     rdi
0x180009a1c  mov     rcx, [rbx]; hHeap
0x180009a1f  and     rdi, rax
0x180009a22  xor     edx, edx; dwFlags
0x180009a24  test    r8, r8
0x180009a27  jnz     short loc_180009A5A
0x180009a29  mov     r8, rdi; dwBytes
0x180009a2c  call    cs:__imp_HeapAlloc
0x180009a32  mov     rbp, rax
0x180009a35  test    rax, rax
0x180009a38  jz      short loc_180009A66
0x180009a3a  mov     r8, rdi; Size
0x180009a3d  xor     edx, edx; Val
0x180009a3f  mov     rcx, rax; void *
0x180009a42  call    memset_0
0x180009a47  jmp     short loc_180009A66
0x180009a49  mov     [r14], rsi
0x180009a4c  mov     eax, 216h
0x180009a51  jmp     short loc_180009AB4
0x180009a53  mov     eax, 0A0h
0x180009a58  jmp     short loc_180009AB4
0x180009a5a  mov     r9, rdi; dwBytes
0x180009a5d  call    cs:__imp_HeapReAlloc
0x180009a63  mov     rbp, rax
0x180009a66  test    rbp, rbp
0x180009a69  jz      loc_180009984
0x180009a6f  mov     [rbx+28h], rbp
0x180009a73  lea     rax, [rbx+20h]
0x180009a77  xor     ebp, ebp
0x180009a79  mov     [rbx+10h], rdi
0x180009a7d  jmp     short loc_180009A82
0x180009a7f  mov     rax, rsi
0x180009a82  mov     rcx, [rbx+28h]
0x180009a86  mov     r8, r14; Size
0x180009a89  add     rcx, [rax]; void *
0x180009a8c  mov     rdx, r13; Src
0x180009a8f  call    memcpy_0
0x180009a94  mov     rax, [rsi]
0x180009a97  lea     rcx, [r14+rax]
0x180009a9b  cmp     rcx, rax
0x180009a9e  jb      short loc_180009AC5
0x180009aa0  mov     [rsi], rcx
0x180009aa3  mov     rax, [rbx+8]
0x180009aa7  cmp     rax, rcx
0x180009aaa  cmovbe  rax, rcx
0x180009aae  mov     [rbx+8], rax
0x180009ab2  mov     eax, ebp
0x180009ab4  add     rsp, 28h
0x180009ab8  pop     r15
0x180009aba  pop     r14
0x180009abc  pop     r13
0x180009abe  pop     r12
0x180009ac0  pop     rdi
0x180009ac1  pop     rsi
0x180009ac2  pop     rbp
0x180009ac3  pop     rbx
0x180009ac4  retn
0x180009ac5  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180009acc  jmp     loc_180009A4C
```
