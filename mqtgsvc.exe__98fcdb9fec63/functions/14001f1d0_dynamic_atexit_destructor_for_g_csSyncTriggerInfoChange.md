# _dynamic_atexit_destructor_for__g_csSyncTriggerInfoChange__

- ea: `0x14001f1d0`
- end: `0x14001f1e7`
- name: `_dynamic_atexit_destructor_for__g_csSyncTriggerInfoChange__`
- size: `23`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001f1db`
- `KERNEL32!DeleteCriticalSection` at `0x14001f1db`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csSyncTriggerInfoChange__()
{
  DeleteCriticalSection(&g_csSyncTriggerInfoChange);
}

```

## disassembly

```asm
0x14001f1d0  sub     rsp, 28h
0x14001f1d4  lea     rcx, ?g_csSyncTriggerInfoChange@@3VCCriticalSection@@A; lpCriticalSection
0x14001f1db  call    cs:__imp_DeleteCriticalSection
0x14001f1e1  nop
0x14001f1e2  add     rsp, 28h
0x14001f1e6  retn
```
