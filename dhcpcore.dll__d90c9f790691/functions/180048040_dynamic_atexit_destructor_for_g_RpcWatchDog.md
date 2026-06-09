# _dynamic_atexit_destructor_for__g_RpcWatchDog__

- ea: `0x180048040`
- end: `0x18004804e`
- name: `_dynamic_atexit_destructor_for__g_RpcWatchDog__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048047`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_RpcWatchDog__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180048040  lea     rcx, CriticalSection
0x180048047  jmp     cs:__imp_DeleteCriticalSection
```
