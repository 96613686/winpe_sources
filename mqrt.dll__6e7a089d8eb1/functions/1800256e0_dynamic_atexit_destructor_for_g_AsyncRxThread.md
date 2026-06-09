# _dynamic_atexit_destructor_for__g_AsyncRxThread__

- ea: `0x1800256e0`
- end: `0x1800256f7`
- name: `_dynamic_atexit_destructor_for__g_AsyncRxThread__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800256eb`
- `KERNEL32!DeleteCriticalSection` at `0x1800256eb`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_AsyncRxThread__()
{
  DeleteCriticalSection(&g_AsyncRxThread);
}

```

## disassembly

```asm
0x1800256e0  sub     rsp, 28h
0x1800256e4  lea     rcx, ?g_AsyncRxThread@@3VCAsyncRxThread@@A; lpCriticalSection
0x1800256eb  call    cs:__imp_DeleteCriticalSection
0x1800256f1  nop
0x1800256f2  add     rsp, 28h
0x1800256f6  retn
```
