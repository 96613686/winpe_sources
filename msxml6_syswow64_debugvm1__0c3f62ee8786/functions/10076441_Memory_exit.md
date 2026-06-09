# Memory_exit()

- ea: `0x10076441`
- end: `0x1007647e`
- name: `_Memory_exit@0`
- size: `61`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1005b380`

## callees

- `0x10076441`
- `0x100764a1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10076454`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10076454`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1007646d`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1007646d`

## pseudocode

```c
HANDLE __stdcall Memory_exit()
{
  HANDLE result; // eax

  TlsExit();
  if ( failure_tracing::_fInitialized )
    DeleteCriticalSection(&failure_tracing::_cs);
  result = g_hMsxmlHeap;
  if ( g_hMsxmlHeap )
  {
    if ( !g_fProcessShutdown )
      result = (HANDLE)HeapDestroy(g_hMsxmlHeap);
    g_hMsxmlHeap = 0;
  }
  return result;
}

```

## disassembly

```asm
0x10076441  call    ?TlsExit@@YGXXZ; TlsExit(void)
0x10076446  cmp     ?_fInitialized@failure_tracing@@1_NA, 0; bool failure_tracing::_fInitialized
0x1007644d  jz      short loc_1007645A
0x1007644f  push    offset ?_cs@failure_tracing@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10076454  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1007645a  mov     eax, ?g_hMsxmlHeap@@3PAXA; void * g_hMsxmlHeap
0x1007645f  test    eax, eax
0x10076461  jz      short locret_1007647D
0x10076463  cmp     ?g_fProcessShutdown@@3HA, 0; int g_fProcessShutdown
0x1007646a  jnz     short loc_10076473
0x1007646c  push    eax; hHeap
0x1007646d  call    ds:__imp__HeapDestroy@4; HeapDestroy(x)
0x10076473  mov     ?g_hMsxmlHeap@@3PAXA, 0; void * g_hMsxmlHeap
0x1007647d  retn
```
