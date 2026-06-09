# CLKRLinearHashTable::_FreeNodeClump(CNodeClump *)

- ea: `0x18000e900`
- end: `0x18000e9a6`
- name: `?_FreeNodeClump@CLKRLinearHashTable@@CA_NPEAVCNodeClump@@@Z`
- size: `166`
- prototype: `bool __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e900`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e923`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e968`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e968`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000e948`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000e948`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e998`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e998`

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
0x18000e900  push    rsi
0x18000e902  sub     rsp, 20h
0x18000e906  mov     rsi, rcx
0x18000e909  test    rcx, rcx
0x18000e90c  jz      short loc_18000E989
0x18000e90e  mov     [rsp+28h+arg_0], rbx
0x18000e913  mov     rbx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x18000e91a  mov     [rsp+28h+arg_8], rdi
0x18000e91f  mov     rdi, [rbx+18h]
0x18000e923  call    cs:__imp_GetCurrentThreadId
0x18000e92a  nop     dword ptr [rax+rax+00h]
0x18000e92f  mov     eax, eax
0x18000e931  xor     edx, edx
0x18000e933  div     qword ptr [rdi+10h]
0x18000e937  mov     r8d, edx
0x18000e93a  imul    r8, [rdi+8]
0x18000e93f  mov     rdi, [rdi]
0x18000e942  add     rdi, r8
0x18000e945  mov     rcx, rdi; ListHead
0x18000e948  call    cs:__imp_QueryDepthSList
0x18000e94f  nop     dword ptr [rax+rax+00h]
0x18000e954  movzx   eax, ax
0x18000e957  cmp     eax, [rbx+0Ch]
0x18000e95a  jl      short loc_18000E992
0x18000e95c  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000e963  mov     r8, rsi; lpMem
0x18000e966  xor     edx, edx; dwFlags
0x18000e968  call    cs:__imp_HeapFree
0x18000e96f  nop     dword ptr [rax+rax+00h]
0x18000e974  lock dec dword ptr [rbx+40h]
0x18000e978  lock inc dword ptr [rbx+0C0h]
0x18000e97f  mov     rdi, [rsp+28h+arg_8]
0x18000e984  mov     rbx, [rsp+28h+arg_0]
0x18000e989  mov     al, 1
0x18000e98b  add     rsp, 20h
0x18000e98f  pop     rsi
0x18000e990  retn
0x18000e992  mov     rdx, rsi; ListEntry
0x18000e995  mov     rcx, rdi; ListHead
0x18000e998  call    cs:__imp_InterlockedPushEntrySList
0x18000e99f  nop     dword ptr [rax+rax+00h]
0x18000e9a4  jmp     short loc_18000E978
```
