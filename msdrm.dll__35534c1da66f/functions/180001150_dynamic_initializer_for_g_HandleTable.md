# _dynamic_initializer_for__g_HandleTable__

- ea: `0x180001150`
- end: `0x180001187`
- name: `_dynamic_initializer_for__g_HandleTable__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800030a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000115b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000115b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001161`

## pseudocode

```c
int dynamic_initializer_for__g_HandleTable__()
{
  DWORD CurrentProcessId; // eax

  InitializeCriticalSection(&CriticalSection);
  CurrentProcessId = GetCurrentProcessId();
  dword_180084DF0 = 0;
  LODWORD(dword_180084DEC) = CurrentProcessId;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_HandleTable__);
}

```

## disassembly

```asm
0x180001150  sub     rsp, 28h
0x180001154  lea     rcx, CriticalSection; lpCriticalSection
0x18000115b  call    cs:__imp_InitializeCriticalSection
0x180001161  call    cs:__imp_GetCurrentProcessId
0x180001167  lea     rcx, _dynamic_atexit_destructor_for__g_HandleTable__
0x18000116e  mov     cs:dword_180084DF0, 0
0x180001178  mov     cs:dword_180084DEC, eax
0x18000117e  add     rsp, 28h
0x180001182  jmp     atexit
```
