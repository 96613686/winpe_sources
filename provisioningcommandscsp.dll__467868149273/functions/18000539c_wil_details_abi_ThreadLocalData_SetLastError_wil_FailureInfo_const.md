# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000539c`
- end: `0x180005634`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003670`

## callees

- `0x180002c2c`
- `0x180004924`
- `0x18000539c`
- `0x18000cc8e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800055f7`
- `msvcrt!memcpy_s` at `0x1800055f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000554e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000554e`

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
0x18000539c  push    rbx
0x18000539e  push    rbp
0x18000539f  push    rsi
0x1800053a0  push    rdi
0x1800053a1  push    r12
0x1800053a3  push    r13
0x1800053a5  push    r14
0x1800053a7  push    r15
0x1800053a9  sub     rsp, 28h
0x1800053ad  mov     esi, [rcx+10h]
0x1800053b0  xor     r12d, r12d
0x1800053b3  mov     r15, rdx
0x1800053b6  mov     rbx, rcx
0x1800053b9  mov     ebp, 50h ; 'P'
0x1800053be  cmp     [rcx+18h], r12
0x1800053c2  jnz     short loc_1800053F9
0x1800053c4  test    esi, esi
0x1800053c6  jz      short loc_1800053F9
0x1800053c8  mov     edx, 190h; dwBytes
0x1800053cd  lea     ecx, [rbp-48h]; dwFlags
0x1800053d0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053d5  mov     [rbx+18h], rax
0x1800053d9  test    rax, rax
0x1800053dc  jz      short loc_1800053F9
0x1800053de  mov     dword ptr [rbx+20h], 5
0x1800053e5  lea     rcx, [rax+190h]
0x1800053ec  jmp     short loc_1800053F4
0x1800053ee  mov     [rax], bp
0x1800053f1  add     rax, rbp
0x1800053f4  cmp     rax, rcx
0x1800053f7  jnz     short loc_1800053EE
0x1800053f9  mov     rdi, [rbx+18h]
0x1800053fd  test    rdi, rdi
0x180005400  jz      loc_180005622
0x180005406  test    esi, esi
0x180005408  jz      short loc_180005440
0x18000540a  movzx   eax, word ptr [rbx+20h]
0x18000540e  mov     rcx, rdi
0x180005411  lea     rdx, [rax+rax*4]
0x180005415  shl     rdx, 4
0x180005419  add     rdx, rdi
0x18000541c  cmp     rdi, rdx
0x18000541f  jz      short loc_180005440
0x180005421  mov     r8d, [rbx+10h]
0x180005425  cmp     [rcx+4], r8d
0x180005429  jbe     short loc_180005438
0x18000542b  mov     eax, [r15+8]
0x18000542f  cmp     [rcx+8], eax
0x180005432  jz      loc_180005622
0x180005438  add     rcx, rbp
0x18000543b  cmp     rcx, rdx
0x18000543e  jnz     short loc_180005425
0x180005440  movzx   eax, word ptr [rbx+22h]
0x180005444  mov     r8d, 1
0x18000544a  movzx   ecx, word ptr [rbx+20h]
0x18000544e  add     eax, r8d
0x180005451  xor     edx, edx
0x180005453  div     ecx
0x180005455  mov     ecx, r8d
0x180005458  movzx   eax, dx
0x18000545b  mov     [rbx+22h], dx
0x18000545f  lea     rsi, [rax+rax*4]
0x180005463  mov     rax, [rbx+8]
0x180005467  shl     rsi, 4
0x18000546b  lock xadd [rax], ecx
0x18000546f  add     ecx, r8d
0x180005472  lea     r13, [rsi+rdi]
0x180005476  mov     [rsi+rdi+4], ecx
0x18000547a  lea     rbx, [rdi+20h]
0x18000547e  mov     eax, [r15+8]
0x180005482  add     rbx, rsi
0x180005485  mov     [rsi+rdi+8], eax
0x180005489  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000548d  mov     [r13+10h], r12
0x180005491  movzx   eax, word ptr [r15+40h]
0x180005496  mov     [rsi+rdi+18h], ax
0x18000549b  mov     al, [r15]
0x18000549e  mov     [rsi+rdi+1Ah], al
0x1800054a2  mov     [rbx], r12
0x1800054a5  mov     rax, [r15+88h]
0x1800054ac  mov     [rsi+rdi+28h], rax
0x1800054b1  mov     rax, [r15+90h]
0x1800054b8  mov     [rsi+rdi+30h], rax
0x1800054bd  mov     [rsi+rdi+38h], r12
0x1800054c2  mov     rcx, [r15+38h]
0x1800054c6  test    rcx, rcx
0x1800054c9  jnz     short loc_1800054D0
0x1800054cb  mov     edx, r8d
0x1800054ce  jmp     short loc_1800054E0
0x1800054d0  mov     rax, r14
0x1800054d3  inc     rax
0x1800054d6  cmp     [rcx+rax], r12b
0x1800054da  jnz     short loc_1800054D3
0x1800054dc  lea     rdx, [rax+1]
0x1800054e0  mov     rcx, [r15+80h]
0x1800054e7  test    rcx, rcx
0x1800054ea  jz      short loc_1800054FC
0x1800054ec  mov     rax, r14
0x1800054ef  inc     rax
0x1800054f2  cmp     [rcx+rax], r12b
0x1800054f6  jnz     short loc_1800054EF
0x1800054f8  lea     r8, [rax+1]; unsigned __int64
0x1800054fc  mov     rcx, [r15+18h]
0x180005500  test    rcx, rcx
0x180005503  jnz     short loc_18000550A
0x180005505  lea     eax, [rcx+2]
0x180005508  jmp     short loc_18000551F
0x18000550a  mov     rax, r14
0x18000550d  inc     rax
0x180005510  cmp     [rcx+rax*2], r12w
0x180005515  jnz     short loc_18000550D
0x180005517  lea     rax, ds:2[rax*2]
0x18000551f  lea     rbp, [r8+rax]
0x180005523  add     rbp, rdx
0x180005526  cmp     [rsi+rdi+40h], r12
0x18000552b  jz      short loc_180005534
0x18000552d  cmp     [rsi+rdi+48h], rbp
0x180005532  jnb     short loc_180005582
0x180005534  mov     rdx, rbp; dwBytes
0x180005537  mov     ecx, 8; dwFlags
0x18000553c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005541  mov     r12, rax
0x180005544  test    rax, rax
0x180005547  jz      short loc_18000557F
0x180005549  mov     rbx, [rsi+rdi+40h]
0x18000554e  call    cs:__imp_GetProcessHeap
0x180005555  nop     dword ptr [rax+rax+00h]
0x18000555a  mov     r8, rbx; lpMem
0x18000555d  xor     edx, edx; dwFlags
0x18000555f  mov     rcx, rax; hHeap
0x180005562  call    cs:__imp_HeapFree
0x180005569  nop     dword ptr [rax+rax+00h]
0x18000556e  lea     rbx, [rdi+20h]
0x180005572  mov     [rsi+rdi+40h], r12
0x180005577  add     rbx, rsi
0x18000557a  mov     [rsi+rdi+48h], rbp
0x18000557f  xor     r12d, r12d
0x180005582  mov     rcx, [rsi+rdi+40h]
0x180005587  test    rcx, rcx
0x18000558a  jz      loc_180005622
0x180005590  mov     rbp, [rsi+rdi+48h]
0x180005595  lea     r9, [r13+10h]
0x180005599  mov     r8, [r15+38h]
0x18000559d  add     rbp, rcx
0x1800055a0  mov     rdx, rbp
0x1800055a3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800055a8  mov     r8, [r15+80h]
0x1800055af  mov     r9, rbx
0x1800055b2  mov     rdx, rbp
0x1800055b5  mov     rcx, rax
0x1800055b8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800055bd  mov     rbx, rax
0x1800055c0  cmp     rax, rbp
0x1800055c3  jz      short loc_18000560D
0x1800055c5  mov     r8, [r15+18h]; Source
0x1800055c9  test    r8, r8
0x1800055cc  jz      short loc_18000560D
0x1800055ce  cmp     [r8], r12w
0x1800055d2  jz      short loc_18000560D
0x1800055d4  inc     r14
0x1800055d7  cmp     [r8+r14*2], r12w
0x1800055dc  jnz     short loc_1800055D4
0x1800055de  mov     rdx, rbp
0x1800055e1  lea     r14, ds:2[r14*2]
0x1800055e9  sub     rdx, rbx; DestinationSize
0x1800055ec  cmp     rdx, r14
0x1800055ef  jb      short loc_18000560D
0x1800055f1  mov     r9, r14; SourceSize
0x1800055f4  mov     rcx, rbx; Destination
0x1800055f7  call    cs:__imp_memcpy_s
0x1800055fe  nop     dword ptr [rax+rax+00h]
0x180005603  mov     [rsi+rdi+38h], rbx
0x180005608  add     rbx, r14
0x18000560b  jmp     short loc_180005612
0x18000560d  mov     [rsi+rdi+38h], r12
0x180005612  sub     rbp, rbx
0x180005615  xor     edx, edx; Val
0x180005617  mov     r8, rbp; Size
0x18000561a  mov     rcx, rbx; void *
0x18000561d  call    memset_0
0x180005622  add     rsp, 28h
0x180005626  pop     r15
0x180005628  pop     r14
0x18000562a  pop     r13
0x18000562c  pop     r12
0x18000562e  pop     rdi
0x18000562f  pop     rsi
0x180005630  pop     rbp
0x180005631  pop     rbx
0x180005632  retn
```
