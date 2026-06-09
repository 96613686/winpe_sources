# CLKRLinearHashTable::_FreeNodeClump(CNodeClump *)

- ea: `0x18000d8d0`
- end: `0x18000d95d`
- name: `?_FreeNodeClump@CLKRLinearHashTable@@CA_NPEAVCNodeClump@@@Z`
- size: `141`
- prototype: `bool __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d92c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d92c`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000d912`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000d912`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000d955`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000d955`

## pseudocode

```c
char __fastcall CLKRLinearHashTable::_FreeNodeClump(PSLIST_ENTRY ListEntry)
{
  ALLOC_CACHE_HANDLER *v2; // rbx
  _QWORD *v3; // rdi
  union _SLIST_HEADER *v4; // rdi

  if ( ListEntry )
  {
    v2 = CNodeClump::sm_palloc;
    v3 = (_QWORD *)*((_QWORD *)CNodeClump::sm_palloc + 3);
    v4 = (union _SLIST_HEADER *)(v3[1] * ((unsigned __int64)GetCurrentThreadId() % v3[2]) + *v3);
    if ( QueryDepthSList(v4) < *((int *)v2 + 3) )
    {
      InterlockedPushEntrySList(v4, ListEntry);
    }
    else
    {
      HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, ListEntry);
      _InterlockedDecrement((volatile signed __int32 *)v2 + 16);
    }
    _InterlockedIncrement((volatile signed __int32 *)v2 + 48);
  }
  return 1;
}

```

## disassembly

```asm
0x18000d8d0  push    rsi
0x18000d8d2  sub     rsp, 20h
0x18000d8d6  mov     rsi, rcx
0x18000d8d9  test    rcx, rcx
0x18000d8dc  jz      short loc_18000D947
0x18000d8de  mov     [rsp+28h+arg_0], rbx
0x18000d8e3  mov     rbx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000d8ea  mov     [rsp+28h+arg_8], rdi
0x18000d8ef  mov     rdi, [rbx+18h]
0x18000d8f3  call    cs:__imp_GetCurrentThreadId
0x18000d8f9  mov     eax, eax
0x18000d8fb  xor     edx, edx
0x18000d8fd  div     qword ptr [rdi+10h]
0x18000d901  mov     r8d, edx
0x18000d904  imul    r8, [rdi+8]
0x18000d909  mov     rdi, [rdi]
0x18000d90c  add     rdi, r8
0x18000d90f  mov     rcx, rdi; ListHead
0x18000d912  call    cs:__imp_QueryDepthSList
0x18000d918  movzx   eax, ax
0x18000d91b  cmp     eax, [rbx+0Ch]
0x18000d91e  jl      short loc_18000D94F
0x18000d920  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000d927  mov     r8, rsi; lpMem
0x18000d92a  xor     edx, edx; dwFlags
0x18000d92c  call    cs:__imp_HeapFree
0x18000d932  lock dec dword ptr [rbx+40h]
0x18000d936  lock inc dword ptr [rbx+0C0h]
0x18000d93d  mov     rdi, [rsp+28h+arg_8]
0x18000d942  mov     rbx, [rsp+28h+arg_0]
0x18000d947  mov     al, 1
0x18000d949  add     rsp, 20h
0x18000d94d  pop     rsi
0x18000d94e  retn
0x18000d94f  mov     rdx, rsi; ListEntry
0x18000d952  mov     rcx, rdi; ListHead
0x18000d955  call    cs:__imp_InterlockedPushEntrySList
0x18000d95b  jmp     short loc_18000D936
```
