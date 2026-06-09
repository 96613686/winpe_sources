# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140007500`
- end: `0x140007791`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004990`

## callees

- `0x140002b2c`
- `0x1400037c4`
- `0x1400067d4`
- `0x140007500`
- `0x14000942c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400076b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400076b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400076c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400076c6`

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
0x140007500  push    rbx
0x140007502  push    rbp
0x140007503  push    rsi
0x140007504  push    rdi
0x140007505  push    r12
0x140007507  push    r13
0x140007509  push    r14
0x14000750b  push    r15
0x14000750d  sub     rsp, 28h
0x140007511  mov     esi, [rcx+10h]
0x140007514  xor     r12d, r12d
0x140007517  mov     r15, rdx
0x14000751a  mov     rbx, rcx
0x14000751d  mov     ebp, 50h ; 'P'
0x140007522  cmp     [rcx+18h], r12
0x140007526  jnz     short loc_14000755D
0x140007528  test    esi, esi
0x14000752a  jz      short loc_14000755D
0x14000752c  mov     edx, 190h; dwBytes
0x140007531  lea     ecx, [rbp-48h]; dwFlags
0x140007534  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007539  mov     [rbx+18h], rax
0x14000753d  test    rax, rax
0x140007540  jz      short loc_14000755D
0x140007542  mov     dword ptr [rbx+20h], 5
0x140007549  lea     rcx, [rax+190h]
0x140007550  jmp     short loc_140007558
0x140007552  mov     [rax], bp
0x140007555  add     rax, rbp
0x140007558  cmp     rax, rcx
0x14000755b  jnz     short loc_140007552
0x14000755d  mov     rdi, [rbx+18h]
0x140007561  test    rdi, rdi
0x140007564  jz      loc_14000777F
0x14000756a  test    esi, esi
0x14000756c  jz      short loc_1400075A4
0x14000756e  movzx   eax, word ptr [rbx+20h]
0x140007572  mov     rcx, rdi
0x140007575  lea     rdx, [rax+rax*4]
0x140007579  shl     rdx, 4
0x14000757d  add     rdx, rdi
0x140007580  cmp     rdi, rdx
0x140007583  jz      short loc_1400075A4
0x140007585  mov     r8d, [rbx+10h]
0x140007589  cmp     [rcx+4], r8d
0x14000758d  jbe     short loc_14000759C
0x14000758f  mov     eax, [r15+8]
0x140007593  cmp     [rcx+8], eax
0x140007596  jz      loc_14000777F
0x14000759c  add     rcx, rbp
0x14000759f  cmp     rcx, rdx
0x1400075a2  jnz     short loc_140007589
0x1400075a4  movzx   eax, word ptr [rbx+22h]
0x1400075a8  mov     r8d, 1
0x1400075ae  movzx   ecx, word ptr [rbx+20h]
0x1400075b2  add     eax, r8d
0x1400075b5  xor     edx, edx
0x1400075b7  div     ecx
0x1400075b9  mov     ecx, r8d
0x1400075bc  movzx   eax, dx
0x1400075bf  mov     [rbx+22h], dx
0x1400075c3  lea     rsi, [rax+rax*4]
0x1400075c7  mov     rax, [rbx+8]
0x1400075cb  shl     rsi, 4
0x1400075cf  lock xadd [rax], ecx
0x1400075d3  add     ecx, r8d
0x1400075d6  lea     r13, [rsi+rdi]
0x1400075da  mov     [rsi+rdi+4], ecx
0x1400075de  lea     rbx, [rdi+20h]
0x1400075e2  mov     eax, [r15+8]
0x1400075e6  add     rbx, rsi
0x1400075e9  mov     [rsi+rdi+8], eax
0x1400075ed  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400075f1  mov     [r13+10h], r12
0x1400075f5  movzx   eax, word ptr [r15+40h]
0x1400075fa  mov     [rsi+rdi+18h], ax
0x1400075ff  mov     al, [r15]
0x140007602  mov     [rsi+rdi+1Ah], al
0x140007606  mov     [rbx], r12
0x140007609  mov     rax, [r15+88h]
0x140007610  mov     [rsi+rdi+28h], rax
0x140007615  mov     rax, [r15+90h]
0x14000761c  mov     [rsi+rdi+30h], rax
0x140007621  mov     [rsi+rdi+38h], r12
0x140007626  mov     rcx, [r15+38h]
0x14000762a  test    rcx, rcx
0x14000762d  jnz     short loc_140007634
0x14000762f  mov     edx, r8d
0x140007632  jmp     short loc_140007644
0x140007634  mov     rax, r14
0x140007637  inc     rax
0x14000763a  cmp     [rcx+rax], r12b
0x14000763e  jnz     short loc_140007637
0x140007640  lea     rdx, [rax+1]
0x140007644  mov     rcx, [r15+80h]
0x14000764b  test    rcx, rcx
0x14000764e  jz      short loc_140007660
0x140007650  mov     rax, r14
0x140007653  inc     rax
0x140007656  cmp     [rcx+rax], r12b
0x14000765a  jnz     short loc_140007653
0x14000765c  lea     r8, [rax+1]; unsigned __int64
0x140007660  mov     rcx, [r15+18h]
0x140007664  test    rcx, rcx
0x140007667  jnz     short loc_14000766E
0x140007669  lea     eax, [rcx+2]
0x14000766c  jmp     short loc_140007683
0x14000766e  mov     rax, r14
0x140007671  inc     rax
0x140007674  cmp     [rcx+rax*2], r12w
0x140007679  jnz     short loc_140007671
0x14000767b  lea     rax, ds:2[rax*2]
0x140007683  lea     rbp, [r8+rax]
0x140007687  add     rbp, rdx
0x14000768a  cmp     [rsi+rdi+40h], r12
0x14000768f  jz      short loc_140007698
0x140007691  cmp     [rsi+rdi+48h], rbp
0x140007696  jnb     short loc_1400076E6
0x140007698  mov     rdx, rbp; dwBytes
0x14000769b  mov     ecx, 8; dwFlags
0x1400076a0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400076a5  mov     r12, rax
0x1400076a8  test    rax, rax
0x1400076ab  jz      short loc_1400076E3
0x1400076ad  mov     rbx, [rsi+rdi+40h]
0x1400076b2  call    cs:__imp_GetProcessHeap
0x1400076b9  nop     dword ptr [rax+rax+00h]
0x1400076be  mov     r8, rbx; lpMem
0x1400076c1  xor     edx, edx; dwFlags
0x1400076c3  mov     rcx, rax; hHeap
0x1400076c6  call    cs:__imp_HeapFree
0x1400076cd  nop     dword ptr [rax+rax+00h]
0x1400076d2  lea     rbx, [rdi+20h]
0x1400076d6  mov     [rsi+rdi+40h], r12
0x1400076db  add     rbx, rsi
0x1400076de  mov     [rsi+rdi+48h], rbp
0x1400076e3  xor     r12d, r12d
0x1400076e6  mov     rcx, [rsi+rdi+40h]
0x1400076eb  test    rcx, rcx
0x1400076ee  jz      loc_14000777F
0x1400076f4  mov     rbp, [rsi+rdi+48h]
0x1400076f9  lea     r9, [r13+10h]
0x1400076fd  mov     r8, [r15+38h]
0x140007701  add     rbp, rcx
0x140007704  mov     rdx, rbp
0x140007707  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000770c  mov     r8, [r15+80h]
0x140007713  mov     r9, rbx
0x140007716  mov     rdx, rbp
0x140007719  mov     rcx, rax
0x14000771c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140007721  mov     rbx, rax
0x140007724  cmp     rax, rbp
0x140007727  jz      short loc_14000776A
0x140007729  mov     r8, [r15+18h]; Source
0x14000772d  test    r8, r8
0x140007730  jz      short loc_14000776A
0x140007732  cmp     [r8], r12w
0x140007736  jz      short loc_14000776A
0x140007738  inc     r14
0x14000773b  cmp     [r8+r14*2], r12w
0x140007740  jnz     short loc_140007738
0x140007742  mov     rdx, rbp
0x140007745  lea     r14, ds:2[r14*2]
0x14000774d  sub     rdx, rbx; DestinationSize
0x140007750  cmp     rdx, r14
0x140007753  jb      short loc_14000776A
0x140007755  mov     r9, r14; SourceSize
0x140007758  mov     rcx, rbx; Destination
0x14000775b  call    memcpy_s
0x140007760  mov     [rsi+rdi+38h], rbx
0x140007765  add     rbx, r14
0x140007768  jmp     short loc_14000776F
0x14000776a  mov     [rsi+rdi+38h], r12
0x14000776f  sub     rbp, rbx
0x140007772  xor     edx, edx; Val
0x140007774  mov     r8, rbp; Size
0x140007777  mov     rcx, rbx; void *
0x14000777a  call    memset_0
0x14000777f  add     rsp, 28h
0x140007783  pop     r15
0x140007785  pop     r14
0x140007787  pop     r13
0x140007789  pop     r12
0x14000778b  pop     rdi
0x14000778c  pop     rsi
0x14000778d  pop     rbp
0x14000778e  pop     rbx
0x14000778f  retn
```
