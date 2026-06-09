# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006ea4`
- end: `0x18000713c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005340`

## callees

- `0x180004628`
- `0x1800064c4`
- `0x180006ea4`
- `0x18003586a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800070ff`
- `msvcrt!memcpy_s` at `0x1800070ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000706a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000706a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007056`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007056`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x180006ea4  push    rbx
0x180006ea6  push    rbp
0x180006ea7  push    rsi
0x180006ea8  push    rdi
0x180006ea9  push    r12
0x180006eab  push    r13
0x180006ead  push    r14
0x180006eaf  push    r15
0x180006eb1  sub     rsp, 28h
0x180006eb5  mov     esi, [rcx+10h]
0x180006eb8  xor     r12d, r12d
0x180006ebb  mov     r15, rdx
0x180006ebe  mov     rbx, rcx
0x180006ec1  mov     ebp, 50h ; 'P'
0x180006ec6  cmp     [rcx+18h], r12
0x180006eca  jnz     short loc_180006F01
0x180006ecc  test    esi, esi
0x180006ece  jz      short loc_180006F01
0x180006ed0  mov     edx, 190h; dwBytes
0x180006ed5  lea     ecx, [rbp-48h]; dwFlags
0x180006ed8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006edd  mov     [rbx+18h], rax
0x180006ee1  test    rax, rax
0x180006ee4  jz      short loc_180006F01
0x180006ee6  mov     dword ptr [rbx+20h], 5
0x180006eed  lea     rcx, [rax+190h]
0x180006ef4  jmp     short loc_180006EFC
0x180006ef6  mov     [rax], bp
0x180006ef9  add     rax, rbp
0x180006efc  cmp     rax, rcx
0x180006eff  jnz     short loc_180006EF6
0x180006f01  mov     rdi, [rbx+18h]
0x180006f05  test    rdi, rdi
0x180006f08  jz      loc_18000712A
0x180006f0e  test    esi, esi
0x180006f10  jz      short loc_180006F48
0x180006f12  movzx   eax, word ptr [rbx+20h]
0x180006f16  mov     rcx, rdi
0x180006f19  lea     rdx, [rax+rax*4]
0x180006f1d  shl     rdx, 4
0x180006f21  add     rdx, rdi
0x180006f24  cmp     rdi, rdx
0x180006f27  jz      short loc_180006F48
0x180006f29  mov     r8d, [rbx+10h]
0x180006f2d  cmp     [rcx+4], r8d
0x180006f31  jbe     short loc_180006F40
0x180006f33  mov     eax, [r15+8]
0x180006f37  cmp     [rcx+8], eax
0x180006f3a  jz      loc_18000712A
0x180006f40  add     rcx, rbp
0x180006f43  cmp     rcx, rdx
0x180006f46  jnz     short loc_180006F2D
0x180006f48  movzx   eax, word ptr [rbx+22h]
0x180006f4c  mov     r8d, 1
0x180006f52  movzx   ecx, word ptr [rbx+20h]
0x180006f56  add     eax, r8d
0x180006f59  xor     edx, edx
0x180006f5b  div     ecx
0x180006f5d  mov     ecx, r8d
0x180006f60  movzx   eax, dx
0x180006f63  mov     [rbx+22h], dx
0x180006f67  lea     rsi, [rax+rax*4]
0x180006f6b  mov     rax, [rbx+8]
0x180006f6f  shl     rsi, 4
0x180006f73  lock xadd [rax], ecx
0x180006f77  add     ecx, r8d
0x180006f7a  lea     r13, [rsi+rdi]
0x180006f7e  mov     [rsi+rdi+4], ecx
0x180006f82  lea     rbx, [rdi+20h]
0x180006f86  mov     eax, [r15+8]
0x180006f8a  add     rbx, rsi
0x180006f8d  mov     [rsi+rdi+8], eax
0x180006f91  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006f95  mov     [r13+10h], r12
0x180006f99  movzx   eax, word ptr [r15+40h]
0x180006f9e  mov     [rsi+rdi+18h], ax
0x180006fa3  mov     al, [r15]
0x180006fa6  mov     [rsi+rdi+1Ah], al
0x180006faa  mov     [rbx], r12
0x180006fad  mov     rax, [r15+88h]
0x180006fb4  mov     [rsi+rdi+28h], rax
0x180006fb9  mov     rax, [r15+90h]
0x180006fc0  mov     [rsi+rdi+30h], rax
0x180006fc5  mov     [rsi+rdi+38h], r12
0x180006fca  mov     rcx, [r15+38h]
0x180006fce  test    rcx, rcx
0x180006fd1  jnz     short loc_180006FD8
0x180006fd3  mov     edx, r8d
0x180006fd6  jmp     short loc_180006FE8
0x180006fd8  mov     rax, r14
0x180006fdb  inc     rax
0x180006fde  cmp     [rcx+rax], r12b
0x180006fe2  jnz     short loc_180006FDB
0x180006fe4  lea     rdx, [rax+1]
0x180006fe8  mov     rcx, [r15+80h]
0x180006fef  test    rcx, rcx
0x180006ff2  jz      short loc_180007004
0x180006ff4  mov     rax, r14
0x180006ff7  inc     rax
0x180006ffa  cmp     [rcx+rax], r12b
0x180006ffe  jnz     short loc_180006FF7
0x180007000  lea     r8, [rax+1]; unsigned __int64
0x180007004  mov     rcx, [r15+18h]
0x180007008  test    rcx, rcx
0x18000700b  jnz     short loc_180007012
0x18000700d  lea     eax, [rcx+2]
0x180007010  jmp     short loc_180007027
0x180007012  mov     rax, r14
0x180007015  inc     rax
0x180007018  cmp     [rcx+rax*2], r12w
0x18000701d  jnz     short loc_180007015
0x18000701f  lea     rax, ds:2[rax*2]
0x180007027  lea     rbp, [r8+rax]
0x18000702b  add     rbp, rdx
0x18000702e  cmp     [rsi+rdi+40h], r12
0x180007033  jz      short loc_18000703C
0x180007035  cmp     [rsi+rdi+48h], rbp
0x18000703a  jnb     short loc_18000708A
0x18000703c  mov     rdx, rbp; dwBytes
0x18000703f  mov     ecx, 8; dwFlags
0x180007044  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007049  mov     r12, rax
0x18000704c  test    rax, rax
0x18000704f  jz      short loc_180007087
0x180007051  mov     rbx, [rsi+rdi+40h]
0x180007056  call    cs:__imp_GetProcessHeap
0x18000705d  nop     dword ptr [rax+rax+00h]
0x180007062  mov     r8, rbx; lpMem
0x180007065  xor     edx, edx; dwFlags
0x180007067  mov     rcx, rax; hHeap
0x18000706a  call    cs:__imp_HeapFree
0x180007071  nop     dword ptr [rax+rax+00h]
0x180007076  lea     rbx, [rdi+20h]
0x18000707a  mov     [rsi+rdi+40h], r12
0x18000707f  add     rbx, rsi
0x180007082  mov     [rsi+rdi+48h], rbp
0x180007087  xor     r12d, r12d
0x18000708a  mov     rcx, [rsi+rdi+40h]
0x18000708f  test    rcx, rcx
0x180007092  jz      loc_18000712A
0x180007098  mov     rbp, [rsi+rdi+48h]
0x18000709d  lea     r9, [r13+10h]
0x1800070a1  mov     r8, [r15+38h]
0x1800070a5  add     rbp, rcx
0x1800070a8  mov     rdx, rbp
0x1800070ab  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800070b0  mov     r8, [r15+80h]
0x1800070b7  mov     r9, rbx
0x1800070ba  mov     rdx, rbp
0x1800070bd  mov     rcx, rax
0x1800070c0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800070c5  mov     rbx, rax
0x1800070c8  cmp     rax, rbp
0x1800070cb  jz      short loc_180007115
0x1800070cd  mov     r8, [r15+18h]; Source
0x1800070d1  test    r8, r8
0x1800070d4  jz      short loc_180007115
0x1800070d6  cmp     [r8], r12w
0x1800070da  jz      short loc_180007115
0x1800070dc  inc     r14
0x1800070df  cmp     [r8+r14*2], r12w
0x1800070e4  jnz     short loc_1800070DC
0x1800070e6  mov     rdx, rbp
0x1800070e9  lea     r14, ds:2[r14*2]
0x1800070f1  sub     rdx, rbx; DestinationSize
0x1800070f4  cmp     rdx, r14
0x1800070f7  jb      short loc_180007115
0x1800070f9  mov     r9, r14; SourceSize
0x1800070fc  mov     rcx, rbx; Destination
0x1800070ff  call    cs:__imp_memcpy_s
0x180007106  nop     dword ptr [rax+rax+00h]
0x18000710b  mov     [rsi+rdi+38h], rbx
0x180007110  add     rbx, r14
0x180007113  jmp     short loc_18000711A
0x180007115  mov     [rsi+rdi+38h], r12
0x18000711a  sub     rbp, rbx
0x18000711d  xor     edx, edx; Val
0x18000711f  mov     r8, rbp; Size
0x180007122  mov     rcx, rbx; void *
0x180007125  call    memset_0
0x18000712a  add     rsp, 28h
0x18000712e  pop     r15
0x180007130  pop     r14
0x180007132  pop     r13
0x180007134  pop     r12
0x180007136  pop     rdi
0x180007137  pop     rsi
0x180007138  pop     rbp
0x180007139  pop     rbx
0x18000713a  retn
```
