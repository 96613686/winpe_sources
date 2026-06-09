# Memory_exit

- ea: `0x1800d6ec8`
- end: `0x1800d6f1f`
- name: `Memory_exit`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800b4bd0`

## callees

- `0x1800d6ec8`
- `0x1800d6f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d6ee1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d6ee1`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800d6f02`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800d6f02`

## pseudocode

```c
void Memory_exit()
{
  TlsExit();
  if ( failure_tracing::_fInitialized )
    DeleteCriticalSection(&failure_tracing::_cs);
  if ( g_hMsxmlHeap )
  {
    if ( !g_fProcessShutdown )
      HeapDestroy(g_hMsxmlHeap);
    g_hMsxmlHeap = 0;
  }
}

```

## disassembly

```asm
0x1800d6ec8  sub     rsp, 28h
0x1800d6ecc  call    ?TlsExit@@YAXXZ; TlsExit(void)
0x1800d6ed1  cmp     cs:?_fInitialized@failure_tracing@@1_NA, 0; bool failure_tracing::_fInitialized
0x1800d6ed8  jz      short loc_1800D6EED
0x1800d6eda  lea     rcx, ?_cs@failure_tracing@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d6ee1  call    cs:__imp_DeleteCriticalSection
0x1800d6ee8  nop     dword ptr [rax+rax+00h]
0x1800d6eed  mov     rcx, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x1800d6ef4  test    rcx, rcx
0x1800d6ef7  jz      short loc_1800D6F19
0x1800d6ef9  cmp     cs:?g_fProcessShutdown@@3HA, 0; int g_fProcessShutdown
0x1800d6f00  jnz     short loc_1800D6F0E
0x1800d6f02  call    cs:__imp_HeapDestroy
0x1800d6f09  nop     dword ptr [rax+rax+00h]
0x1800d6f0e  mov     cs:?g_hMsxmlHeap@@3PEAXEA, 0; void * g_hMsxmlHeap
0x1800d6f19  add     rsp, 28h
0x1800d6f1d  retn
```
