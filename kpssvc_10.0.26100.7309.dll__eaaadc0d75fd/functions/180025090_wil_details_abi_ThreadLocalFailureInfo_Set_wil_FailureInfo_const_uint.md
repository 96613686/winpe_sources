# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180025090`
- end: `0x1800252f4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `612`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025424`

## callees

- `0x180023520`
- `0x180025090`
- `0x18003100e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800251ee`
- `msvcrt!memcpy_s` at `0x180025249`
- `msvcrt!memcpy_s` at `0x1800252a5`
- `msvcrt!memcpy_s` at `0x1800251ee`
- `msvcrt!memcpy_s` at `0x180025249`
- `msvcrt!memcpy_s` at `0x1800252a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025182`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025196`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r12
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r14
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // r14
  __int64 v25; // rbp
  rsize_t v26; // rbp
  _BYTE *v27; // r8
  char **v28; // rdi
  __int64 v29; // rbp
  rsize_t v30; // rbp
  _WORD *v31; // r8
  char **v32; // rdi
  unsigned __int64 v33; // rsi

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v4 = -1;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v6 + v8) );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 1;
  }
  v9 = *((_QWORD *)a2 + 16);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v7 + v13 + v10;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v7 + v13 + v10);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = (char **)((char *)this + 16);
    v23 = (_BYTE *)*((_QWORD *)a2 + 7);
    v24 = &v20[v21];
    if ( v20 == &v20[v21] )
      goto LABEL_30;
    if ( !v23 )
      goto LABEL_30;
    if ( !*v23 )
      goto LABEL_30;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v26 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v26);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_30:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 )
      goto LABEL_41;
    if ( !v27 )
      goto LABEL_41;
    if ( !*v27 )
      goto LABEL_41;
    v29 = -1;
    do
      ++v29;
    while ( v27[v29] );
    v30 = v29 + 1;
    if ( v24 - v20 >= v30 )
    {
      memcpy_s(v20, v24 - v20, v27, v30);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v30;
    }
    else
    {
LABEL_41:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v31 = (_WORD *)*((_QWORD *)a2 + 3);
    v32 = (char **)((char *)this + 56);
    if ( v20 == v24 || !v31 || !*v31 )
      goto LABEL_51;
    do
      ++v4;
    while ( v31[v4] );
    v33 = 2 * v4 + 2;
    if ( v24 - v20 >= v33 )
    {
      memcpy_s(v20, v24 - v20, v31, 2 * v4 + 2);
      if ( v32 )
        *v32 = v20;
      v20 += v33;
    }
    else
    {
LABEL_51:
      if ( v32 )
        *v32 = 0;
    }
    memset_0(v20, 0, v24 - v20);
  }
}

```

## disassembly

