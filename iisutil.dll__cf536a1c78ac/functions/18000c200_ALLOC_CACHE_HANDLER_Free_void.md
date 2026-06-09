# ALLOC_CACHE_HANDLER::Free(void *)

- ea: `0x18000c200`
- end: `0x18000c29e`
- name: `?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z`
- size: `158`
- prototype: `int(ALLOC_CACHE_HANDLER *__hidden this, void *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008470`
- `0x18000a180`
- `0x18000c2b0`
- `0x18002cfd0`
- `0x18002d1c0`
- `0x18002d250`

## callees

- `0x18000c200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c219`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c25d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c25d`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000c23d`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000c23d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000c290`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000c290`

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
0x18000c200  mov     [rsp+arg_0], rbx
0x18000c205  mov     [rsp+arg_8], rsi
0x18000c20a  push    rdi
0x18000c20b  sub     rsp, 20h
0x18000c20f  mov     rdi, [rcx+18h]
0x18000c213  mov     rsi, rdx
0x18000c216  mov     rbx, rcx
0x18000c219  call    cs:__imp_GetCurrentThreadId
0x18000c220  nop     dword ptr [rax+rax+00h]
0x18000c225  mov     eax, eax
0x18000c227  xor     edx, edx
0x18000c229  div     qword ptr [rdi+10h]
0x18000c22d  mov     ecx, edx
0x18000c22f  imul    rcx, [rdi+8]
0x18000c234  mov     rdi, [rdi]
0x18000c237  add     rdi, rcx
0x18000c23a  mov     rcx, rdi; ListHead
0x18000c23d  call    cs:__imp_QueryDepthSList
0x18000c244  nop     dword ptr [rax+rax+00h]
0x18000c249  movzx   eax, ax
0x18000c24c  cmp     eax, [rbx+0Ch]
0x18000c24f  jl      short loc_18000C28A
0x18000c251  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000c258  mov     r8, rsi; lpMem
0x18000c25b  xor     edx, edx; dwFlags
0x18000c25d  call    cs:__imp_HeapFree
0x18000c264  nop     dword ptr [rax+rax+00h]
0x18000c269  lock dec dword ptr [rbx+40h]
0x18000c26d  lock inc dword ptr [rbx+0C0h]
0x18000c274  mov     rbx, [rsp+28h+arg_0]
0x18000c279  mov     eax, 1
0x18000c27e  mov     rsi, [rsp+28h+arg_8]
0x18000c283  add     rsp, 20h
0x18000c287  pop     rdi
0x18000c288  retn
0x18000c28a  mov     rdx, rsi; ListEntry
0x18000c28d  mov     rcx, rdi; ListHead
0x18000c290  call    cs:__imp_InterlockedPushEntrySList
0x18000c297  nop     dword ptr [rax+rax+00h]
0x18000c29c  jmp     short loc_18000C26D
```
