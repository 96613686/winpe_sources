# CLKRLinearHashTable::_SplitRecordSet(CNodeClump *,CNodeClump *,ulong,ulong,ulong,CNodeClump *)

- ea: `0x18000f870`
- end: `0x18000fb43`
- name: `?_SplitRecordSet@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEAVCNodeClump@@0KKK0@Z`
- size: `723`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000f870`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa7e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000fa5e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000fa5e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000fac9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000fac9`

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
0x18000f870  mov     [rsp+arg_0], rbx
0x18000f875  mov     [rsp+arg_18], rbp
0x18000f87a  push    rsi
0x18000f87b  push    rdi
0x18000f87c  push    r12
0x18000f87e  push    r14
0x18000f880  push    r15
0x18000f882  sub     rsp, 60h
0x18000f886  mov     rax, cs:__security_cookie
0x18000f88d  xor     rax, rsp
0x18000f890  mov     [rsp+88h+var_30], rax
0x18000f895  movups  xmm0, xmmword ptr [rdx]
0x18000f898  mov     rsi, [rsp+88h+lpMem]
0x18000f8a0  xor     r12d, r12d
0x18000f8a3  movups  xmm1, xmmword ptr [rdx+10h]
0x18000f8a7  mov     edi, [rsp+88h+arg_28]
0x18000f8ae  mov     r15d, r9d
0x18000f8b1  mov     r10d, [rsp+88h+arg_20]
0x18000f8b9  lea     r9, [rsp+88h+var_68]
0x18000f8be  movups  [rsp+88h+var_68], xmm0
0x18000f8c3  mov     rbx, r8
0x18000f8c6  mov     r11, rdx
0x18000f8c9  movups  xmm0, xmmword ptr [rdx+20h]
0x18000f8cd  mov     ebp, r12d
0x18000f8d0  mov     r14d, r12d
0x18000f8d3  movups  [rsp+88h+var_58], xmm1
0x18000f8d8  movsd   xmm1, qword ptr [rdx+30h]
0x18000f8dd  mov     [rdx+10h], r12
0x18000f8e1  mov     dword ptr [rdx+0Ch], 1E3603Bh
0x18000f8e8  mov     [rdx+30h], r12
0x18000f8ec  mov     dword ptr [rdx+8], 1E3603Bh
0x18000f8f3  mov     [rdx+28h], r12
0x18000f8f7  mov     dword ptr [rdx+4], 1E3603Bh
0x18000f8fe  mov     [rdx+20h], r12
0x18000f902  mov     dword ptr [rdx], 1E3603Bh
0x18000f908  mov     [rdx+18h], r12
0x18000f90c  mov     [r8+10h], r12
0x18000f910  mov     dword ptr [r8+0Ch], 1E3603Bh
0x18000f918  mov     [r8+30h], r12
0x18000f91c  mov     dword ptr [r8+8], 1E3603Bh
0x18000f924  mov     [r8+28h], r12
0x18000f928  mov     dword ptr [r8+4], 1E3603Bh
0x18000f930  mov     [r8+20h], r12
0x18000f934  mov     dword ptr [r8], 1E3603Bh
0x18000f93b  mov     [r8+18h], r12
0x18000f93f  movups  [rsp+88h+var_48], xmm0
0x18000f944  movsd   [rsp+88h+var_38], xmm1
0x18000f94a  nop     word ptr [rax+rax+00h]
0x18000f950  mov     rdx, r12
0x18000f953  mov     ecx, [r9+rdx*4]
0x18000f957  cmp     ecx, 1E3603Bh
0x18000f95d  jz      loc_18000F9F2
0x18000f963  mov     eax, ecx
0x18000f965  mov     r8, rsi
0x18000f968  and     eax, r10d
0x18000f96b  cmp     eax, r15d
0x18000f96e  jnb     short loc_18000F979
0x18000f970  lea     eax, [r10+r10]
0x18000f974  or      eax, 1
0x18000f977  and     eax, ecx
0x18000f979  cmp     eax, edi
0x18000f97b  jz      loc_18000FAD7
0x18000f981  cmp     ebp, 4
0x18000f984  jnz     short loc_18000F9CA
0x18000f986  mov     rcx, rsi
0x18000f989  lea     rax, [rsi+10h]
0x18000f98d  mov     rsi, [rsi+10h]
0x18000f991  mov     ebp, r12d
0x18000f994  mov     [rax], r12
0x18000f997  mov     dword ptr [rcx+0Ch], 1E3603Bh
0x18000f99e  mov     [rcx+30h], r12
0x18000f9a2  mov     dword ptr [rcx+8], 1E3603Bh
0x18000f9a9  mov     [rcx+28h], r12
0x18000f9ad  mov     dword ptr [rcx+4], 1E3603Bh
0x18000f9b4  mov     [rcx+20h], r12
0x18000f9b8  mov     dword ptr [r8], 1E3603Bh
0x18000f9bf  mov     [rcx+18h], r12
0x18000f9c3  mov     [r11+10h], rcx
0x18000f9c7  mov     r11, rcx
0x18000f9ca  mov     eax, [r9+rdx*4]
0x18000f9ce  lea     r8, [rdx+3]
0x18000f9d2  movsxd  rcx, ebp
0x18000f9d5  lea     r8, [r9+r8*8]
0x18000f9d9  inc     ebp
0x18000f9db  mov     [r11+rcx*4], eax
0x18000f9df  mov     rax, [r8]
0x18000f9e2  mov     [r11+rcx*8+18h], rax
0x18000f9e7  mov     dword ptr [r9+rdx*4], 1E3603Bh
0x18000f9ef  mov     [r8], r12
0x18000f9f2  inc     rdx
0x18000f9f5  cmp     rdx, 4
0x18000f9f9  jnz     loc_18000F953
0x18000f9ff  mov     rax, r9
0x18000fa02  lea     rcx, [r9+10h]
0x18000fa06  mov     r9, [r9+10h]
0x18000fa0a  lea     rdx, [rsp+88h+var_68]
0x18000fa0f  cmp     rax, rdx
0x18000fa12  jz      short loc_18000FA1A
0x18000fa14  mov     [rcx], rsi
0x18000fa17  mov     rsi, rax
0x18000fa1a  test    r9, r9
0x18000fa1d  jnz     loc_18000F950
0x18000fa23  test    rsi, rsi
0x18000fa26  jz      short loc_18000FA9A
0x18000fa28  mov     rdi, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000fa2f  mov     rbp, rsi
0x18000fa32  mov     rsi, [rsi+10h]
0x18000fa36  mov     rbx, [rdi+18h]
0x18000fa3a  call    cs:__imp_GetCurrentThreadId
0x18000fa41  nop     dword ptr [rax+rax+00h]
0x18000fa46  mov     eax, eax
0x18000fa48  xor     edx, edx
0x18000fa4a  div     qword ptr [rbx+10h]
0x18000fa4e  mov     ecx, edx
0x18000fa50  imul    rcx, [rbx+8]
0x18000fa55  mov     rbx, [rbx]
0x18000fa58  add     rbx, rcx
0x18000fa5b  mov     rcx, rbx; ListHead
0x18000fa5e  call    cs:__imp_QueryDepthSList
0x18000fa65  nop     dword ptr [rax+rax+00h]
0x18000fa6a  movzx   eax, ax
0x18000fa6d  cmp     eax, [rdi+0Ch]
0x18000fa70  jl      short loc_18000FAC3
0x18000fa72  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000fa79  mov     r8, rbp; lpMem
0x18000fa7c  xor     edx, edx; dwFlags
0x18000fa7e  call    cs:__imp_HeapFree
0x18000fa85  nop     dword ptr [rax+rax+00h]
0x18000fa8a  lock dec dword ptr [rdi+40h]
0x18000fa8e  lock inc dword ptr [rdi+0C0h]
0x18000fa95  test    rsi, rsi
0x18000fa98  jnz     short loc_18000FA28
0x18000fa9a  xor     eax, eax
0x18000fa9c  mov     rcx, [rsp+88h+var_30]
0x18000faa1  xor     rcx, rsp; StackCookie
0x18000faa4  call    __security_check_cookie
0x18000faa9  lea     r11, [rsp+88h+var_28]
0x18000faae  mov     rbx, [r11+30h]
0x18000fab2  mov     rbp, [r11+48h]
0x18000fab6  mov     rsp, r11
0x18000fab9  pop     r15
0x18000fabb  pop     r14
0x18000fabd  pop     r12
0x18000fabf  pop     rdi
0x18000fac0  pop     rsi
0x18000fac1  retn
0x18000fac3  mov     rdx, rbp; ListEntry
0x18000fac6  mov     rcx, rbx; ListHead
0x18000fac9  call    cs:__imp_InterlockedPushEntrySList
0x18000fad0  nop     dword ptr [rax+rax+00h]
0x18000fad5  jmp     short loc_18000FA8E
0x18000fad7  cmp     r14d, 4
0x18000fadb  jnz     short loc_18000FB21
0x18000fadd  mov     rcx, rsi
0x18000fae0  lea     rax, [rsi+10h]
0x18000fae4  mov     rsi, [rsi+10h]
0x18000fae8  mov     r14d, r12d
0x18000faeb  mov     [rax], r12
0x18000faee  mov     dword ptr [rcx+0Ch], 1E3603Bh
0x18000faf5  mov     [rcx+30h], r12
0x18000faf9  mov     dword ptr [rcx+8], 1E3603Bh
0x18000fb00  mov     [rcx+28h], r12
0x18000fb04  mov     dword ptr [rcx+4], 1E3603Bh
0x18000fb0b  mov     [rcx+20h], r12
0x18000fb0f  mov     dword ptr [r8], 1E3603Bh
0x18000fb16  mov     [rcx+18h], r12
0x18000fb1a  mov     [rbx+10h], rcx
0x18000fb1e  mov     rbx, rcx
0x18000fb21  mov     eax, [r9+rdx*4]
0x18000fb25  lea     r8, [rdx+3]
0x18000fb29  movsxd  rcx, r14d
0x18000fb2c  lea     r8, [r9+r8*8]
0x18000fb30  inc     r14d
0x18000fb33  mov     [rbx+rcx*4], eax
0x18000fb36  mov     rax, [r8]
0x18000fb39  mov     [rbx+rcx*8+18h], rax
0x18000fb3e  jmp     loc_18000F9E7
```
