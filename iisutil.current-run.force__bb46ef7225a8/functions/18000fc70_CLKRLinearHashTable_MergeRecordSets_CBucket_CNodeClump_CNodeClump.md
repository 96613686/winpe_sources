# CLKRLinearHashTable::_MergeRecordSets(CBucket *,CNodeClump *,CNodeClump *)

- ea: `0x18000fc70`
- end: `0x18000fead`
- name: `?_MergeRecordSets@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEAVCBucket@@PEAVCNodeClump@@1@Z`
- size: `573`
- prototype: `enum LK_RETCODE __high(struct CBucket *, struct CNodeClump *, struct CNodeClump *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000fc70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd33`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000fd19`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000fd19`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000fd8e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000fd8e`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_MergeRecordSets(
        __int64 a1,
        __int64 a2,
        struct _SLIST_ENTRY *a3,
        struct _SLIST_ENTRY *a4)
{
  struct _SLIST_ENTRY *Next; // rax
  struct _SLIST_ENTRY *v6; // r10
  int j; // r9d
  ALLOC_CACHE_HANDLER *v8; // rsi
  struct _SLIST_ENTRY *v9; // rbp
  _QWORD *v10; // rbx
  union _SLIST_HEADER *v11; // rbx
  __int64 v13; // r9
  __int64 i; // r11
  struct _SLIST_ENTRY *v15; // rcx
  struct _SLIST_ENTRY **p_Next; // rdx
  struct _SLIST_ENTRY *v17; // r9
  struct _SLIST_ENTRY *v18; // rcx

  Next = (struct _SLIST_ENTRY *)(a2 + 8);
  v6 = a3;
LABEL_2:
  if ( Next[1].Next )
  {
    v13 = 0;
    while ( *((_DWORD *)&Next->Next + v13) != 31678523 )
    {
      v13 = (unsigned int)(v13 + 1);
      if ( (int)v13 >= 4 )
      {
        if ( (_DWORD)v13 != 4 )
          break;
        Next = Next[1].Next;
        goto LABEL_2;
      }
    }
  }
  j = 0;
  if ( LODWORD(Next->Next) != 31678523 )
  {
    j = 1;
    if ( HIDWORD(Next->Next) != 31678523 )
    {
      j = 2;
      if ( *((_DWORD *)&Next->Next + 2) != 31678523 )
      {
        j = 3;
        if ( *((_DWORD *)&Next->Next + 3) != 31678523 )
          j = 4;
      }
    }
  }
  while ( a3 )
  {
    for ( i = 0; i != 4; ++i )
    {
      if ( *((_DWORD *)&a3->Next + i) != 31678523 )
      {
        if ( j == 4 )
        {
          while ( 1 )
          {
            v17 = Next + 1;
            Next = Next[1].Next;
            if ( !Next )
              break;
            for ( j = 0; j < 4; ++j )
            {
              if ( *((_DWORD *)&Next->Next + j) == 31678523 )
                goto LABEL_37;
            }
          }
          Next = a4;
          v18 = a4 + 1;
          a4 = a4[1].Next;
          v18->Next = 0;
          *((_DWORD *)&Next->Next + 3) = 31678523;
          Next[3].Next = 0;
          *((_DWORD *)&Next->Next + 2) = 31678523;
          *((_QWORD *)&Next[2].Next + 1) = 0;
          HIDWORD(Next->Next) = 31678523;
          Next[2].Next = 0;
          LODWORD(Next->Next) = 31678523;
          *((_QWORD *)&Next[1].Next + 1) = 0;
          v17->Next = Next;
          j = 0;
        }
LABEL_37:
        *((_DWORD *)&Next->Next + j) = *((_DWORD *)&a3->Next + i);
        *((_QWORD *)&Next[1].Next + j + 1) = *((_QWORD *)&a3[1].Next + i + 1);
        *((_DWORD *)&a3->Next + i) = 31678523;
        *((_QWORD *)&a3[1].Next + i + 1) = 0;
        do
          ++j;
        while ( j != 4 && *((_DWORD *)&Next->Next + j) != 31678523 );
      }
    }
    v15 = a3;
    p_Next = &a3[1].Next;
    a3 = a3[1].Next;
    if ( v15 != v6 )
    {
      *p_Next = a4;
      a4 = v15;
    }
  }
  while ( a4 )
  {
    v8 = CNodeClump::sm_palloc;
    v9 = a4;
    a4 = a4[1].Next;
    v10 = (_QWORD *)*((_QWORD *)CNodeClump::sm_palloc + 3);
    v11 = (union _SLIST_HEADER *)(v10[1] * ((unsigned __int64)GetCurrentThreadId() % v10[2]) + *v10);
    if ( QueryDepthSList(v11) < *((int *)v8 + 3) )
    {
      InterlockedPushEntrySList(v11, v9);
    }
    else
    {
      HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v9);
      _InterlockedDecrement((volatile signed __int32 *)v8 + 16);
    }
    _InterlockedIncrement((volatile signed __int32 *)v8 + 48);
  }
  return 0;
}

```

