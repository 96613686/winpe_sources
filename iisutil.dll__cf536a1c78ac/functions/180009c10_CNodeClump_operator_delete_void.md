# CNodeClump::operator delete(void *)

- ea: `0x180009c10`
- end: `0x180009cb7`
- name: `??3CNodeClump@@SAXPEAX@Z`
- size: `167`
- prototype: `void __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180005520`
- `0x180008470`
- `0x180008f60`
- `0x1800096d0`
- `0x180009cc0`
- `0x18000a180`
- `0x18000ac30`
- `0x18000b020`
- `0x18000b310`
- `0x18000b840`

## callees

- `0x180009c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c7b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180009c5b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180009c5b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009ca9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009ca9`

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
0x180009c10  test    rcx, rcx
0x180009c13  jz      locret_180009CA1
0x180009c19  push    rsi
0x180009c1a  sub     rsp, 20h
0x180009c1e  mov     [rsp+28h+arg_0], rbx
0x180009c23  mov     rsi, rcx
0x180009c26  mov     rbx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x180009c2d  mov     [rsp+28h+arg_8], rdi
0x180009c32  mov     rdi, [rbx+18h]
0x180009c36  call    cs:__imp_GetCurrentThreadId
0x180009c3d  nop     dword ptr [rax+rax+00h]
0x180009c42  mov     eax, eax
0x180009c44  xor     edx, edx
0x180009c46  div     qword ptr [rdi+10h]
0x180009c4a  mov     r8d, edx
0x180009c4d  imul    r8, [rdi+8]
0x180009c52  mov     rdi, [rdi]
0x180009c55  add     rdi, r8
0x180009c58  mov     rcx, rdi; ListHead
0x180009c5b  call    cs:__imp_QueryDepthSList
0x180009c62  nop     dword ptr [rax+rax+00h]
0x180009c67  movzx   eax, ax
0x180009c6a  cmp     eax, [rbx+0Ch]
0x180009c6d  jl      short loc_180009CA3
0x180009c6f  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180009c76  mov     r8, rsi; lpMem
0x180009c79  xor     edx, edx; dwFlags
0x180009c7b  call    cs:__imp_HeapFree
0x180009c82  nop     dword ptr [rax+rax+00h]
0x180009c87  lock dec dword ptr [rbx+40h]
0x180009c8b  lock inc dword ptr [rbx+0C0h]
0x180009c92  mov     rdi, [rsp+28h+arg_8]
0x180009c97  mov     rbx, [rsp+28h+arg_0]
0x180009c9c  add     rsp, 20h
0x180009ca0  pop     rsi
0x180009ca1  retn
0x180009ca3  mov     rdx, rsi; ListEntry
0x180009ca6  mov     rcx, rdi; ListHead
0x180009ca9  call    cs:__imp_InterlockedPushEntrySList
0x180009cb0  nop     dword ptr [rax+rax+00h]
0x180009cb5  jmp     short loc_180009C8B
```
