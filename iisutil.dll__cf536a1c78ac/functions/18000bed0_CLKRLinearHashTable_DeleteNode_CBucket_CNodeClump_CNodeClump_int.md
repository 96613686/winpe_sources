# CLKRLinearHashTable::_DeleteNode(CBucket *,CNodeClump * &,CNodeClump * &,int &)

- ea: `0x18000bed0`
- end: `0x18000c09a`
- name: `?_DeleteNode@CLKRLinearHashTable@@AEAA_NPEAVCBucket@@AEAPEAVCNodeClump@@1AEAH@Z`
- size: `458`
- prototype: `bool __fastcall(CLKRLinearHashTable *__hidden this, struct CBucket *, struct CNodeClump **, struct CNodeClump **, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b690`
- `0x18000ce30`
- `0x1800172c0`

## callees

- `0x18000bed0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bff3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c037`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c037`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000c017`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000c017`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000c064`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000c064`

## pseudocode

```c
char __fastcall CLKRLinearHashTable::_DeleteNode(
        CLKRLinearHashTable *this,
        struct CNodeClump **a2,
        struct _SLIST_ENTRY **a3,
        struct CNodeClump **a4,
        int *a5)
{
  struct _SLIST_ENTRY *Next; // rdi
  int v10; // r10d
  __int64 v11; // rdx
  int v12; // r10d
  _DWORD *v13; // r8
  struct CNodeClump *v14; // rax
  struct CNodeClump *v15; // rcx
  ALLOC_CACHE_HANDLER *v17; // rsi
  _QWORD *v18; // rbx
  union _SLIST_HEADER *v19; // rbx
  char *v20; // rdx

  (*((void (__fastcall **)(_QWORD, __int64))this + 7))(*((_QWORD *)&(*a3)[1].Next + *a5 + 1), 0xFFFFFFFFLL);
  Next = *a3;
  v10 = *a5;
  while ( Next[1].Next )
  {
    Next = Next[1].Next;
    v10 = 0;
  }
  for ( ; v10 != 4; ++v10 )
  {
    if ( *((_DWORD *)&Next->Next + v10) == 31678523 )
      break;
  }
  v11 = v10;
  v12 = v10 - 1;
  *((_QWORD *)&(*a3)[1].Next + *a5 + 1) = *((_QWORD *)&Next[1].Next + v11--);
  v13 = (_DWORD *)Next + v11;
  *((_DWORD *)&(*a3)->Next + *a5) = *v13;
  v14 = (struct CNodeClump *)(a2 + 1);
  *((_QWORD *)&Next[1].Next + v11 + 1) = 0;
  *v13 = 31678523;
  if ( *a5 )
  {
    --*a5;
  }
  else if ( *a3 == (struct _SLIST_ENTRY *)v14 )
  {
    *a5 = -1;
  }
  else
  {
    *a5 = 4;
    v15 = *a4;
    *a3 = (struct _SLIST_ENTRY *)*a4;
    if ( v15 == v14 )
    {
      *a4 = 0;
    }
    else
    {
      *a4 = v14;
      if ( a2[3] != (struct CNodeClump *)*a3 )
      {
        v20 = (char *)(a2 + 1);
        do
        {
          v20 = (char *)*((_QWORD *)v20 + 2);
          *a4 = (struct CNodeClump *)v20;
        }
        while ( *((struct _SLIST_ENTRY **)v20 + 2) != *a3 );
      }
    }
  }
  if ( !v12 && Next != (struct _SLIST_ENTRY *)v14 )
  {
    if ( a2[3] != (struct CNodeClump *)Next )
    {
      do
        v14 = (struct CNodeClump *)*((_QWORD *)v14 + 2);
      while ( *((struct _SLIST_ENTRY **)v14 + 2) != Next );
    }
    v17 = CNodeClump::sm_palloc;
    *((_QWORD *)v14 + 2) = 0;
    v18 = (_QWORD *)*((_QWORD *)v17 + 3);
    v19 = (union _SLIST_HEADER *)(v18[1] * ((unsigned __int64)GetCurrentThreadId() % v18[2]) + *v18);
    if ( QueryDepthSList(v19) < *((int *)v17 + 3) )
    {
      InterlockedPushEntrySList(v19, Next);
    }
    else
    {
      HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, Next);
      _InterlockedDecrement((volatile signed __int32 *)v17 + 16);
    }
    _InterlockedIncrement((volatile signed __int32 *)v17 + 48);
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 30);
  return 1;
}

