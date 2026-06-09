# CLKRLinearHashTable::operator delete(void *)

- ea: `0x180010c20`
- end: `0x180010cc7`
- name: `??3CLKRLinearHashTable@@SAXPEAX@Z`
- size: `167`
- prototype: `void __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180010bf0`

## callees

- `0x180010c20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c8b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180010c6b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180010c6b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010cb9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010cb9`

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
0x180010c20  test    rcx, rcx
0x180010c23  jz      locret_180010CB1
0x180010c29  mov     [rsp+arg_0], rbx
0x180010c2e  mov     [rsp+arg_8], rsi
0x180010c33  push    rdi
0x180010c34  sub     rsp, 20h
0x180010c38  mov     rdi, cs:?sm_palloc@CLKRLinearHashTable@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CLKRLinearHashTable::sm_palloc
0x180010c3f  mov     rsi, rcx
0x180010c42  mov     rbx, [rdi+18h]
0x180010c46  call    cs:__imp_GetCurrentThreadId
0x180010c4d  nop     dword ptr [rax+rax+00h]
0x180010c52  mov     eax, eax
0x180010c54  xor     edx, edx
0x180010c56  div     qword ptr [rbx+10h]
0x180010c5a  mov     r8d, edx
0x180010c5d  imul    r8, [rbx+8]
0x180010c62  mov     rbx, [rbx]
0x180010c65  add     rbx, r8
0x180010c68  mov     rcx, rbx; ListHead
0x180010c6b  call    cs:__imp_QueryDepthSList
0x180010c72  nop     dword ptr [rax+rax+00h]
0x180010c77  movzx   eax, ax
0x180010c7a  cmp     eax, [rdi+0Ch]
0x180010c7d  jl      short loc_180010CB3
0x180010c7f  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180010c86  mov     r8, rsi; lpMem
0x180010c89  xor     edx, edx; dwFlags
0x180010c8b  call    cs:__imp_HeapFree
0x180010c92  nop     dword ptr [rax+rax+00h]
0x180010c97  lock dec dword ptr [rdi+40h]
0x180010c9b  lock inc dword ptr [rdi+0C0h]
0x180010ca2  mov     rbx, [rsp+28h+arg_0]
0x180010ca7  mov     rsi, [rsp+28h+arg_8]
0x180010cac  add     rsp, 20h
0x180010cb0  pop     rdi
0x180010cb1  retn
0x180010cb3  mov     rdx, rsi; ListEntry
0x180010cb6  mov     rcx, rbx; ListHead
0x180010cb9  call    cs:__imp_InterlockedPushEntrySList
0x180010cc0  nop     dword ptr [rax+rax+00h]
0x180010cc5  jmp     short loc_180010C9B
```
