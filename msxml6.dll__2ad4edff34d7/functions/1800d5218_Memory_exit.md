# Memory_exit

- ea: `0x1800d5218`
- end: `0x1800d5262`
- name: `Memory_exit`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800b3600`

## callees

- `0x1800d5218`
- `0x1800d5268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5231`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5231`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800d524c`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800d524c`

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
0x1800d5218  sub     rsp, 28h
0x1800d521c  call    ?TlsExit@@YAXXZ; TlsExit(void)
0x1800d5221  cmp     cs:?_fInitialized@failure_tracing@@1_NA, 0; bool failure_tracing::_fInitialized
0x1800d5228  jz      short loc_1800D5237
0x1800d522a  lea     rcx, ?_cs@failure_tracing@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d5231  call    cs:__imp_DeleteCriticalSection
0x1800d5237  mov     rcx, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x1800d523e  test    rcx, rcx
0x1800d5241  jz      short loc_1800D525D
0x1800d5243  cmp     cs:?g_fProcessShutdown@@3HA, 0; int g_fProcessShutdown
0x1800d524a  jnz     short loc_1800D5252
0x1800d524c  call    cs:__imp_HeapDestroy
0x1800d5252  mov     cs:?g_hMsxmlHeap@@3PEAXEA, 0; void * g_hMsxmlHeap
0x1800d525d  add     rsp, 28h
0x1800d5261  retn
```
