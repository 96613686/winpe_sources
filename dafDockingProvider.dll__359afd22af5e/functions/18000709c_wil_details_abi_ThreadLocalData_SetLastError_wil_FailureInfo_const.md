# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000709c`
- end: `0x180007321`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x180002d3c`
- `0x1800057d8`
- `0x18000709c`
- `0x18001ca3e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800072eb`
- `msvcrt!memcpy_s` at `0x1800072eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000725c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000725c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000724e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000724e`

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
0x18000709c  push    rbx
0x18000709e  push    rbp
0x18000709f  push    rsi
0x1800070a0  push    rdi
0x1800070a1  push    r12
0x1800070a3  push    r13
0x1800070a5  push    r14
0x1800070a7  push    r15
0x1800070a9  sub     rsp, 28h
0x1800070ad  mov     esi, [rcx+10h]
0x1800070b0  xor     r12d, r12d
0x1800070b3  mov     r15, rdx
0x1800070b6  mov     rbx, rcx
0x1800070b9  mov     ebp, 50h ; 'P'
0x1800070be  cmp     [rcx+18h], r12
0x1800070c2  jnz     short loc_1800070F9
0x1800070c4  test    esi, esi
0x1800070c6  jz      short loc_1800070F9
0x1800070c8  mov     edx, 190h; dwBytes
0x1800070cd  lea     ecx, [rbp-48h]; dwFlags
0x1800070d0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800070d5  mov     [rbx+18h], rax
0x1800070d9  test    rax, rax
0x1800070dc  jz      short loc_1800070F9
0x1800070de  mov     dword ptr [rbx+20h], 5
0x1800070e5  lea     rcx, [rax+190h]
0x1800070ec  jmp     short loc_1800070F4
0x1800070ee  mov     [rax], bp
0x1800070f1  add     rax, rbp
0x1800070f4  cmp     rax, rcx
0x1800070f7  jnz     short loc_1800070EE
0x1800070f9  mov     rdi, [rbx+18h]
0x1800070fd  test    rdi, rdi
0x180007100  jz      loc_180007310
0x180007106  test    esi, esi
0x180007108  jz      short loc_180007140
0x18000710a  movzx   eax, word ptr [rbx+20h]
0x18000710e  mov     rcx, rdi
0x180007111  lea     rdx, [rax+rax*4]
0x180007115  shl     rdx, 4
0x180007119  add     rdx, rdi
0x18000711c  cmp     rdi, rdx
0x18000711f  jz      short loc_180007140
0x180007121  mov     r8d, [rbx+10h]
0x180007125  cmp     [rcx+4], r8d
0x180007129  jbe     short loc_180007138
0x18000712b  mov     eax, [r15+8]
0x18000712f  cmp     [rcx+8], eax
0x180007132  jz      loc_180007310
0x180007138  add     rcx, rbp
0x18000713b  cmp     rcx, rdx
0x18000713e  jnz     short loc_180007125
0x180007140  movzx   eax, word ptr [rbx+22h]
0x180007144  mov     r8d, 1
0x18000714a  movzx   ecx, word ptr [rbx+20h]
0x18000714e  add     eax, r8d
0x180007151  xor     edx, edx
0x180007153  div     ecx
0x180007155  mov     ecx, r8d
0x180007158  movzx   eax, dx
0x18000715b  mov     [rbx+22h], dx
0x18000715f  lea     rsi, [rax+rax*4]
0x180007163  mov     rax, [rbx+8]
0x180007167  shl     rsi, 4
0x18000716b  lock xadd [rax], ecx
0x18000716f  add     ecx, r8d
0x180007172  lea     r13, [rsi+rdi]
0x180007176  mov     [rsi+rdi+4], ecx
0x18000717a  lea     rbx, [rdi+20h]
0x18000717e  mov     eax, [r15+8]
0x180007182  add     rbx, rsi
0x180007185  mov     [rsi+rdi+8], eax
0x180007189  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000718d  mov     [r13+10h], r12
0x180007191  movzx   eax, word ptr [r15+40h]
0x180007196  mov     [rsi+rdi+18h], ax
0x18000719b  mov     al, [r15]
0x18000719e  mov     [rsi+rdi+1Ah], al
0x1800071a2  mov     [rbx], r12
0x1800071a5  mov     rax, [r15+88h]
0x1800071ac  mov     [rsi+rdi+28h], rax
0x1800071b1  mov     rax, [r15+90h]
0x1800071b8  mov     [rsi+rdi+30h], rax
0x1800071bd  mov     [rsi+rdi+38h], r12
0x1800071c2  mov     rcx, [r15+38h]
0x1800071c6  test    rcx, rcx
0x1800071c9  jnz     short loc_1800071D0
0x1800071cb  mov     edx, r8d
0x1800071ce  jmp     short loc_1800071E0
0x1800071d0  mov     rax, r14
0x1800071d3  inc     rax
0x1800071d6  cmp     [rcx+rax], r12b
0x1800071da  jnz     short loc_1800071D3
0x1800071dc  lea     rdx, [rax+1]
0x1800071e0  mov     rcx, [r15+80h]
0x1800071e7  test    rcx, rcx
0x1800071ea  jz      short loc_1800071FC
0x1800071ec  mov     rax, r14
0x1800071ef  inc     rax
0x1800071f2  cmp     [rcx+rax], r12b
0x1800071f6  jnz     short loc_1800071EF
0x1800071f8  lea     r8, [rax+1]; unsigned __int64
0x1800071fc  mov     rcx, [r15+18h]
0x180007200  test    rcx, rcx
0x180007203  jnz     short loc_18000720A
0x180007205  lea     eax, [rcx+2]
0x180007208  jmp     short loc_18000721F
0x18000720a  mov     rax, r14
0x18000720d  inc     rax
0x180007210  cmp     [rcx+rax*2], r12w
0x180007215  jnz     short loc_18000720D
0x180007217  lea     rax, ds:2[rax*2]
0x18000721f  lea     rbp, [r8+rax]
0x180007223  add     rbp, rdx
0x180007226  cmp     [rsi+rdi+40h], r12
0x18000722b  jz      short loc_180007234
0x18000722d  cmp     [rsi+rdi+48h], rbp
0x180007232  jnb     short loc_180007276
0x180007234  mov     rdx, rbp; dwBytes
0x180007237  mov     ecx, 8; dwFlags
0x18000723c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007241  mov     r12, rax
0x180007244  test    rax, rax
0x180007247  jz      short loc_180007273
0x180007249  mov     rbx, [rsi+rdi+40h]
0x18000724e  call    cs:__imp_GetProcessHeap
0x180007254  mov     r8, rbx; lpMem
0x180007257  xor     edx, edx; dwFlags
0x180007259  mov     rcx, rax; hHeap
0x18000725c  call    cs:__imp_HeapFree
0x180007262  lea     rbx, [rdi+20h]
0x180007266  mov     [rsi+rdi+40h], r12
0x18000726b  add     rbx, rsi
0x18000726e  mov     [rsi+rdi+48h], rbp
0x180007273  xor     r12d, r12d
0x180007276  mov     rcx, [rsi+rdi+40h]
0x18000727b  test    rcx, rcx
0x18000727e  jz      loc_180007310
0x180007284  mov     rbp, [rsi+rdi+48h]
0x180007289  lea     r9, [r13+10h]
0x18000728d  mov     r8, [r15+38h]
0x180007291  add     rbp, rcx
0x180007294  mov     rdx, rbp
0x180007297  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000729c  mov     r8, [r15+80h]
0x1800072a3  mov     r9, rbx
0x1800072a6  mov     rdx, rbp
0x1800072a9  mov     rcx, rax
0x1800072ac  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800072b1  mov     rbx, rax
0x1800072b4  cmp     rax, rbp
0x1800072b7  jz      short loc_1800072FB
0x1800072b9  mov     r8, [r15+18h]; Source
0x1800072bd  test    r8, r8
0x1800072c0  jz      short loc_1800072FB
0x1800072c2  cmp     [r8], r12w
0x1800072c6  jz      short loc_1800072FB
0x1800072c8  inc     r14
0x1800072cb  cmp     [r8+r14*2], r12w
0x1800072d0  jnz     short loc_1800072C8
0x1800072d2  mov     rdx, rbp
0x1800072d5  lea     r14, ds:2[r14*2]
0x1800072dd  sub     rdx, rbx; DestinationSize
0x1800072e0  cmp     rdx, r14
0x1800072e3  jb      short loc_1800072FB
0x1800072e5  mov     r9, r14; SourceSize
0x1800072e8  mov     rcx, rbx; Destination
0x1800072eb  call    cs:__imp_memcpy_s
0x1800072f1  mov     [rsi+rdi+38h], rbx
0x1800072f6  add     rbx, r14
0x1800072f9  jmp     short loc_180007300
0x1800072fb  mov     [rsi+rdi+38h], r12
0x180007300  sub     rbp, rbx
0x180007303  xor     edx, edx; Val
0x180007305  mov     r8, rbp; Size
0x180007308  mov     rcx, rbx; void *
0x18000730b  call    memset_0
0x180007310  add     rsp, 28h
0x180007314  pop     r15
0x180007316  pop     r14
0x180007318  pop     r13
0x18000731a  pop     r12
0x18000731c  pop     rdi
0x18000731d  pop     rsi
0x18000731e  pop     rbp
0x18000731f  pop     rbx
0x180007320  retn
```