## disassembly

```asm
0x18000fc70  push    rdi
0x18000fc72  sub     rsp, 20h
0x18000fc76  mov     rdi, r9
0x18000fc79  lea     rax, [rdx+8]
0x18000fc7d  mov     r10, r8
0x18000fc80  mov     rdx, [rax+10h]
0x18000fc84  test    rdx, rdx
0x18000fc87  jnz     loc_18000FD60
0x18000fc8d  xor     r9d, r9d
0x18000fc90  cmp     dword ptr [rax], 1E3603Bh
0x18000fc96  jz      short loc_18000FCCC
0x18000fc98  cmp     dword ptr [rax+4], 1E3603Bh
0x18000fc9f  mov     r9d, 1
0x18000fca5  jz      short loc_18000FCCC
0x18000fca7  cmp     dword ptr [rax+8], 1E3603Bh
0x18000fcae  mov     r9d, 2
0x18000fcb4  jz      short loc_18000FCCC
0x18000fcb6  cmp     dword ptr [rax+0Ch], 1E3603Bh
0x18000fcbd  mov     ecx, 4
0x18000fcc2  mov     r9d, 3
0x18000fcc8  cmovnz  r9d, ecx
0x18000fccc  test    r8, r8
0x18000fccf  jnz     loc_18000FDA0
0x18000fcd5  test    rdi, rdi
0x18000fcd8  jz      short loc_18000FD58
0x18000fcda  mov     [rsp+28h+arg_0], rbx
0x18000fcdf  mov     [rsp+28h+arg_8], rbp
0x18000fce4  mov     [rsp+28h+arg_10], rsi
0x18000fce9  mov     rsi, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000fcf0  mov     rbp, rdi
0x18000fcf3  mov     rdi, [rdi+10h]
0x18000fcf7  mov     rbx, [rsi+18h]
0x18000fcfb  call    cs:__imp_GetCurrentThreadId
0x18000fd01  mov     eax, eax
0x18000fd03  xor     edx, edx
0x18000fd05  div     qword ptr [rbx+10h]
0x18000fd09  mov     ecx, edx
0x18000fd0b  imul    rcx, [rbx+8]
0x18000fd10  mov     rbx, [rbx]
0x18000fd13  add     rbx, rcx
0x18000fd16  mov     rcx, rbx; ListHead
0x18000fd19  call    cs:__imp_QueryDepthSList
0x18000fd1f  movzx   eax, ax
0x18000fd22  cmp     eax, [rsi+0Ch]
0x18000fd25  jl      short loc_18000FD88
0x18000fd27  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000fd2e  mov     r8, rbp; lpMem
0x18000fd31  xor     edx, edx; dwFlags
0x18000fd33  call    cs:__imp_HeapFree
0x18000fd39  lock dec dword ptr [rsi+40h]
0x18000fd3d  lock inc dword ptr [rsi+0C0h]
0x18000fd44  test    rdi, rdi
0x18000fd47  jnz     short loc_18000FCE9
0x18000fd49  mov     rsi, [rsp+28h+arg_10]
0x18000fd4e  mov     rbp, [rsp+28h+arg_8]
0x18000fd53  mov     rbx, [rsp+28h+arg_0]
0x18000fd58  xor     eax, eax
0x18000fd5a  add     rsp, 20h
0x18000fd5e  pop     rdi
0x18000fd5f  retn
0x18000fd60  xor     r9d, r9d
0x18000fd63  cmp     dword ptr [rax+r9*4], 1E3603Bh
0x18000fd6b  jz      loc_18000FC8D
0x18000fd71  inc     r9d
0x18000fd74  cmp     r9d, 4
0x18000fd78  jl      short loc_18000FD63
0x18000fd7a  jnz     loc_18000FC8D
0x18000fd80  mov     rax, rdx
0x18000fd83  jmp     loc_18000FC80
0x18000fd88  mov     rdx, rbp; ListEntry
0x18000fd8b  mov     rcx, rbx; ListHead
0x18000fd8e  call    cs:__imp_InterlockedPushEntrySList
0x18000fd94  jmp     short loc_18000FD3D
0x18000fda0  xor     r11d, r11d
0x18000fda3  cmp     dword ptr [r8+r11*4], 1E3603Bh
0x18000fdab  jnz     short loc_18000FE0E
0x18000fdad  inc     r11
0x18000fdb0  cmp     r11, 4
0x18000fdb4  jnz     short loc_18000FDA3
0x18000fdb6  mov     rcx, r8
0x18000fdb9  lea     rdx, [r8+10h]
0x18000fdbd  mov     r8, [r8+10h]
0x18000fdc1  cmp     rcx, r10
0x18000fdc4  jnz     loc_18000FEA2
0x18000fdca  test    r8, r8
0x18000fdcd  jz      loc_18000FCD5
0x18000fdd3  jmp     short loc_18000FDA0
0x18000fdd5  lea     r9, [rax+10h]
0x18000fdd9  mov     rax, [rax+10h]
0x18000fddd  test    rax, rax
0x18000fde0  jz      short loc_18000FE16
0x18000fde2  xor     r9d, r9d
0x18000fde5  cmp     r9d, 4
0x18000fde9  jge     short loc_18000FDD5
0x18000fdeb  movsxd  rcx, r9d
0x18000fdee  cmp     dword ptr [rax+rcx*4], 1E3603Bh
0x18000fdf5  jz      short loc_18000FE6B
0x18000fdf7  inc     r9d
0x18000fdfa  jmp     short loc_18000FDE5
0x18000fdfc  movsxd  rcx, r9d
0x18000fdff  cmp     dword ptr [rax+rcx*4], 1E3603Bh
0x18000fe06  jnz     loc_18000FE90
0x18000fe0c  jmp     short loc_18000FDAD
0x18000fe0e  cmp     r9d, 4
0x18000fe12  jnz     short loc_18000FE6B
0x18000fe14  jmp     short loc_18000FDD5
0x18000fe16  mov     rax, rdi
0x18000fe19  lea     rcx, [rdi+10h]
0x18000fe1d  mov     rdx, rdi
0x18000fe20  mov     rdi, [rcx]
0x18000fe23  mov     qword ptr [rcx], 0
0x18000fe2a  mov     dword ptr [rax+0Ch], 1E3603Bh
0x18000fe31  mov     qword ptr [rax+30h], 0
0x18000fe39  mov     dword ptr [rax+8], 1E3603Bh
0x18000fe40  mov     qword ptr [rax+28h], 0
0x18000fe48  mov     dword ptr [rax+4], 1E3603Bh
0x18000fe4f  mov     qword ptr [rax+20h], 0
0x18000fe57  mov     dword ptr [rax], 1E3603Bh
0x18000fe5d  mov     qword ptr [rax+18h], 0
0x18000fe65  mov     [r9], rax
0x18000fe68  xor     r9d, r9d
0x18000fe6b  mov     ecx, [r8+r11*4]
0x18000fe6f  movsxd  rdx, r9d
0x18000fe72  mov     [rax+rdx*4], ecx
0x18000fe75  mov     rcx, [r8+r11*8+18h]
0x18000fe7a  mov     [rax+rdx*8+18h], rcx
0x18000fe7f  mov     dword ptr [r8+r11*4], 1E3603Bh
0x18000fe87  mov     qword ptr [r8+r11*8+18h], 0
0x18000fe90  inc     r9d
0x18000fe93  cmp     r9d, 4
0x18000fe97  jz      loc_18000FDAD
0x18000fe9d  jmp     loc_18000FDFC
0x18000fea2  mov     [rdx], rdi
0x18000fea5  mov     rdi, rcx
0x18000fea8  jmp     loc_18000FDCA
```
