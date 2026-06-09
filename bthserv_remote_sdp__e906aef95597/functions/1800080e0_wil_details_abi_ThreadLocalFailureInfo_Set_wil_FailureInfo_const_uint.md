# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800080e0`
- end: `0x1800082ee`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `526`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000894c`

## callees

- `0x18000270c`
- `0x1800036b8`
- `0x180006764`
- `0x1800080e0`
- `0x18000a090`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081e7`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r14
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
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // r15
  __int64 v25; // rbp
  rsize_t v26; // rbp
  _BYTE *v27; // r8
  char **v28; // rdi
  rsize_t v29; // r14
  void *v30; // rax

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
    if ( v20 == v24 || !v27 || !*v27 )
      goto LABEL_40;
    do
      ++v4;
    while ( v27[v4] );
    v29 = v4 + 1;
    if ( v24 - v20 >= v29 )
    {
      memcpy_s(v20, v24 - v20, v27, v29);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v29;
    }
    else
    {
LABEL_40:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v30 = (void *)wil::details::WriteResultString<unsigned short const *>(
                    v20,
                    v24,
                    *((_QWORD *)a2 + 3),
                    (char *)this + 56);
    memset_0(v30, 0, v24 - (_BYTE *)v30);
  }
}

```

## disassembly

```asm
0x1800080e0  mov     [rsp+arg_0], rbx
0x1800080e5  mov     [rsp+arg_8], rbp
0x1800080ea  mov     [rsp+arg_10], rsi
0x1800080ef  push    rdi
0x1800080f0  push    r12
0x1800080f2  push    r13
0x1800080f4  push    r14
0x1800080f6  push    r15
0x1800080f8  sub     rsp, 20h
0x1800080fc  mov     [rcx+4], r8d
0x180008100  xor     r13d, r13d
0x180008103  mov     eax, [rdx+8]
0x180008106  mov     rsi, rcx
0x180008109  mov     [rcx+8], eax
0x18000810c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180008110  mov     [rcx+10h], r13
0x180008114  mov     r12, rdx
0x180008117  movzx   eax, word ptr [rdx+40h]
0x18000811b  mov     [rcx+18h], ax
0x18000811f  mov     al, [rdx]
0x180008121  mov     [rcx+1Ah], al
0x180008124  mov     [rcx+20h], r13
0x180008128  mov     rax, [rdx+88h]
0x18000812f  mov     [rcx+28h], rax
0x180008133  mov     rax, [rdx+90h]
0x18000813a  mov     [rcx+30h], rax
0x18000813e  mov     [rcx+38h], r13
0x180008142  mov     rcx, [rdx+38h]
0x180008146  test    rcx, rcx
0x180008149  jnz     short loc_180008150
0x18000814b  lea     eax, [rcx+1]
0x18000814e  jmp     short loc_18000815F
0x180008150  mov     rax, r14
0x180008153  inc     rax
0x180008156  cmp     [rcx+rax], r13b
0x18000815a  jnz     short loc_180008153
0x18000815c  inc     rax
0x18000815f  mov     rdx, [rdx+80h]
0x180008166  test    rdx, rdx
0x180008169  jnz     short loc_180008170
0x18000816b  lea     ecx, [rdx+1]
0x18000816e  jmp     short loc_18000817F
0x180008170  mov     rcx, r14
0x180008173  inc     rcx
0x180008176  cmp     [rdx+rcx], r13b
0x18000817a  jnz     short loc_180008173
0x18000817c  inc     rcx
0x18000817f  mov     r8, [r12+18h]; unsigned __int64
0x180008184  test    r8, r8
0x180008187  jnz     short loc_18000818F
0x180008189  lea     edx, [r8+2]
0x18000818d  jmp     short loc_1800081A4
0x18000818f  mov     rdx, r14
0x180008192  inc     rdx
0x180008195  cmp     [r8+rdx*2], r13w
0x18000819a  jnz     short loc_180008192
0x18000819c  lea     rdx, ds:2[rdx*2]
0x1800081a4  lea     rbp, [rdx+rcx]
0x1800081a8  add     rbp, rax
0x1800081ab  lea     rdi, [rsi+48h]
0x1800081af  cmp     [rsi+40h], r13
0x1800081b3  jz      short loc_1800081BA
0x1800081b5  cmp     [rdi], rbp
0x1800081b8  jnb     short loc_1800081FA
0x1800081ba  mov     rdx, rbp; dwBytes
0x1800081bd  mov     ecx, 8; dwFlags
0x1800081c2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800081c7  mov     r15, rax
0x1800081ca  test    rax, rax
0x1800081cd  jz      short loc_1800081FA
0x1800081cf  mov     rbx, [rsi+40h]
0x1800081d3  call    cs:__imp_GetProcessHeap
0x1800081da  nop     dword ptr [rax+rax+00h]
0x1800081df  mov     r8, rbx; lpMem
0x1800081e2  xor     edx, edx; dwFlags
0x1800081e4  mov     rcx, rax; hHeap
0x1800081e7  call    cs:__imp_HeapFree
0x1800081ee  nop     dword ptr [rax+rax+00h]
0x1800081f3  mov     [rsi+40h], r15
0x1800081f7  mov     [rdi], rbp
0x1800081fa  mov     rbx, [rsi+40h]
0x1800081fe  test    rbx, rbx
0x180008201  jz      loc_1800082D0
0x180008207  mov     rdx, [rdi]; DestinationSize
0x18000820a  lea     rdi, [rsi+10h]
0x18000820e  mov     r8, [r12+38h]; Source
0x180008213  lea     r15, [rdx+rbx]
0x180008217  cmp     rbx, r15
0x18000821a  jz      short loc_180008252
0x18000821c  test    r8, r8
0x18000821f  jz      short loc_180008252
0x180008221  cmp     [r8], r13b
0x180008224  jz      short loc_180008252
0x180008226  mov     rbp, r14
0x180008229  inc     rbp
0x18000822c  cmp     [r8+rbp], r13b
0x180008230  jnz     short loc_180008229
0x180008232  inc     rbp
0x180008235  cmp     rdx, rbp
0x180008238  jb      short loc_180008252
0x18000823a  mov     r9, rbp; SourceSize
0x18000823d  mov     rcx, rbx; Destination
0x180008240  call    memcpy_s
0x180008245  test    rdi, rdi
0x180008248  jz      short loc_18000824D
0x18000824a  mov     [rdi], rbx
0x18000824d  add     rbx, rbp
0x180008250  jmp     short loc_18000825A
0x180008252  test    rdi, rdi
0x180008255  jz      short loc_18000825A
0x180008257  mov     [rdi], r13
0x18000825a  mov     r8, [r12+80h]; Source
0x180008262  lea     rdi, [rsi+20h]
0x180008266  cmp     rbx, r15
0x180008269  jz      short loc_1800082A4
0x18000826b  test    r8, r8
0x18000826e  jz      short loc_1800082A4
0x180008270  cmp     [r8], r13b
0x180008273  jz      short loc_1800082A4
0x180008275  inc     r14
0x180008278  cmp     [r8+r14], r13b
0x18000827c  jnz     short loc_180008275
0x18000827e  mov     rdx, r15
0x180008281  inc     r14
0x180008284  sub     rdx, rbx; DestinationSize
0x180008287  cmp     rdx, r14
0x18000828a  jb      short loc_1800082A4
0x18000828c  mov     r9, r14; SourceSize
0x18000828f  mov     rcx, rbx; Destination
0x180008292  call    memcpy_s
0x180008297  test    rdi, rdi
0x18000829a  jz      short loc_18000829F
0x18000829c  mov     [rdi], rbx
0x18000829f  add     rbx, r14
0x1800082a2  jmp     short loc_1800082AC
0x1800082a4  test    rdi, rdi
0x1800082a7  jz      short loc_1800082AC
0x1800082a9  mov     [rdi], r13
0x1800082ac  mov     r8, [r12+18h]
0x1800082b1  lea     r9, [rsi+38h]
0x1800082b5  mov     rdx, r15
0x1800082b8  mov     rcx, rbx
0x1800082bb  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800082c0  sub     r15, rax
0x1800082c3  xor     edx, edx; Val
0x1800082c5  mov     r8, r15; Size
0x1800082c8  mov     rcx, rax; void *
0x1800082cb  call    memset_0
0x1800082d0  mov     rbx, [rsp+48h+arg_0]
0x1800082d5  mov     rbp, [rsp+48h+arg_8]
0x1800082da  mov     rsi, [rsp+48h+arg_10]
0x1800082df  add     rsp, 20h
0x1800082e3  pop     r15
0x1800082e5  pop     r14
0x1800082e7  pop     r13
0x1800082e9  pop     r12
0x1800082eb  pop     rdi
0x1800082ec  retn
```
