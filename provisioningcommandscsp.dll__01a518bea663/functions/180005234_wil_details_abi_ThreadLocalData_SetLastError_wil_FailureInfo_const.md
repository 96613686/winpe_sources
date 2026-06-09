# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005234`
- end: `0x1800054b9`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800038e0`

## callees

- `0x180002bec`
- `0x180004898`
- `0x180005234`
- `0x18000c5ce`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005483`
- `msvcrt!memcpy_s` at `0x180005483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053e6`

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
  char *v27; // rcx
  char *v28; // rbp
  char *v29; // rax
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
      v27 = *(char **)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = &v27[*(_QWORD *)(v12 + v7 + 72)];
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_BYTE **)a2 + 7), (_QWORD *)(v12 + v7 + 16));
        v30 = wil::details::WriteResultString<char const *>(v29, v28, *((_BYTE **)a2 + 16), v13);
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
0x180005234  push    rbx
0x180005236  push    rbp
0x180005237  push    rsi
0x180005238  push    rdi
0x180005239  push    r12
0x18000523b  push    r13
0x18000523d  push    r14
0x18000523f  push    r15
0x180005241  sub     rsp, 28h
0x180005245  mov     esi, [rcx+10h]
0x180005248  xor     r12d, r12d
0x18000524b  mov     r15, rdx
0x18000524e  mov     rbx, rcx
0x180005251  mov     ebp, 50h ; 'P'
0x180005256  cmp     [rcx+18h], r12
0x18000525a  jnz     short loc_180005291
0x18000525c  test    esi, esi
0x18000525e  jz      short loc_180005291
0x180005260  mov     edx, 190h; dwBytes
0x180005265  lea     ecx, [rbp-48h]; dwFlags
0x180005268  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000526d  mov     [rbx+18h], rax
0x180005271  test    rax, rax
0x180005274  jz      short loc_180005291
0x180005276  mov     dword ptr [rbx+20h], 5
0x18000527d  lea     rcx, [rax+190h]
0x180005284  jmp     short loc_18000528C
0x180005286  mov     [rax], bp
0x180005289  add     rax, rbp
0x18000528c  cmp     rax, rcx
0x18000528f  jnz     short loc_180005286
0x180005291  mov     rdi, [rbx+18h]
0x180005295  test    rdi, rdi
0x180005298  jz      loc_1800054A8
0x18000529e  test    esi, esi
0x1800052a0  jz      short loc_1800052D8
0x1800052a2  movzx   eax, word ptr [rbx+20h]
0x1800052a6  mov     rcx, rdi
0x1800052a9  lea     rdx, [rax+rax*4]
0x1800052ad  shl     rdx, 4
0x1800052b1  add     rdx, rdi
0x1800052b4  cmp     rdi, rdx
0x1800052b7  jz      short loc_1800052D8
0x1800052b9  mov     r8d, [rbx+10h]
0x1800052bd  cmp     [rcx+4], r8d
0x1800052c1  jbe     short loc_1800052D0
0x1800052c3  mov     eax, [r15+8]
0x1800052c7  cmp     [rcx+8], eax
0x1800052ca  jz      loc_1800054A8
0x1800052d0  add     rcx, rbp
0x1800052d3  cmp     rcx, rdx
0x1800052d6  jnz     short loc_1800052BD
0x1800052d8  movzx   eax, word ptr [rbx+22h]
0x1800052dc  mov     r8d, 1
0x1800052e2  movzx   ecx, word ptr [rbx+20h]
0x1800052e6  add     eax, r8d
0x1800052e9  xor     edx, edx
0x1800052eb  div     ecx
0x1800052ed  mov     ecx, r8d
0x1800052f0  movzx   eax, dx
0x1800052f3  mov     [rbx+22h], dx
0x1800052f7  lea     rsi, [rax+rax*4]
0x1800052fb  mov     rax, [rbx+8]
0x1800052ff  shl     rsi, 4
0x180005303  lock xadd [rax], ecx
0x180005307  add     ecx, r8d
0x18000530a  lea     r13, [rsi+rdi]
0x18000530e  mov     [rsi+rdi+4], ecx
0x180005312  lea     rbx, [rdi+20h]
0x180005316  mov     eax, [r15+8]
0x18000531a  add     rbx, rsi
0x18000531d  mov     [rsi+rdi+8], eax
0x180005321  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005325  mov     [r13+10h], r12
0x180005329  movzx   eax, word ptr [r15+40h]
0x18000532e  mov     [rsi+rdi+18h], ax
0x180005333  mov     al, [r15]
0x180005336  mov     [rsi+rdi+1Ah], al
0x18000533a  mov     [rbx], r12
0x18000533d  mov     rax, [r15+88h]
0x180005344  mov     [rsi+rdi+28h], rax
0x180005349  mov     rax, [r15+90h]
0x180005350  mov     [rsi+rdi+30h], rax
0x180005355  mov     [rsi+rdi+38h], r12
0x18000535a  mov     rcx, [r15+38h]
0x18000535e  test    rcx, rcx
0x180005361  jnz     short loc_180005368
0x180005363  mov     edx, r8d
0x180005366  jmp     short loc_180005378
0x180005368  mov     rax, r14
0x18000536b  inc     rax
0x18000536e  cmp     [rcx+rax], r12b
0x180005372  jnz     short loc_18000536B
0x180005374  lea     rdx, [rax+1]
0x180005378  mov     rcx, [r15+80h]
0x18000537f  test    rcx, rcx
0x180005382  jz      short loc_180005394
0x180005384  mov     rax, r14
0x180005387  inc     rax
0x18000538a  cmp     [rcx+rax], r12b
0x18000538e  jnz     short loc_180005387
0x180005390  lea     r8, [rax+1]; unsigned __int64
0x180005394  mov     rcx, [r15+18h]
0x180005398  test    rcx, rcx
0x18000539b  jnz     short loc_1800053A2
0x18000539d  lea     eax, [rcx+2]
0x1800053a0  jmp     short loc_1800053B7
0x1800053a2  mov     rax, r14
0x1800053a5  inc     rax
0x1800053a8  cmp     [rcx+rax*2], r12w
0x1800053ad  jnz     short loc_1800053A5
0x1800053af  lea     rax, ds:2[rax*2]
0x1800053b7  lea     rbp, [r8+rax]
0x1800053bb  add     rbp, rdx
0x1800053be  cmp     [rsi+rdi+40h], r12
0x1800053c3  jz      short loc_1800053CC
0x1800053c5  cmp     [rsi+rdi+48h], rbp
0x1800053ca  jnb     short loc_18000540E
0x1800053cc  mov     rdx, rbp; dwBytes
0x1800053cf  mov     ecx, 8; dwFlags
0x1800053d4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053d9  mov     r12, rax
0x1800053dc  test    rax, rax
0x1800053df  jz      short loc_18000540B
0x1800053e1  mov     rbx, [rsi+rdi+40h]
0x1800053e6  call    cs:__imp_GetProcessHeap
0x1800053ec  mov     r8, rbx; lpMem
0x1800053ef  xor     edx, edx; dwFlags
0x1800053f1  mov     rcx, rax; hHeap
0x1800053f4  call    cs:__imp_HeapFree
0x1800053fa  lea     rbx, [rdi+20h]
0x1800053fe  mov     [rsi+rdi+40h], r12
0x180005403  add     rbx, rsi
0x180005406  mov     [rsi+rdi+48h], rbp
0x18000540b  xor     r12d, r12d
0x18000540e  mov     rcx, [rsi+rdi+40h]
0x180005413  test    rcx, rcx
0x180005416  jz      loc_1800054A8
0x18000541c  mov     rbp, [rsi+rdi+48h]
0x180005421  lea     r9, [r13+10h]
0x180005425  mov     r8, [r15+38h]
0x180005429  add     rbp, rcx
0x18000542c  mov     rdx, rbp
0x18000542f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005434  mov     r8, [r15+80h]
0x18000543b  mov     r9, rbx
0x18000543e  mov     rdx, rbp
0x180005441  mov     rcx, rax
0x180005444  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005449  mov     rbx, rax
0x18000544c  cmp     rax, rbp
0x18000544f  jz      short loc_180005493
0x180005451  mov     r8, [r15+18h]; Source
0x180005455  test    r8, r8
0x180005458  jz      short loc_180005493
0x18000545a  cmp     [r8], r12w
0x18000545e  jz      short loc_180005493
0x180005460  inc     r14
0x180005463  cmp     [r8+r14*2], r12w
0x180005468  jnz     short loc_180005460
0x18000546a  mov     rdx, rbp
0x18000546d  lea     r14, ds:2[r14*2]
0x180005475  sub     rdx, rbx; DestinationSize
0x180005478  cmp     rdx, r14
0x18000547b  jb      short loc_180005493
0x18000547d  mov     r9, r14; SourceSize
0x180005480  mov     rcx, rbx; Destination
0x180005483  call    cs:__imp_memcpy_s
0x180005489  mov     [rsi+rdi+38h], rbx
0x18000548e  add     rbx, r14
0x180005491  jmp     short loc_180005498
0x180005493  mov     [rsi+rdi+38h], r12
0x180005498  sub     rbp, rbx
0x18000549b  xor     edx, edx; Val
0x18000549d  mov     r8, rbp; Size
0x1800054a0  mov     rcx, rbx; void *
0x1800054a3  call    memset_0
0x1800054a8  add     rsp, 28h
0x1800054ac  pop     r15
0x1800054ae  pop     r14
0x1800054b0  pop     r13
0x1800054b2  pop     r12
0x1800054b4  pop     rdi
0x1800054b5  pop     rsi
0x1800054b6  pop     rbp
0x1800054b7  pop     rbx
0x1800054b8  retn
```
