# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000a29c`
- end: `0x18000a52d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006ba0`

## callees

- `0x180003cf0`
- `0x180004cdc`
- `0x1800080d8`
- `0x18000a29c`
- `0x18000bd1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a44e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a462`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a462`

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
0x18000a29c  push    rbx
0x18000a29e  push    rbp
0x18000a29f  push    rsi
0x18000a2a0  push    rdi
0x18000a2a1  push    r12
0x18000a2a3  push    r13
0x18000a2a5  push    r14
0x18000a2a7  push    r15
0x18000a2a9  sub     rsp, 28h
0x18000a2ad  mov     esi, [rcx+10h]
0x18000a2b0  xor     r12d, r12d
0x18000a2b3  mov     r15, rdx
0x18000a2b6  mov     rbx, rcx
0x18000a2b9  mov     ebp, 50h ; 'P'
0x18000a2be  cmp     [rcx+18h], r12
0x18000a2c2  jnz     short loc_18000A2F9
0x18000a2c4  test    esi, esi
0x18000a2c6  jz      short loc_18000A2F9
0x18000a2c8  mov     edx, 190h; dwBytes
0x18000a2cd  lea     ecx, [rbp-48h]; dwFlags
0x18000a2d0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a2d5  mov     [rbx+18h], rax
0x18000a2d9  test    rax, rax
0x18000a2dc  jz      short loc_18000A2F9
0x18000a2de  mov     dword ptr [rbx+20h], 5
0x18000a2e5  lea     rcx, [rax+190h]
0x18000a2ec  jmp     short loc_18000A2F4
0x18000a2ee  mov     [rax], bp
0x18000a2f1  add     rax, rbp
0x18000a2f4  cmp     rax, rcx
0x18000a2f7  jnz     short loc_18000A2EE
0x18000a2f9  mov     rdi, [rbx+18h]
0x18000a2fd  test    rdi, rdi
0x18000a300  jz      loc_18000A51B
0x18000a306  test    esi, esi
0x18000a308  jz      short loc_18000A340
0x18000a30a  movzx   eax, word ptr [rbx+20h]
0x18000a30e  mov     rcx, rdi
0x18000a311  lea     rdx, [rax+rax*4]
0x18000a315  shl     rdx, 4
0x18000a319  add     rdx, rdi
0x18000a31c  cmp     rdi, rdx
0x18000a31f  jz      short loc_18000A340
0x18000a321  mov     r8d, [rbx+10h]
0x18000a325  cmp     [rcx+4], r8d
0x18000a329  jbe     short loc_18000A338
0x18000a32b  mov     eax, [r15+8]
0x18000a32f  cmp     [rcx+8], eax
0x18000a332  jz      loc_18000A51B
0x18000a338  add     rcx, rbp
0x18000a33b  cmp     rcx, rdx
0x18000a33e  jnz     short loc_18000A325
0x18000a340  movzx   eax, word ptr [rbx+22h]
0x18000a344  mov     r8d, 1
0x18000a34a  movzx   ecx, word ptr [rbx+20h]
0x18000a34e  add     eax, r8d
0x18000a351  xor     edx, edx
0x18000a353  div     ecx
0x18000a355  mov     ecx, r8d
0x18000a358  movzx   eax, dx
0x18000a35b  mov     [rbx+22h], dx
0x18000a35f  lea     rsi, [rax+rax*4]
0x18000a363  mov     rax, [rbx+8]
0x18000a367  shl     rsi, 4
0x18000a36b  lock xadd [rax], ecx
0x18000a36f  add     ecx, r8d
0x18000a372  lea     r13, [rsi+rdi]
0x18000a376  mov     [rsi+rdi+4], ecx
0x18000a37a  lea     rbx, [rdi+20h]
0x18000a37e  mov     eax, [r15+8]
0x18000a382  add     rbx, rsi
0x18000a385  mov     [rsi+rdi+8], eax
0x18000a389  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a38d  mov     [r13+10h], r12
0x18000a391  movzx   eax, word ptr [r15+40h]
0x18000a396  mov     [rsi+rdi+18h], ax
0x18000a39b  mov     al, [r15]
0x18000a39e  mov     [rsi+rdi+1Ah], al
0x18000a3a2  mov     [rbx], r12
0x18000a3a5  mov     rax, [r15+88h]
0x18000a3ac  mov     [rsi+rdi+28h], rax
0x18000a3b1  mov     rax, [r15+90h]
0x18000a3b8  mov     [rsi+rdi+30h], rax
0x18000a3bd  mov     [rsi+rdi+38h], r12
0x18000a3c2  mov     rcx, [r15+38h]
0x18000a3c6  test    rcx, rcx
0x18000a3c9  jnz     short loc_18000A3D0
0x18000a3cb  mov     edx, r8d
0x18000a3ce  jmp     short loc_18000A3E0
0x18000a3d0  mov     rax, r14
0x18000a3d3  inc     rax
0x18000a3d6  cmp     [rcx+rax], r12b
0x18000a3da  jnz     short loc_18000A3D3
0x18000a3dc  lea     rdx, [rax+1]
0x18000a3e0  mov     rcx, [r15+80h]
0x18000a3e7  test    rcx, rcx
0x18000a3ea  jz      short loc_18000A3FC
0x18000a3ec  mov     rax, r14
0x18000a3ef  inc     rax
0x18000a3f2  cmp     [rcx+rax], r12b
0x18000a3f6  jnz     short loc_18000A3EF
0x18000a3f8  lea     r8, [rax+1]; unsigned __int64
0x18000a3fc  mov     rcx, [r15+18h]
0x18000a400  test    rcx, rcx
0x18000a403  jnz     short loc_18000A40A
0x18000a405  lea     eax, [rcx+2]
0x18000a408  jmp     short loc_18000A41F
0x18000a40a  mov     rax, r14
0x18000a40d  inc     rax
0x18000a410  cmp     [rcx+rax*2], r12w
0x18000a415  jnz     short loc_18000A40D
0x18000a417  lea     rax, ds:2[rax*2]
0x18000a41f  lea     rbp, [r8+rax]
0x18000a423  add     rbp, rdx
0x18000a426  cmp     [rsi+rdi+40h], r12
0x18000a42b  jz      short loc_18000A434
0x18000a42d  cmp     [rsi+rdi+48h], rbp
0x18000a432  jnb     short loc_18000A482
0x18000a434  mov     rdx, rbp; dwBytes
0x18000a437  mov     ecx, 8; dwFlags
0x18000a43c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a441  mov     r12, rax
0x18000a444  test    rax, rax
0x18000a447  jz      short loc_18000A47F
0x18000a449  mov     rbx, [rsi+rdi+40h]
0x18000a44e  call    cs:__imp_GetProcessHeap
0x18000a455  nop     dword ptr [rax+rax+00h]
0x18000a45a  mov     r8, rbx; lpMem
0x18000a45d  xor     edx, edx; dwFlags
0x18000a45f  mov     rcx, rax; hHeap
0x18000a462  call    cs:__imp_HeapFree
0x18000a469  nop     dword ptr [rax+rax+00h]
0x18000a46e  lea     rbx, [rdi+20h]
0x18000a472  mov     [rsi+rdi+40h], r12
0x18000a477  add     rbx, rsi
0x18000a47a  mov     [rsi+rdi+48h], rbp
0x18000a47f  xor     r12d, r12d
0x18000a482  mov     rcx, [rsi+rdi+40h]
0x18000a487  test    rcx, rcx
0x18000a48a  jz      loc_18000A51B
0x18000a490  mov     rbp, [rsi+rdi+48h]
0x18000a495  lea     r9, [r13+10h]
0x18000a499  mov     r8, [r15+38h]
0x18000a49d  add     rbp, rcx
0x18000a4a0  mov     rdx, rbp
0x18000a4a3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a4a8  mov     r8, [r15+80h]
0x18000a4af  mov     r9, rbx
0x18000a4b2  mov     rdx, rbp
0x18000a4b5  mov     rcx, rax
0x18000a4b8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a4bd  mov     rbx, rax
0x18000a4c0  cmp     rax, rbp
0x18000a4c3  jz      short loc_18000A506
0x18000a4c5  mov     r8, [r15+18h]; Source
0x18000a4c9  test    r8, r8
0x18000a4cc  jz      short loc_18000A506
0x18000a4ce  cmp     [r8], r12w
0x18000a4d2  jz      short loc_18000A506
0x18000a4d4  inc     r14
0x18000a4d7  cmp     [r8+r14*2], r12w
0x18000a4dc  jnz     short loc_18000A4D4
0x18000a4de  mov     rdx, rbp
0x18000a4e1  lea     r14, ds:2[r14*2]
0x18000a4e9  sub     rdx, rbx; DestinationSize
0x18000a4ec  cmp     rdx, r14
0x18000a4ef  jb      short loc_18000A506
0x18000a4f1  mov     r9, r14; SourceSize
0x18000a4f4  mov     rcx, rbx; Destination
0x18000a4f7  call    memcpy_s
0x18000a4fc  mov     [rsi+rdi+38h], rbx
0x18000a501  add     rbx, r14
0x18000a504  jmp     short loc_18000A50B
0x18000a506  mov     [rsi+rdi+38h], r12
0x18000a50b  sub     rbp, rbx
0x18000a50e  xor     edx, edx; Val
0x18000a510  mov     r8, rbp; Size
0x18000a513  mov     rcx, rbx; void *
0x18000a516  call    memset_0
0x18000a51b  add     rsp, 28h
0x18000a51f  pop     r15
0x18000a521  pop     r14
0x18000a523  pop     r13
0x18000a525  pop     r12
0x18000a527  pop     rdi
0x18000a528  pop     rsi
0x18000a529  pop     rbp
0x18000a52a  pop     rbx
0x18000a52b  retn
```
