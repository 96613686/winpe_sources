# APPLICATION_MODULE::Create(ushort const *,ushort const *,ushort const *,VIRTUAL_MODULE *,int)

- ea: `0x18002d3a0`
- end: `0x18002d4c5`
- name: `?Create@APPLICATION_MODULE@@QEAAJPEBG00PEAVVIRTUAL_MODULE@@H@Z`
- size: `293`
- prototype: `int(APPLICATION_MODULE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct VIRTUAL_MODULE *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d4cc`
- `0x18002e740`

## callees

- `0x18002d3a0`
- `0x180034382`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d406`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d44c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d48b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d406`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d44c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d48b`

## pseudocode

```c
__int64 __fastcall APPLICATION_MODULE::Create(
        APPLICATION_MODULE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct VIRTUAL_MODULE *a5,
        int a6)
{
  __int64 v6; // rbx
  __int64 v11; // rax
  SIZE_T v12; // rbp
  HLOCAL v13; // rax
  HLOCAL v14; // rdi
  __int64 v15; // rax
  SIZE_T v16; // rbp
  HLOCAL v17; // rax
  HLOCAL v18; // rdi
  SIZE_T v19; // rdi
  HLOCAL v20; // rax
  HLOCAL v21; // rbx

  v6 = -1;
  *((_DWORD *)this + 1) = a6;
  if ( a5 )
  {
    *((_QWORD *)this + 4) = a5;
    goto LABEL_13;
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 )
  {
    v12 = 2 * v11 + 2;
    v13 = LocalAlloc(0x40u, v12);
    v14 = v13;
    if ( !v13 )
      return 2147942408LL;
    memcpy_0(v13, a2, v12);
    *((_QWORD *)this + 1) = v14;
  }
  v15 = -1;
  do
    ++v15;
  while ( a3[v15] );
  if ( !v15 )
    goto LABEL_13;
  v16 = 2 * v15 + 2;
  v17 = LocalAlloc(0x40u, v16);
  v18 = v17;
  if ( !v17 )
    return 2147942408LL;
  memcpy_0(v17, a3, v16);
  *((_QWORD *)this + 2) = v18;
  do
LABEL_13:
    ++v6;
  while ( a4[v6] );
  if ( v6 )
  {
    v19 = 2 * v6 + 2;
    v20 = LocalAlloc(0x40u, v19);
    v21 = v20;
    if ( !v20 )
      return 2147942408LL;
    memcpy_0(v20, a4, v19);
    *((_QWORD *)this + 3) = v21;
  }
  return 0;
}

```

## disassembly

```asm
0x18002d3a0  push    rbx
0x18002d3a2  push    rbp
0x18002d3a3  push    rsi
0x18002d3a4  push    rdi
0x18002d3a5  push    r12
0x18002d3a7  push    r13
0x18002d3a9  push    r14
0x18002d3ab  push    r15
0x18002d3ad  sub     rsp, 28h
0x18002d3b1  mov     eax, [rsp+68h+arg_28]
0x18002d3b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d3bc  mov     [rcx+4], eax
0x18002d3bf  xor     r13d, r13d
0x18002d3c2  mov     rax, [rsp+68h+arg_20]
0x18002d3ca  mov     r12, r9
0x18002d3cd  mov     r15, r8
0x18002d3d0  mov     r14, rdx
0x18002d3d3  mov     rsi, rcx
0x18002d3d6  test    rax, rax
0x18002d3d9  jz      short loc_18002D3E4
0x18002d3db  mov     [rcx+20h], rax
0x18002d3df  jmp     loc_18002D46C
0x18002d3e4  mov     rax, rbx
0x18002d3e7  inc     rax
0x18002d3ea  cmp     [rdx+rax*2], r13w
0x18002d3ef  jnz     short loc_18002D3E7
0x18002d3f1  test    rax, rax
0x18002d3f4  jz      short loc_18002D42A
0x18002d3f6  lea     rbp, ds:2[rax*2]
0x18002d3fe  mov     ecx, 40h ; '@'; uFlags
0x18002d403  mov     rdx, rbp; uBytes
0x18002d406  call    cs:__imp_LocalAlloc
0x18002d40c  mov     rdi, rax
0x18002d40f  test    rax, rax
0x18002d412  jz      loc_18002D499
0x18002d418  mov     r8, rbp; Size
0x18002d41b  mov     rdx, r14; Src
0x18002d41e  mov     rcx, rax; void *
0x18002d421  call    memcpy_0
0x18002d426  mov     [rsi+8], rdi
0x18002d42a  mov     rax, rbx
0x18002d42d  inc     rax
0x18002d430  cmp     [r15+rax*2], r13w
0x18002d435  jnz     short loc_18002D42D
0x18002d437  test    rax, rax
0x18002d43a  jz      short loc_18002D46C
0x18002d43c  lea     rbp, ds:2[rax*2]
0x18002d444  mov     ecx, 40h ; '@'; uFlags
0x18002d449  mov     rdx, rbp; uBytes
0x18002d44c  call    cs:__imp_LocalAlloc
0x18002d452  mov     rdi, rax
0x18002d455  test    rax, rax
0x18002d458  jz      short loc_18002D499
0x18002d45a  mov     r8, rbp; Size
0x18002d45d  mov     rdx, r15; Src
0x18002d460  mov     rcx, rax; void *
0x18002d463  call    memcpy_0
0x18002d468  mov     [rsi+10h], rdi
0x18002d46c  inc     rbx
0x18002d46f  cmp     [r12+rbx*2], r13w
0x18002d474  jnz     short loc_18002D46C
0x18002d476  test    rbx, rbx
0x18002d479  jz      short loc_18002D4B2
0x18002d47b  lea     rdi, ds:2[rbx*2]
0x18002d483  mov     ecx, 40h ; '@'; uFlags
0x18002d488  mov     rdx, rdi; uBytes
0x18002d48b  call    cs:__imp_LocalAlloc
0x18002d491  mov     rbx, rax
0x18002d494  test    rax, rax
0x18002d497  jnz     short loc_18002D4A0
0x18002d499  mov     eax, 80070008h
0x18002d49e  jmp     short loc_18002D4B4
0x18002d4a0  mov     r8, rdi; Size
0x18002d4a3  mov     rdx, r12; Src
0x18002d4a6  mov     rcx, rbx; void *
0x18002d4a9  call    memcpy_0
0x18002d4ae  mov     [rsi+18h], rbx
0x18002d4b2  xor     eax, eax
0x18002d4b4  add     rsp, 28h
0x18002d4b8  pop     r15
0x18002d4ba  pop     r14
0x18002d4bc  pop     r13
0x18002d4be  pop     r12
0x18002d4c0  pop     rdi
0x18002d4c1  pop     rsi
0x18002d4c2  pop     rbp
0x18002d4c3  pop     rbx
0x18002d4c4  retn
```
