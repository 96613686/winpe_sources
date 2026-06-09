# NatCleanupDynamicRedirect

- ea: `0x18004bff8`
- end: `0x18004c033`
- name: `NatCleanupDynamicRedirect`
- size: `59`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031970`
- `0x180031a40`
- `0x180031c50`
- `0x180031e20`
- `0x1800573a0`

## callees

- `0x18004bff8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c02c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c013`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c013`
- `ntdll!NtClose` at `0x18004c00a`
- `ntdll!NtClose` at `0x18004c00a`

## pseudocode

```c
BOOL __fastcall NatCleanupDynamicRedirect(LPCRITICAL_SECTION lpCriticalSection)
{
  void *v2; // rcx
  HANDLE ProcessHeap; // rax

  v2 = *(void **)&lpCriticalSection[1].LockCount;
  if ( v2 )
    NtClose(v2);
  DeleteCriticalSection(lpCriticalSection);
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, lpCriticalSection);
}

```

## disassembly

```asm
0x18004bff8  push    rbx
0x18004bffa  sub     rsp, 20h
0x18004bffe  mov     rbx, rcx
0x18004c001  mov     rcx, [rcx+30h]; Handle
0x18004c005  test    rcx, rcx
0x18004c008  jz      short loc_18004C010
0x18004c00a  call    cs:__imp_NtClose
0x18004c010  mov     rcx, rbx; lpCriticalSection
0x18004c013  call    cs:__imp_DeleteCriticalSection
0x18004c019  call    cs:__imp_GetProcessHeap
0x18004c01f  mov     r8, rbx
0x18004c022  xor     edx, edx
0x18004c024  mov     rcx, rax
0x18004c027  add     rsp, 20h
0x18004c02b  pop     rbx
0x18004c02c  jmp     cs:__imp_HeapFree
```
