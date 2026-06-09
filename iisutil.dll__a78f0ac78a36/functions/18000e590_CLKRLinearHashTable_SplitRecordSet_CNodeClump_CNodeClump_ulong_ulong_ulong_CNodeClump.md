# CLKRLinearHashTable::_SplitRecordSet(CNodeClump *,CNodeClump *,ulong,ulong,ulong,CNodeClump *)

- ea: `0x18000e590`
- end: `0x18000e84a`
- name: `?_SplitRecordSet@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEAVCNodeClump@@0KKK0@Z`
- size: `698`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e590`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e75a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e75a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e792`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e792`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000e778`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000e778`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e7d6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e7d6`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_SplitRecordSet(
        __int64 a1,
        char *a2,
        char *a3,
        unsigned int a4,
        int a5,
        int a6,
        char *lpMem)
{
  __int128 v8; // xmm1
  _OWORD *v10; // r9
  char *v11; // rbx
  char *v12; // r11
  __int128 v13; // xmm0
  int v14; // ebp
  int v15; // r14d
  __int64 i; // rdx
  unsigned int v17; // ecx
  _DWORD *v18; // r8
  int v19; // eax
  char *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // r8
  char *v24; // rax
  _QWORD *v25; // rcx
  ALLOC_CACHE_HANDLER *v26; // rdi
  struct _SLIST_ENTRY *v27; // rbp
  _QWORD *v28; // rbx
  union _SLIST_HEADER *v29; // rbx
  char *v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  _OWORD v34[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v35; // [rsp+50h] [rbp-38h]

  v8 = *((_OWORD *)a2 + 1);
  v10 = v34;
  v34[0] = *(_OWORD *)a2;
  v11 = a3;
  v12 = a2;
  v13 = *((_OWORD *)a2 + 2);
  v14 = 0;
  v15 = 0;
  v34[1] = v8;
  *(_QWORD *)&v8 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 2) = 0;
  *((_DWORD *)a2 + 3) = 31678523;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 2) = 31678523;
  *((_QWORD *)a2 + 5) = 0;
  *((_DWORD *)a2 + 1) = 31678523;
  *((_QWORD *)a2 + 4) = 0;
  *(_DWORD *)a2 = 31678523;
  *((_QWORD *)a2 + 3) = 0;
  *((_QWORD *)a3 + 2) = 0;
  *((_DWORD *)a3 + 3) = 31678523;
  *((_QWORD *)a3 + 6) = 0;
  *((_DWORD *)a3 + 2) = 31678523;
  *((_QWORD *)a3 + 5) = 0;
  *((_DWORD *)a3 + 1) = 31678523;
  *((_QWORD *)a3 + 4) = 0;
  *(_DWORD *)a3 = 31678523;
  *((_QWORD *)a3 + 3) = 0;
  v34[2] = v13;
  v35 = v8;
  do
  {
    for ( i = 0; i != 4; ++i )
    {
      v17 = *((_DWORD *)v10 + i);
      if ( v17 != 31678523 )
      {
        v18 = lpMem;
        v19 = a5 & v17;
        if ( (a5 & v17) < a4 )
          v19 = v17 & ((2 * a5) | 1);
        if ( v19 == a6 )
        {
          if ( v15 == 4 )
          {
            v31 = lpMem;
            v32 = lpMem + 16;
            lpMem = (char *)*((_QWORD *)lpMem + 2);
            v15 = 0;
            *v32 = 0;
            *((_DWORD *)v31 + 3) = 31678523;
            *((_QWORD *)v31 + 6) = 0;
            *((_DWORD *)v31 + 2) = 31678523;
            *((_QWORD *)v31 + 5) = 0;
            *((_DWORD *)v31 + 1) = 31678523;
            *((_QWORD *)v31 + 4) = 0;
            *v18 = 31678523;
            *((_QWORD *)v31 + 3) = 0;
            *((_QWORD *)v11 + 2) = v31;
            v11 = v31;
          }
          v33 = v15;
          v23 = (_QWORD *)v10 + i + 3;
          ++v15;
          *(_DWORD *)&v11[4 * v33] = *((_DWORD *)v10 + i);
          *(_QWORD *)&v11[8 * v33 + 24] = *v23;
        }
        else
        {
          if ( v14 == 4 )
          {
            v20 = lpMem;
            v21 = lpMem + 16;
            lpMem = (char *)*((_QWORD *)lpMem + 2);
            v14 = 0;
            *v21 = 0;
            *((_DWORD *)v20 + 3) = 31678523;
            *((_QWORD *)v20 + 6) = 0;
            *((_DWORD *)v20 + 2) = 31678523;
            *((_QWORD *)v20 + 5) = 0;
            *((_DWORD *)v20 + 1) = 31678523;
            *((_QWORD *)v20 + 4) = 0;
            *v18 = 31678523;
            *((_QWORD *)v20 + 3) = 0;
            *((_QWORD *)v12 + 2) = v20;
            v12 = v20;
          }
          v22 = v14;
          v23 = (_QWORD *)v10 + i + 3;
          ++v14;
          *(_DWORD *)&v12[4 * v22] = *((_DWORD *)v10 + i);
          *(_QWORD *)&v12[8 * v22 + 24] = *v23;
        }
        *((_DWORD *)v10 + i) = 31678523;
        *v23 = 0;
      }
    }
    v24 = (char *)v10;
    v25 = v10 + 1;
    v10 = (_OWORD *)*((_QWORD *)v10 + 2);
    if ( v24 != (char *)v34 )
    {
      *v25 = lpMem;
      lpMem = v24;
    }
  }
  while ( v10 );
  while ( lpMem )
  {
    v26 = CNodeClump::sm_palloc;
    v27 = (struct _SLIST_ENTRY *)lpMem;
    lpMem = (char *)*((_QWORD *)lpMem + 2);
    v28 = (_QWORD *)*((_QWORD *)CNodeClump::sm_palloc + 3);
    v29 = (union _SLIST_HEADER *)(v28[1] * ((unsigned __int64)GetCurrentThreadId() % v28[2]) + *v28);
    if ( QueryDepthSList(v29) < *((int *)v26 + 3) )
    {
      InterlockedPushEntrySList(v29, v27);
    }
    else
    {
      HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v27);
      _InterlockedDecrement((volatile signed __int32 *)v26 + 16);
    }
    _InterlockedIncrement((volatile signed __int32 *)v26 + 48);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e590  mov     [rsp+arg_0], rbx
