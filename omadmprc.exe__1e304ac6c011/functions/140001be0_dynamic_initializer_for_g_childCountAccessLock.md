# _dynamic_initializer_for__g_childCountAccessLock__

- ea: `0x140001be0`
- end: `0x140001c0c`
- name: `_dynamic_initializer_for__g_childCountAccessLock__`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140001bf0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140001bf0`

## pseudocode

```c
int dynamic_initializer_for__g_childCountAccessLock__()
{
  InitializeCriticalSectionEx(&stru_140024310, 0, 0);
  return atexit(dynamic_atexit_destructor_for__g_childCountAccessLock__);
}

```

## disassembly

```asm
0x140001be0  sub     rsp, 28h
0x140001be4  xor     r8d, r8d; Flags
0x140001be7  lea     rcx, stru_140024310; lpCriticalSection
0x140001bee  xor     edx, edx; dwSpinCount
0x140001bf0  call    cs:__imp_InitializeCriticalSectionEx
0x140001bf7  nop     dword ptr [rax+rax+00h]
0x140001bfc  lea     rcx, _dynamic_atexit_destructor_for__g_childCountAccessLock__
0x140001c03  add     rsp, 28h
0x140001c07  jmp     atexit
```
