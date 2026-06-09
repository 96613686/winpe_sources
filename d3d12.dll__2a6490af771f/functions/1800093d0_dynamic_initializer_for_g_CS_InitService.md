# _dynamic_initializer_for__g_CS_InitService__

- ea: `0x1800093d0`
- end: `0x1800093f1`
- name: `_dynamic_initializer_for__g_CS_InitService__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b7c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800093db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800093db`

## pseudocode

```c
int dynamic_initializer_for__g_CS_InitService__()
{
  InitializeCriticalSection(&g_CS_InitService);
  return atexit(dynamic_atexit_destructor_for__g_CS_InitService__);
}

```

## disassembly

```asm
0x1800093d0  sub     rsp, 28h
0x1800093d4  lea     rcx, ?g_CS_InitService@@3VCriticalSection@@A; lpCriticalSection
0x1800093db  call    cs:__imp_InitializeCriticalSection
0x1800093e1  lea     rcx, _dynamic_atexit_destructor_for__g_CS_InitService__
0x1800093e8  add     rsp, 28h
0x1800093ec  jmp     atexit
```
