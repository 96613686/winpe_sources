# CLKRLinearHashTable::operator delete(void *)

- ea: `0x18000f8c0`
- end: `0x18000f94a`
- name: `??3CLKRLinearHashTable@@SAXPEAX@Z`
- size: `138`
- prototype: `void __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f890`

## callees

- `0x18000f8c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f91b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f91b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000f901`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000f901`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000f942`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000f942`

## pseudocode

```c
void __fastcall CLKRLinearHashTable::operator delete(PSLIST_ENTRY ListEntry)
{
  ALLOC_CACHE_HANDLER *v1; // rdi
  _QWORD *v3; // rbx
  union _SLIST_HEADER *v4; // rbx

  if ( ListEntry )
  {
    v1 = CLKRLinearHashTable::sm_palloc;
    v3 = (_QWORD *)*((_QWORD *)CLKRLinearHashTable::sm_palloc + 3);
    v4 = (union _SLIST_HEADER *)(v3[1] * ((unsigned __int64)GetCurrentThreadId() % v3[2]) + *v3);
    if ( QueryDepthSList(v4) < *((int *)v1 + 3) )
    {
      InterlockedPushEntrySList(v4, ListEntry);
    }
    else
    {
      HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, ListEntry);
      _InterlockedDecrement((volatile signed __int32 *)v1 + 16);
    }
    _InterlockedIncrement((volatile signed __int32 *)v1 + 48);
  }
}

```

## disassembly

```asm
0x18000f8c0  test    rcx, rcx
0x18000f8c3  jz      short locret_18000F93B
0x18000f8c5  mov     [rsp+arg_0], rbx
0x18000f8ca  mov     [rsp+arg_8], rsi
0x18000f8cf  push    rdi
0x18000f8d0  sub     rsp, 20h
0x18000f8d4  mov     rdi, cs:?sm_palloc@CLKRLinearHashTable@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CLKRLinearHashTable::sm_palloc
0x18000f8db  mov     rsi, rcx
0x18000f8de  mov     rbx, [rdi+18h]
0x18000f8e2  call    cs:__imp_GetCurrentThreadId
0x18000f8e8  mov     eax, eax
0x18000f8ea  xor     edx, edx
0x18000f8ec  div     qword ptr [rbx+10h]
0x18000f8f0  mov     r8d, edx
0x18000f8f3  imul    r8, [rbx+8]
0x18000f8f8  mov     rbx, [rbx]
0x18000f8fb  add     rbx, r8
0x18000f8fe  mov     rcx, rbx; ListHead
0x18000f901  call    cs:__imp_QueryDepthSList
0x18000f907  movzx   eax, ax
0x18000f90a  cmp     eax, [rdi+0Ch]
0x18000f90d  jl      short loc_18000F93C
0x18000f90f  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000f916  mov     r8, rsi; lpMem
0x18000f919  xor     edx, edx; dwFlags
0x18000f91b  call    cs:__imp_HeapFree
0x18000f921  lock dec dword ptr [rdi+40h]
0x18000f925  lock inc dword ptr [rdi+0C0h]
0x18000f92c  mov     rbx, [rsp+28h+arg_0]
0x18000f931  mov     rsi, [rsp+28h+arg_8]
0x18000f936  add     rsp, 20h
0x18000f93a  pop     rdi
0x18000f93b  retn
0x18000f93c  mov     rdx, rsi; ListEntry
0x18000f93f  mov     rcx, rbx; ListHead
0x18000f942  call    cs:__imp_InterlockedPushEntrySList
0x18000f948  jmp     short loc_18000F925
```