```asm
0x180025090  mov     [rsp+arg_0], rbx
0x180025095  mov     [rsp+arg_8], rbp
0x18002509a  mov     [rsp+arg_10], rsi
0x18002509f  push    rdi
0x1800250a0  push    r12
0x1800250a2  push    r13
0x1800250a4  push    r14
0x1800250a6  push    r15
0x1800250a8  sub     rsp, 20h
0x1800250ac  mov     [rcx+4], r8d
0x1800250b0  xor     r13d, r13d
0x1800250b3  mov     eax, [rdx+8]
0x1800250b6  mov     rsi, rcx
0x1800250b9  mov     [rcx+8], eax
0x1800250bc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800250c0  mov     [rcx+10h], r13
0x1800250c4  mov     r15, rdx
0x1800250c7  movzx   eax, word ptr [rdx+40h]
0x1800250cb  mov     [rcx+18h], ax
0x1800250cf  mov     al, [rdx]
0x1800250d1  mov     [rcx+1Ah], al
0x1800250d4  mov     [rcx+20h], r13
0x1800250d8  mov     rax, [rdx+88h]
0x1800250df  mov     [rcx+28h], rax
0x1800250e3  mov     rax, [rdx+90h]
0x1800250ea  mov     [rcx+30h], rax
0x1800250ee  mov     [rcx+38h], r13
0x1800250f2  mov     rcx, [rdx+38h]
0x1800250f6  test    rcx, rcx
0x1800250f9  jnz     short loc_180025100
0x1800250fb  lea     eax, [rcx+1]
0x1800250fe  jmp     short loc_18002510F
0x180025100  mov     rax, r12
0x180025103  inc     rax
0x180025106  cmp     [rcx+rax], r13b
0x18002510a  jnz     short loc_180025103
0x18002510c  inc     rax
0x18002510f  mov     rdx, [rdx+80h]
0x180025116  test    rdx, rdx
0x180025119  jnz     short loc_180025120
0x18002511b  lea     ecx, [rdx+1]
0x18002511e  jmp     short loc_18002512F
0x180025120  mov     rcx, r12
0x180025123  inc     rcx
0x180025126  cmp     [rdx+rcx], r13b
0x18002512a  jnz     short loc_180025123
0x18002512c  inc     rcx
0x18002512f  mov     r8, [r15+18h]; unsigned __int64
0x180025133  test    r8, r8
0x180025136  jnz     short loc_18002513E
0x180025138  lea     edx, [r8+2]
0x18002513c  jmp     short loc_180025153
0x18002513e  mov     rdx, r12
0x180025141  inc     rdx
0x180025144  cmp     [r8+rdx*2], r13w
0x180025149  jnz     short loc_180025141
0x18002514b  lea     rdx, ds:2[rdx*2]
0x180025153  lea     rbp, [rdx+rcx]
0x180025157  add     rbp, rax
0x18002515a  lea     rdi, [rsi+48h]
0x18002515e  cmp     [rsi+40h], r13
0x180025162  jz      short loc_180025169
0x180025164  cmp     [rdi], rbp
0x180025167  jnb     short loc_1800251A9
0x180025169  mov     rdx, rbp; dwBytes
0x18002516c  mov     ecx, 8; dwFlags
0x180025171  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180025176  mov     r14, rax
0x180025179  test    rax, rax
0x18002517c  jz      short loc_1800251A9
0x18002517e  mov     rbx, [rsi+40h]
0x180025182  call    cs:__imp_GetProcessHeap
0x180025189  nop     dword ptr [rax+rax+00h]
0x18002518e  mov     r8, rbx; lpMem
0x180025191  xor     edx, edx; dwFlags
0x180025193  mov     rcx, rax; hHeap
0x180025196  call    cs:__imp_HeapFree
0x18002519d  nop     dword ptr [rax+rax+00h]
0x1800251a2  mov     [rsi+40h], r14
0x1800251a6  mov     [rdi], rbp
0x1800251a9  mov     rbx, [rsi+40h]
0x1800251ad  test    rbx, rbx
0x1800251b0  jz      loc_1800252D6
0x1800251b6  mov     rdx, [rdi]; DestinationSize
0x1800251b9  lea     rdi, [rsi+10h]
0x1800251bd  mov     r8, [r15+38h]; Source
0x1800251c1  lea     r14, [rdx+rbx]
0x1800251c5  cmp     rbx, r14
0x1800251c8  jz      short loc_180025207
0x1800251ca  test    r8, r8
0x1800251cd  jz      short loc_180025207
0x1800251cf  cmp     [r8], r13b
0x1800251d2  jz      short loc_180025207
0x1800251d4  mov     rbp, r12
0x1800251d7  inc     rbp
0x1800251da  cmp     [r8+rbp], r13b
0x1800251de  jnz     short loc_1800251D7
0x1800251e0  inc     rbp
0x1800251e3  cmp     rdx, rbp
0x1800251e6  jb      short loc_180025207
0x1800251e8  mov     r9, rbp; SourceSize
0x1800251eb  mov     rcx, rbx; Destination
0x1800251ee  call    cs:__imp_memcpy_s
0x1800251f5  nop     dword ptr [rax+rax+00h]
0x1800251fa  test    rdi, rdi
0x1800251fd  jz      short loc_180025202
0x1800251ff  mov     [rdi], rbx
0x180025202  add     rbx, rbp
0x180025205  jmp     short loc_18002520F
0x180025207  test    rdi, rdi
0x18002520a  jz      short loc_18002520F
0x18002520c  mov     [rdi], r13
0x18002520f  mov     r8, [r15+80h]; Source
0x180025216  lea     rdi, [rsi+20h]
0x18002521a  cmp     rbx, r14
0x18002521d  jz      short loc_180025262
0x18002521f  test    r8, r8
0x180025222  jz      short loc_180025262
0x180025224  cmp     [r8], r13b
0x180025227  jz      short loc_180025262
0x180025229  mov     rbp, r12
0x18002522c  inc     rbp
0x18002522f  cmp     [r8+rbp], r13b
0x180025233  jnz     short loc_18002522C
0x180025235  mov     rdx, r14
0x180025238  inc     rbp
0x18002523b  sub     rdx, rbx; DestinationSize
0x18002523e  cmp     rdx, rbp
0x180025241  jb      short loc_180025262
0x180025243  mov     r9, rbp; SourceSize
0x180025246  mov     rcx, rbx; Destination
0x180025249  call    cs:__imp_memcpy_s
0x180025250  nop     dword ptr [rax+rax+00h]
0x180025255  test    rdi, rdi
0x180025258  jz      short loc_18002525D
0x18002525a  mov     [rdi], rbx
0x18002525d  add     rbx, rbp
0x180025260  jmp     short loc_18002526A
0x180025262  test    rdi, rdi
0x180025265  jz      short loc_18002526A
0x180025267  mov     [rdi], r13
0x18002526a  mov     r8, [r15+18h]; Source
0x18002526e  lea     rdi, [rsi+38h]
0x180025272  cmp     rbx, r14
0x180025275  jz      short loc_1800252BE
0x180025277  test    r8, r8
0x18002527a  jz      short loc_1800252BE
0x18002527c  cmp     [r8], r13w
0x180025280  jz      short loc_1800252BE
0x180025282  inc     r12
0x180025285  cmp     [r8+r12*2], r13w
0x18002528a  jnz     short loc_180025282
0x18002528c  mov     rdx, r14
0x18002528f  lea     rsi, ds:2[r12*2]
0x180025297  sub     rdx, rbx; DestinationSize
0x18002529a  cmp     rdx, rsi
0x18002529d  jb      short loc_1800252BE
0x18002529f  mov     r9, rsi; SourceSize
0x1800252a2  mov     rcx, rbx; Destination
0x1800252a5  call    cs:__imp_memcpy_s
0x1800252ac  nop     dword ptr [rax+rax+00h]
0x1800252b1  test    rdi, rdi
0x1800252b4  jz      short loc_1800252B9
0x1800252b6  mov     [rdi], rbx
0x1800252b9  add     rbx, rsi
0x1800252bc  jmp     short loc_1800252C6
0x1800252be  test    rdi, rdi
0x1800252c1  jz      short loc_1800252C6
0x1800252c3  mov     [rdi], r13
0x1800252c6  sub     r14, rbx
0x1800252c9  xor     edx, edx; Val
0x1800252cb  mov     r8, r14; Size
0x1800252ce  mov     rcx, rbx; void *
0x1800252d1  call    memset_0
0x1800252d6  mov     rbx, [rsp+48h+arg_0]
0x1800252db  mov     rbp, [rsp+48h+arg_8]
0x1800252e0  mov     rsi, [rsp+48h+arg_10]
0x1800252e5  add     rsp, 20h
0x1800252e9  pop     r15
0x1800252eb  pop     r14
0x1800252ed  pop     r13
0x1800252ef  pop     r12
0x1800252f1  pop     rdi
0x1800252f2  retn
```