```

## disassembly

```asm
0x18000bed0  push    rbx
0x18000bed2  push    rbp
0x18000bed3  push    rsi
0x18000bed4  push    rdi
0x18000bed5  push    r14
0x18000bed7  push    r15
0x18000bed9  sub     rsp, 28h
0x18000bedd  mov     rbx, [rsp+58h+arg_20]
0x18000bee5  mov     rbp, rcx
0x18000bee8  mov     rcx, [r8]
0x18000beeb  mov     r15, rdx
0x18000beee  mov     edx, 0FFFFFFFFh
0x18000bef3  mov     r14, r9
0x18000bef6  mov     rsi, r8
0x18000bef9  movsxd  rax, dword ptr [rbx]
0x18000befc  mov     rcx, [rcx+rax*8+18h]
0x18000bf01  mov     rax, [rbp+38h]
0x18000bf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0a  mov     r8, [rsi]
0x18000bf0d  xor     r11d, r11d
0x18000bf10  movsxd  rcx, dword ptr [rbx]
0x18000bf13  mov     rdi, r8
0x18000bf16  mov     r10d, ecx
0x18000bf19  mov     rax, [rdi+10h]
0x18000bf1d  test    rax, rax
0x18000bf20  jnz     short loc_18000BF8B
0x18000bf22  cmp     r10d, 4
0x18000bf26  jnz     loc_18000BFB0
0x18000bf2c  movsxd  rdx, r10d
0x18000bf2f  dec     r10d
0x18000bf32  dec     rdx
0x18000bf35  mov     rax, [rdi+rdx*8+18h]
0x18000bf3a  lea     r9, [rdi+rdx*8]
0x18000bf3e  mov     [r8+rcx*8+18h], rax
0x18000bf43  lea     r8, [rdi+rdx*4]
0x18000bf47  mov     rcx, [rsi]
0x18000bf4a  mov     eax, [r8]
0x18000bf4d  movsxd  rdx, dword ptr [rbx]
0x18000bf50  mov     [rcx+rdx*4], eax
0x18000bf53  lea     rax, [r15+8]
0x18000bf57  mov     [r9+18h], r11
0x18000bf5b  mov     dword ptr [r8], 1E3603Bh
0x18000bf62  mov     ecx, [rbx]
0x18000bf64  test    ecx, ecx
0x18000bf66  jnz     short loc_18000BF93
0x18000bf68  cmp     [rsi], rax
0x18000bf6b  jz      loc_18000C053
0x18000bf71  mov     dword ptr [rbx], 4
0x18000bf77  mov     rcx, [r14]
0x18000bf7a  mov     [rsi], rcx
0x18000bf7d  cmp     rcx, rax
0x18000bf80  jnz     loc_18000C072
0x18000bf86  mov     [r14], r11
0x18000bf89  jmp     short loc_18000BF97
0x18000bf8b  mov     rdi, rax
0x18000bf8e  mov     r10d, r11d
0x18000bf91  jmp     short loc_18000BF19
0x18000bf93  dec     ecx
0x18000bf95  mov     [rbx], ecx
0x18000bf97  test    r10d, r10d
0x18000bf9a  jz      short loc_18000BFCF
0x18000bf9c  lock dec dword ptr [rbp+78h]
0x18000bfa0  mov     al, 1
0x18000bfa2  add     rsp, 28h
0x18000bfa6  pop     r15
0x18000bfa8  pop     r14
0x18000bfaa  pop     rdi
0x18000bfab  pop     rsi
0x18000bfac  pop     rbp
0x18000bfad  pop     rbx
0x18000bfae  retn
0x18000bfb0  movsxd  rax, r10d
0x18000bfb3  cmp     dword ptr [rdi+rax*4], 1E3603Bh
0x18000bfba  jz      loc_18000BF2C
0x18000bfc0  inc     r10d
0x18000bfc3  cmp     r10d, 4
0x18000bfc7  jz      loc_18000BF2C
0x18000bfcd  jmp     short loc_18000BFB0
0x18000bfcf  cmp     rdi, rax
0x18000bfd2  jz      short loc_18000BF9C
0x18000bfd4  cmp     [rax+10h], rdi
0x18000bfd8  jz      short loc_18000BFE4
0x18000bfda  mov     rax, [rax+10h]
0x18000bfde  cmp     [rax+10h], rdi
0x18000bfe2  jnz     short loc_18000BFDA
0x18000bfe4  mov     rsi, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000bfeb  mov     [rax+10h], r11
0x18000bfef  mov     rbx, [rsi+18h]
0x18000bff3  call    cs:__imp_GetCurrentThreadId
0x18000bffa  nop     dword ptr [rax+rax+00h]
0x18000bfff  mov     eax, eax
0x18000c001  xor     edx, edx
0x18000c003  div     qword ptr [rbx+10h]
0x18000c007  mov     ecx, edx
0x18000c009  imul    rcx, [rbx+8]
0x18000c00e  mov     rbx, [rbx]
0x18000c011  add     rbx, rcx
0x18000c014  mov     rcx, rbx; ListHead
0x18000c017  call    cs:__imp_QueryDepthSList
0x18000c01e  nop     dword ptr [rax+rax+00h]
0x18000c023  movzx   eax, ax
0x18000c026  cmp     eax, [rsi+0Ch]
0x18000c029  jl      short loc_18000C05E
0x18000c02b  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000c032  mov     r8, rdi; lpMem
0x18000c035  xor     edx, edx; dwFlags
0x18000c037  call    cs:__imp_HeapFree
0x18000c03e  nop     dword ptr [rax+rax+00h]
0x18000c043  lock dec dword ptr [rsi+40h]
0x18000c047  lock inc dword ptr [rsi+0C0h]
0x18000c04e  jmp     loc_18000BF9C
0x18000c053  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000c059  jmp     loc_18000BF97
0x18000c05e  mov     rdx, rdi; ListEntry
0x18000c061  mov     rcx, rbx; ListHead
0x18000c064  call    cs:__imp_InterlockedPushEntrySList
0x18000c06b  nop     dword ptr [rax+rax+00h]
0x18000c070  jmp     short loc_18000C047
0x18000c072  mov     [r14], rax
0x18000c075  mov     rcx, [rsi]
0x18000c078  cmp     [r15+18h], rcx
0x18000c07c  jz      loc_18000BF97
0x18000c082  mov     rdx, rax
0x18000c085  mov     rdx, [rdx+10h]
0x18000c089  mov     [r14], rdx
0x18000c08c  mov     rcx, [rsi]
0x18000c08f  cmp     [rdx+10h], rcx
0x18000c093  jnz     short loc_18000C085
0x18000c095  jmp     loc_18000BF97
```
