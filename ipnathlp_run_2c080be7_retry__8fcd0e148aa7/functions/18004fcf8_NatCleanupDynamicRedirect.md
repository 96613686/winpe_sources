# NatCleanupDynamicRedirect

- ea: `0x18004fcf8`
- end: `0x18004fd4a`
- name: `NatCleanupDynamicRedirect`
- size: `82`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034010`
- `0x1800340f0`
- `0x180034328`
- `0x180034538`
- `0x18005b880`

## callees

- `0x18004fcf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fd25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fd25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fd3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fd19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fd19`
- `ntdll!NtClose` at `0x18004fd0a`
- `ntdll!NtClose` at `0x18004fd0a`

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
0x18004fcf8  push    rbx
0x18004fcfa  sub     rsp, 20h
0x18004fcfe  mov     rbx, rcx
0x18004fd01  mov     rcx, [rcx+30h]; Handle
0x18004fd05  test    rcx, rcx
0x18004fd08  jz      short loc_18004FD16
0x18004fd0a  call    cs:__imp_NtClose
0x18004fd11  nop     dword ptr [rax+rax+00h]
0x18004fd16  mov     rcx, rbx; lpCriticalSection
0x18004fd19  call    cs:__imp_DeleteCriticalSection
0x18004fd20  nop     dword ptr [rax+rax+00h]
0x18004fd25  call    cs:__imp_GetProcessHeap
0x18004fd2c  nop     dword ptr [rax+rax+00h]
0x18004fd31  mov     r8, rbx
0x18004fd34  xor     edx, edx
0x18004fd36  mov     rcx, rax
0x18004fd39  add     rsp, 20h
0x18004fd3d  pop     rbx
0x18004fd3e  jmp     cs:__imp_HeapFree
```
