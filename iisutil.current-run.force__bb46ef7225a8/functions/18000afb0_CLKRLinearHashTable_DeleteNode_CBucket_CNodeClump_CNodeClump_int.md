# CLKRLinearHashTable::_DeleteNode(CBucket *,CNodeClump * &,CNodeClump * &,int &)

- ea: `0x18000afb0`
- end: `0x18000b162`
- name: `?_DeleteNode@CLKRLinearHashTable@@AEAA_NPEAVCBucket@@AEAPEAVCNodeClump@@1AEAH@Z`
- size: `434`
- prototype: `bool __fastcall(CLKRLinearHashTable *__hidden this, struct CBucket *, struct CNodeClump **, struct CNodeClump **, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ae00`
- `0x18000bec0`
- `0x180016690`

## callees

- `0x18000afb0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b10b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b10b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000b0f1`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000b0f1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000b132`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000b132`

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
0x18000afb0  push    rbx
0x18000afb2  push    rbp
0x18000afb3  push    rsi
0x18000afb4  push    rdi
0x18000afb5  push    r14
0x18000afb7  push    r15
0x18000afb9  sub     rsp, 28h
0x18000afbd  mov     rbx, [rsp+58h+arg_20]
0x18000afc5  mov     rbp, rcx
0x18000afc8  mov     rcx, [r8]
0x18000afcb  mov     r15, rdx
0x18000afce  mov     edx, 0FFFFFFFFh
0x18000afd3  mov     r14, r9
0x18000afd6  mov     rsi, r8
0x18000afd9  movsxd  rax, dword ptr [rbx]
0x18000afdc  mov     rcx, [rcx+rax*8+18h]
0x18000afe1  mov     rax, [rbp+38h]
0x18000afe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afea  mov     r8, [rsi]
0x18000afed  xor     r11d, r11d
0x18000aff0  movsxd  rcx, dword ptr [rbx]
0x18000aff3  mov     rdi, r8
0x18000aff6  mov     r10d, ecx
0x18000aff9  mov     rax, [rdi+10h]
0x18000affd  test    rax, rax
0x18000b000  jnz     short loc_18000B06B
0x18000b002  cmp     r10d, 4
0x18000b006  jnz     loc_18000B090
0x18000b00c  movsxd  rdx, r10d
0x18000b00f  dec     r10d
0x18000b012  dec     rdx
0x18000b015  mov     rax, [rdi+rdx*8+18h]
0x18000b01a  lea     r9, [rdi+rdx*8]
0x18000b01e  mov     [r8+rcx*8+18h], rax
0x18000b023  lea     r8, [rdi+rdx*4]
0x18000b027  mov     rcx, [rsi]
0x18000b02a  mov     eax, [r8]
0x18000b02d  movsxd  rdx, dword ptr [rbx]
0x18000b030  mov     [rcx+rdx*4], eax
0x18000b033  lea     rax, [r15+8]
0x18000b037  mov     [r9+18h], r11
0x18000b03b  mov     dword ptr [r8], 1E3603Bh
0x18000b042  mov     ecx, [rbx]
0x18000b044  test    ecx, ecx
0x18000b046  jnz     short loc_18000B073
0x18000b048  cmp     [rsi], rax
0x18000b04b  jz      loc_18000B121
0x18000b051  mov     dword ptr [rbx], 4
0x18000b057  mov     rcx, [r14]
0x18000b05a  mov     [rsi], rcx
0x18000b05d  cmp     rcx, rax
0x18000b060  jnz     loc_18000B13A
0x18000b066  mov     [r14], r11
0x18000b069  jmp     short loc_18000B077
0x18000b06b  mov     rdi, rax
0x18000b06e  mov     r10d, r11d
0x18000b071  jmp     short loc_18000AFF9
0x18000b073  dec     ecx
0x18000b075  mov     [rbx], ecx
0x18000b077  test    r10d, r10d
0x18000b07a  jz      short loc_18000B0AF
0x18000b07c  lock dec dword ptr [rbp+78h]
0x18000b080  mov     al, 1
0x18000b082  add     rsp, 28h
0x18000b086  pop     r15
0x18000b088  pop     r14
0x18000b08a  pop     rdi
0x18000b08b  pop     rsi
0x18000b08c  pop     rbp
0x18000b08d  pop     rbx
0x18000b08e  retn
0x18000b090  movsxd  rax, r10d
0x18000b093  cmp     dword ptr [rdi+rax*4], 1E3603Bh
0x18000b09a  jz      loc_18000B00C
0x18000b0a0  inc     r10d
0x18000b0a3  cmp     r10d, 4
0x18000b0a7  jz      loc_18000B00C
0x18000b0ad  jmp     short loc_18000B090
0x18000b0af  cmp     rdi, rax
0x18000b0b2  jz      short loc_18000B07C
0x18000b0b4  cmp     [rax+10h], rdi
0x18000b0b8  jz      short loc_18000B0C4
0x18000b0ba  mov     rax, [rax+10h]
0x18000b0be  cmp     [rax+10h], rdi
0x18000b0c2  jnz     short loc_18000B0BA
0x18000b0c4  mov     rsi, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000b0cb  mov     [rax+10h], r11
0x18000b0cf  mov     rbx, [rsi+18h]
0x18000b0d3  call    cs:__imp_GetCurrentThreadId
0x18000b0d9  mov     eax, eax
0x18000b0db  xor     edx, edx
0x18000b0dd  div     qword ptr [rbx+10h]
0x18000b0e1  mov     ecx, edx
0x18000b0e3  imul    rcx, [rbx+8]
0x18000b0e8  mov     rbx, [rbx]
0x18000b0eb  add     rbx, rcx
0x18000b0ee  mov     rcx, rbx; ListHead
0x18000b0f1  call    cs:__imp_QueryDepthSList
0x18000b0f7  movzx   eax, ax
0x18000b0fa  cmp     eax, [rsi+0Ch]
0x18000b0fd  jl      short loc_18000B12C
0x18000b0ff  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000b106  mov     r8, rdi; lpMem
0x18000b109  xor     edx, edx; dwFlags
0x18000b10b  call    cs:__imp_HeapFree
0x18000b111  lock dec dword ptr [rsi+40h]
0x18000b115  lock inc dword ptr [rsi+0C0h]
0x18000b11c  jmp     loc_18000B07C
0x18000b121  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000b127  jmp     loc_18000B077
0x18000b12c  mov     rdx, rdi; ListEntry
0x18000b12f  mov     rcx, rbx; ListHead
0x18000b132  call    cs:__imp_InterlockedPushEntrySList
0x18000b138  jmp     short loc_18000B115
0x18000b13a  mov     [r14], rax
0x18000b13d  mov     rcx, [rsi]
0x18000b140  cmp     [r15+18h], rcx
0x18000b144  jz      loc_18000B077
0x18000b14a  mov     rdx, rax
0x18000b14d  mov     rdx, [rdx+10h]
0x18000b151  mov     [r14], rdx
0x18000b154  mov     rcx, [rsi]
0x18000b157  cmp     [rdx+10h], rcx
0x18000b15b  jnz     short loc_18000B14D
0x18000b15d  jmp     loc_18000B077
```
