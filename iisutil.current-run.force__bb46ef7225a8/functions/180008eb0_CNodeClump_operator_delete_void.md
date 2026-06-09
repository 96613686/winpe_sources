# CNodeClump::operator delete(void *)

- ea: `0x180008eb0`
- end: `0x180008f3a`
- name: `??3CNodeClump@@SAXPEAX@Z`
- size: `138`
- prototype: `void __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800049c0`
- `0x180007750`
- `0x180008220`
- `0x180008980`
- `0x180008f40`
- `0x18000a110`
- `0x18000a400`
- `0x18000a9d0`

## callees

- `0x180008eb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ed2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f0b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180008ef1`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180008ef1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180008f32`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180008f32`

## pseudocode

```c
void __fastcall CNodeClump::operator delete(PSLIST_ENTRY ListEntry)
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
}

```

## disassembly

```asm
0x180008eb0  test    rcx, rcx
0x180008eb3  jz      short locret_180008F2B
0x180008eb5  push    rsi
0x180008eb6  sub     rsp, 20h
0x180008eba  mov     [rsp+28h+arg_0], rbx
0x180008ebf  mov     rsi, rcx
0x180008ec2  mov     rbx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x180008ec9  mov     [rsp+28h+arg_8], rdi
0x180008ece  mov     rdi, [rbx+18h]
0x180008ed2  call    cs:__imp_GetCurrentThreadId
0x180008ed8  mov     eax, eax
0x180008eda  xor     edx, edx
0x180008edc  div     qword ptr [rdi+10h]
0x180008ee0  mov     r8d, edx
0x180008ee3  imul    r8, [rdi+8]
0x180008ee8  mov     rdi, [rdi]
0x180008eeb  add     rdi, r8
0x180008eee  mov     rcx, rdi; ListHead
0x180008ef1  call    cs:__imp_QueryDepthSList
0x180008ef7  movzx   eax, ax
0x180008efa  cmp     eax, [rbx+0Ch]
0x180008efd  jl      short loc_180008F2C
0x180008eff  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180008f06  mov     r8, rsi; lpMem
0x180008f09  xor     edx, edx; dwFlags
0x180008f0b  call    cs:__imp_HeapFree
0x180008f11  lock dec dword ptr [rbx+40h]
0x180008f15  lock inc dword ptr [rbx+0C0h]
0x180008f1c  mov     rdi, [rsp+28h+arg_8]
0x180008f21  mov     rbx, [rsp+28h+arg_0]
0x180008f26  add     rsp, 20h
0x180008f2a  pop     rsi
0x180008f2b  retn
0x180008f2c  mov     rdx, rsi; ListEntry
0x180008f2f  mov     rcx, rdi; ListHead
0x180008f32  call    cs:__imp_InterlockedPushEntrySList
0x180008f38  jmp     short loc_180008F15
```
