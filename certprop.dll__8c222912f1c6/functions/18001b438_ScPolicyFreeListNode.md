# ScPolicyFreeListNode

- ea: `0x18001b438`
- end: `0x18001b48a`
- name: `ScPolicyFreeListNode`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001aee0`
- `0x18001af6c`
- `0x18001b278`
- `0x18001b808`
- `0x18001b9b0`

## callees

- `0x18001b438`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b46c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b46c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b483`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b445`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b454`

## pseudocode

```c
BOOL __fastcall ScPolicyFreeListNode(__int64 a1)
{
  void *v2; // rcx
  void *v3; // r8

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v2 = *(void **)(a1 + 56);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)(a1 + 64);
  if ( v3 )
    HeapFree(g_hScPolicyHeap, 0, v3);
  return HeapFree(g_hScPolicyHeap, 0, (LPVOID)a1);
}

```

## disassembly

```asm
0x18001b438  push    rbx
0x18001b43a  sub     rsp, 20h
0x18001b43e  mov     rbx, rcx
0x18001b441  add     rcx, 8; lpCriticalSection
0x18001b445  call    cs:__imp_DeleteCriticalSection
0x18001b44b  mov     rcx, [rbx+38h]; hObject
0x18001b44f  test    rcx, rcx
0x18001b452  jz      short loc_18001B45A
0x18001b454  call    cs:__imp_CloseHandle
0x18001b45a  mov     r8, [rbx+40h]; lpMem
0x18001b45e  test    r8, r8
0x18001b461  jz      short loc_18001B472
0x18001b463  mov     rcx, cs:g_hScPolicyHeap; hHeap
0x18001b46a  xor     edx, edx; dwFlags
0x18001b46c  call    cs:__imp_HeapFree
0x18001b472  mov     rcx, cs:g_hScPolicyHeap
0x18001b479  mov     r8, rbx
0x18001b47c  xor     edx, edx
0x18001b47e  add     rsp, 20h
0x18001b482  pop     rbx
0x18001b483  jmp     cs:__imp_HeapFree
```
