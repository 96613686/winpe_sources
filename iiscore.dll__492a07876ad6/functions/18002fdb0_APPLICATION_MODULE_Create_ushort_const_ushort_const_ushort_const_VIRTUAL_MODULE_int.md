# APPLICATION_MODULE::Create(ushort const *,ushort const *,ushort const *,VIRTUAL_MODULE *,int)

- ea: `0x18002fdb0`
- end: `0x18002fee8`
- name: `?Create@APPLICATION_MODULE@@QEAAJPEBG00PEAVVIRTUAL_MODULE@@H@Z`
- size: `312`
- prototype: `int(APPLICATION_MODULE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct VIRTUAL_MODULE *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fef0`
- `0x180031310`

## callees

- `0x18002fdb0`
- `0x180037722`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fea7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fea7`

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
0x18002fdb0  push    rbx
0x18002fdb2  push    rbp
0x18002fdb3  push    rsi
0x18002fdb4  push    rdi
0x18002fdb5  push    r12
0x18002fdb7  push    r13
0x18002fdb9  push    r14
0x18002fdbb  push    r15
0x18002fdbd  sub     rsp, 28h
0x18002fdc1  mov     eax, [rsp+68h+arg_28]
0x18002fdc8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fdcc  mov     [rcx+4], eax
0x18002fdcf  xor     r13d, r13d
0x18002fdd2  mov     rax, [rsp+68h+arg_20]
0x18002fdda  mov     r12, r9
0x18002fddd  mov     r15, r8
0x18002fde0  mov     r14, rdx
0x18002fde3  mov     rsi, rcx
0x18002fde6  test    rax, rax
0x18002fde9  jz      short loc_18002FDF4
0x18002fdeb  mov     [rcx+20h], rax
0x18002fdef  jmp     loc_18002FE88
0x18002fdf4  mov     rax, rbx
0x18002fdf7  inc     rax
0x18002fdfa  cmp     [rdx+rax*2], r13w
0x18002fdff  jnz     short loc_18002FDF7
0x18002fe01  test    rax, rax
0x18002fe04  jz      short loc_18002FE40
0x18002fe06  lea     rbp, ds:2[rax*2]
0x18002fe0e  mov     ecx, 40h ; '@'; uFlags
0x18002fe13  mov     rdx, rbp; uBytes
0x18002fe16  call    cs:__imp_LocalAlloc
0x18002fe1d  nop     dword ptr [rax+rax+00h]
0x18002fe22  mov     rdi, rax
0x18002fe25  test    rax, rax
0x18002fe28  jz      loc_18002FEBB
0x18002fe2e  mov     r8, rbp; Size
0x18002fe31  mov     rdx, r14; Src
0x18002fe34  mov     rcx, rax; void *
0x18002fe37  call    memcpy_0
0x18002fe3c  mov     [rsi+8], rdi
0x18002fe40  mov     rax, rbx
0x18002fe43  inc     rax
0x18002fe46  cmp     [r15+rax*2], r13w
0x18002fe4b  jnz     short loc_18002FE43
0x18002fe4d  test    rax, rax
0x18002fe50  jz      short loc_18002FE88
0x18002fe52  lea     rbp, ds:2[rax*2]
0x18002fe5a  mov     ecx, 40h ; '@'; uFlags
0x18002fe5f  mov     rdx, rbp; uBytes
0x18002fe62  call    cs:__imp_LocalAlloc
0x18002fe69  nop     dword ptr [rax+rax+00h]
0x18002fe6e  mov     rdi, rax
0x18002fe71  test    rax, rax
0x18002fe74  jz      short loc_18002FEBB
0x18002fe76  mov     r8, rbp; Size
0x18002fe79  mov     rdx, r15; Src
0x18002fe7c  mov     rcx, rax; void *
0x18002fe7f  call    memcpy_0
0x18002fe84  mov     [rsi+10h], rdi
0x18002fe88  inc     rbx
0x18002fe8b  cmp     [r12+rbx*2], r13w
0x18002fe90  jnz     short loc_18002FE88
0x18002fe92  test    rbx, rbx
0x18002fe95  jz      short loc_18002FED4
0x18002fe97  lea     rdi, ds:2[rbx*2]
0x18002fe9f  mov     ecx, 40h ; '@'; uFlags
0x18002fea4  mov     rdx, rdi; uBytes
0x18002fea7  call    cs:__imp_LocalAlloc
0x18002feae  nop     dword ptr [rax+rax+00h]
0x18002feb3  mov     rbx, rax
0x18002feb6  test    rax, rax
0x18002feb9  jnz     short loc_18002FEC2
0x18002febb  mov     eax, 80070008h
0x18002fec0  jmp     short loc_18002FED6
0x18002fec2  mov     r8, rdi; Size
0x18002fec5  mov     rdx, r12; Src
0x18002fec8  mov     rcx, rbx; void *
0x18002fecb  call    memcpy_0
0x18002fed0  mov     [rsi+18h], rbx
0x18002fed4  xor     eax, eax
0x18002fed6  add     rsp, 28h
0x18002feda  pop     r15
0x18002fedc  pop     r14
0x18002fede  pop     r13
0x18002fee0  pop     r12
0x18002fee2  pop     rdi
0x18002fee3  pop     rsi
0x18002fee4  pop     rbp
0x18002fee5  pop     rbx
0x18002fee6  retn
```
