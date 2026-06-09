# SHashFreeLock

- ea: `0x14005c730`
- end: `0x14005c76a`
- name: `SHashFreeLock`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005c739`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14005c739`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005c75e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005c745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005c745`

## pseudocode

```c
BOOL __fastcall SHashFreeLock(struct _RTL_CRITICAL_SECTION *a1)
{
  HANDLE ProcessHeap; // rax

  DeleteCriticalSection(a1);
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x14005c730  push    rbx
0x14005c732  sub     rsp, 20h
0x14005c736  mov     rbx, rcx
0x14005c739  call    cs:__imp_DeleteCriticalSection
0x14005c740  nop     dword ptr [rax+rax+00h]
0x14005c745  call    cs:__imp_GetProcessHeap
0x14005c74c  nop     dword ptr [rax+rax+00h]
0x14005c751  mov     r8, rbx
0x14005c754  xor     edx, edx
0x14005c756  mov     rcx, rax
0x14005c759  add     rsp, 20h
0x14005c75d  pop     rbx
0x14005c75e  jmp     cs:__imp_HeapFree
```