0x18000e595  mov     [rsp+arg_18], rbp
0x18000e59a  push    rsi
0x18000e59b  push    rdi
0x18000e59c  push    r12
0x18000e59e  push    r14
0x18000e5a0  push    r15
0x18000e5a2  sub     rsp, 60h
0x18000e5a6  mov     rax, cs:__security_cookie
0x18000e5ad  xor     rax, rsp
0x18000e5b0  mov     [rsp+88h+var_30], rax
0x18000e5b5  movups  xmm0, xmmword ptr [rdx]
0x18000e5b8  mov     rsi, [rsp+88h+lpMem]
0x18000e5c0  xor     r12d, r12d
0x18000e5c3  movups  xmm1, xmmword ptr [rdx+10h]
0x18000e5c7  mov     edi, [rsp+88h+arg_28]
0x18000e5ce  mov     r15d, r9d
0x18000e5d1  mov     r10d, [rsp+88h+arg_20]
0x18000e5d9  lea     r9, [rsp+88h+var_68]
0x18000e5de  movups  [rsp+88h+var_68], xmm0
0x18000e5e3  mov     rbx, r8
0x18000e5e6  mov     r11, rdx
0x18000e5e9  movups  xmm0, xmmword ptr [rdx+20h]
0x18000e5ed  mov     ebp, r12d
0x18000e5f0  mov     r14d, r12d
0x18000e5f3  movups  [rsp+88h+var_58], xmm1
0x18000e5f8  movsd   xmm1, qword ptr [rdx+30h]
0x18000e5fd  mov     [rdx+10h], r12
0x18000e601  mov     dword ptr [rdx+0Ch], 1E3603Bh
0x18000e608  mov     [rdx+30h], r12
0x18000e60c  mov     dword ptr [rdx+8], 1E3603Bh
0x18000e613  mov     [rdx+28h], r12
0x18000e617  mov     dword ptr [rdx+4], 1E3603Bh
0x18000e61e  mov     [rdx+20h], r12
0x18000e622  mov     dword ptr [rdx], 1E3603Bh
0x18000e628  mov     [rdx+18h], r12
0x18000e62c  mov     [r8+10h], r12
0x18000e630  mov     dword ptr [r8+0Ch], 1E3603Bh
0x18000e638  mov     [r8+30h], r12
0x18000e63c  mov     dword ptr [r8+8], 1E3603Bh
0x18000e644  mov     [r8+28h], r12
0x18000e648  mov     dword ptr [r8+4], 1E3603Bh
0x18000e650  mov     [r8+20h], r12
0x18000e654  mov     dword ptr [r8], 1E3603Bh
0x18000e65b  mov     [r8+18h], r12
0x18000e65f  movups  [rsp+88h+var_48], xmm0
0x18000e664  movsd   [rsp+88h+var_38], xmm1
0x18000e66a  nop     word ptr [rax+rax+00h]
0x18000e670  mov     rdx, r12
0x18000e673  mov     ecx, [r9+rdx*4]
0x18000e677  cmp     ecx, 1E3603Bh
0x18000e67d  jz      loc_18000E712
0x18000e683  mov     eax, ecx
0x18000e685  mov     r8, rsi
0x18000e688  and     eax, r10d
0x18000e68b  cmp     eax, r15d
0x18000e68e  jnb     short loc_18000E699
0x18000e690  lea     eax, [r10+r10]
0x18000e694  or      eax, 1
0x18000e697  and     eax, ecx
0x18000e699  cmp     eax, edi
0x18000e69b  jz      loc_18000E7DE
0x18000e6a1  cmp     ebp, 4
0x18000e6a4  jnz     short loc_18000E6EA
0x18000e6a6  mov     rcx, rsi
0x18000e6a9  lea     rax, [rsi+10h]
0x18000e6ad  mov     rsi, [rsi+10h]
0x18000e6b1  mov     ebp, r12d
0x18000e6b4  mov     [rax], r12
0x18000e6b7  mov     dword ptr [rcx+0Ch], 1E3603Bh
0x18000e6be  mov     [rcx+30h], r12
0x18000e6c2  mov     dword ptr [rcx+8], 1E3603Bh
0x18000e6c9  mov     [rcx+28h], r12
0x18000e6cd  mov     dword ptr [rcx+4], 1E3603Bh
0x18000e6d4  mov     [rcx+20h], r12
0x18000e6d8  mov     dword ptr [r8], 1E3603Bh
0x18000e6df  mov     [rcx+18h], r12
0x18000e6e3  mov     [r11+10h], rcx
0x18000e6e7  mov     r11, rcx
0x18000e6ea  mov     eax, [r9+rdx*4]
0x18000e6ee  lea     r8, [rdx+3]
0x18000e6f2  movsxd  rcx, ebp
0x18000e6f5  lea     r8, [r9+r8*8]
0x18000e6f9  inc     ebp
0x18000e6fb  mov     [r11+rcx*4], eax
0x18000e6ff  mov     rax, [r8]
0x18000e702  mov     [r11+rcx*8+18h], rax
0x18000e707  mov     dword ptr [r9+rdx*4], 1E3603Bh
0x18000e70f  mov     [r8], r12
0x18000e712  inc     rdx
0x18000e715  cmp     rdx, 4
0x18000e719  jnz     loc_18000E673
0x18000e71f  mov     rax, r9
0x18000e722  lea     rcx, [r9+10h]
0x18000e726  mov     r9, [r9+10h]
0x18000e72a  lea     rdx, [rsp+88h+var_68]
0x18000e72f  cmp     rax, rdx
0x18000e732  jz      short loc_18000E73A
0x18000e734  mov     [rcx], rsi
0x18000e737  mov     rsi, rax
0x18000e73a  test    r9, r9
0x18000e73d  jnz     loc_18000E670
0x18000e743  test    rsi, rsi
0x18000e746  jz      short loc_18000E7A8
0x18000e748  mov     rdi, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000e74f  mov     rbp, rsi
0x18000e752  mov     rsi, [rsi+10h]
0x18000e756  mov     rbx, [rdi+18h]
0x18000e75a  call    cs:__imp_GetCurrentThreadId
0x18000e760  mov     eax, eax
0x18000e762  xor     edx, edx
0x18000e764  div     qword ptr [rbx+10h]
0x18000e768  mov     ecx, edx
0x18000e76a  imul    rcx, [rbx+8]
0x18000e76f  mov     rbx, [rbx]
0x18000e772  add     rbx, rcx
0x18000e775  mov     rcx, rbx; ListHead
0x18000e778  call    cs:__imp_QueryDepthSList
0x18000e77e  movzx   eax, ax
0x18000e781  cmp     eax, [rdi+0Ch]
0x18000e784  jl      short loc_18000E7D0
0x18000e786  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000e78d  mov     r8, rbp; lpMem
0x18000e790  xor     edx, edx; dwFlags
0x18000e792  call    cs:__imp_HeapFree
0x18000e798  lock dec dword ptr [rdi+40h]
0x18000e79c  lock inc dword ptr [rdi+0C0h]
0x18000e7a3  test    rsi, rsi
0x18000e7a6  jnz     short loc_18000E748
0x18000e7a8  xor     eax, eax
0x18000e7aa  mov     rcx, [rsp+88h+var_30]
0x18000e7af  xor     rcx, rsp; StackCookie
0x18000e7b2  call    __security_check_cookie
0x18000e7b7  lea     r11, [rsp+88h+var_28]
0x18000e7bc  mov     rbx, [r11+30h]
0x18000e7c0  mov     rbp, [r11+48h]
0x18000e7c4  mov     rsp, r11
0x18000e7c7  pop     r15
0x18000e7c9  pop     r14
0x18000e7cb  pop     r12
0x18000e7cd  pop     rdi
0x18000e7ce  pop     rsi
0x18000e7cf  retn
0x18000e7d0  mov     rdx, rbp; ListEntry
0x18000e7d3  mov     rcx, rbx; ListHead
0x18000e7d6  call    cs:__imp_InterlockedPushEntrySList
0x18000e7dc  jmp     short loc_18000E79C
0x18000e7de  cmp     r14d, 4
0x18000e7e2  jnz     short loc_18000E828
0x18000e7e4  mov     rcx, rsi
0x18000e7e7  lea     rax, [rsi+10h]
0x18000e7eb  mov     rsi, [rsi+10h]
0x18000e7ef  mov     r14d, r12d
0x18000e7f2  mov     [rax], r12
0x18000e7f5  mov     dword ptr [rcx+0Ch], 1E3603Bh
0x18000e7fc  mov     [rcx+30h], r12
0x18000e800  mov     dword ptr [rcx+8], 1E3603Bh
0x18000e807  mov     [rcx+28h], r12
0x18000e80b  mov     dword ptr [rcx+4], 1E3603Bh
0x18000e812  mov     [rcx+20h], r12
0x18000e816  mov     dword ptr [r8], 1E3603Bh
0x18000e81d  mov     [rcx+18h], r12
0x18000e821  mov     [rbx+10h], rcx
0x18000e825  mov     rbx, rcx
0x18000e828  mov     eax, [r9+rdx*4]
0x18000e82c  lea     r8, [rdx+3]
0x18000e830  movsxd  rcx, r14d
0x18000e833  lea     r8, [r9+r8*8]
0x18000e837  inc     r14d
0x18000e83a  mov     [rbx+rcx*4], eax
0x18000e83d  mov     rax, [r8]
0x18000e840  mov     [rbx+rcx*8+18h], rax
0x18000e845  jmp     loc_18000E707
```
