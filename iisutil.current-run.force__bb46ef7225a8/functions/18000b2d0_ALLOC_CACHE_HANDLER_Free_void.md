# ALLOC_CACHE_HANDLER::Free(void *)

- ea: `0x18000b2d0`
- end: `0x18000b355`
- name: `?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z`
- size: `133`
- prototype: `int(ALLOC_CACHE_HANDLER *__hidden this, void *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007750`
- `0x1800093e0`
- `0x18000b360`
- `0x18002b080`
- `0x18002b260`
- `0x18002b2f0`

## callees

- `0x18000b2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b321`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b321`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000b307`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000b307`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000b34d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000b34d`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::Free(ALLOC_CACHE_HANDLER *this, struct _SLIST_ENTRY *a2)
{
  _QWORD *v2; // rdi
  union _SLIST_HEADER *v5; // rdi

  v2 = (_QWORD *)*((_QWORD *)this + 3);
  v5 = (union _SLIST_HEADER *)(v2[1] * ((unsigned __int64)GetCurrentThreadId() % v2[2]) + *v2);
  if ( QueryDepthSList(v5) < *((int *)this + 3) )
  {
    InterlockedPushEntrySList(v5, a2);
  }
  else
  {
    HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, a2);
    _InterlockedDecrement((volatile signed __int32 *)this + 16);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 48);
  return 1;
}

```

## disassembly

```asm
0x18000b2d0  mov     [rsp+arg_0], rbx
0x18000b2d5  mov     [rsp+arg_8], rsi
0x18000b2da  push    rdi
0x18000b2db  sub     rsp, 20h
0x18000b2df  mov     rdi, [rcx+18h]
0x18000b2e3  mov     rsi, rdx
0x18000b2e6  mov     rbx, rcx
0x18000b2e9  call    cs:__imp_GetCurrentThreadId
0x18000b2ef  mov     eax, eax
0x18000b2f1  xor     edx, edx
0x18000b2f3  div     qword ptr [rdi+10h]
0x18000b2f7  mov     ecx, edx
0x18000b2f9  imul    rcx, [rdi+8]
0x18000b2fe  mov     rdi, [rdi]
0x18000b301  add     rdi, rcx
0x18000b304  mov     rcx, rdi; ListHead
0x18000b307  call    cs:__imp_QueryDepthSList
0x18000b30d  movzx   eax, ax
0x18000b310  cmp     eax, [rbx+0Ch]
0x18000b313  jl      short loc_18000B347
0x18000b315  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000b31c  mov     r8, rsi; lpMem
0x18000b31f  xor     edx, edx; dwFlags
0x18000b321  call    cs:__imp_HeapFree
0x18000b327  lock dec dword ptr [rbx+40h]
0x18000b32b  lock inc dword ptr [rbx+0C0h]
0x18000b332  mov     rbx, [rsp+28h+arg_0]
0x18000b337  mov     eax, 1
0x18000b33c  mov     rsi, [rsp+28h+arg_8]
0x18000b341  add     rsp, 20h
0x18000b345  pop     rdi
0x18000b346  retn
0x18000b347  mov     rdx, rsi; ListEntry
0x18000b34a  mov     rcx, rdi; ListHead
0x18000b34d  call    cs:__imp_InterlockedPushEntrySList
0x18000b353  jmp     short loc_18000B32B
```
