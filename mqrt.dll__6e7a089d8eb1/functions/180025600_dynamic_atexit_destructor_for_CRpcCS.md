# _dynamic_atexit_destructor_for__CRpcCS__

- ea: `0x180025600`
- end: `0x180025617`
- name: `_dynamic_atexit_destructor_for__CRpcCS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002560b`
- `KERNEL32!DeleteCriticalSection` at `0x18002560b`

## pseudocode

```c
void dynamic_atexit_destructor_for__CRpcCS__()
{
  DeleteCriticalSection(&CRpcCS);
}

```

## disassembly

```asm
0x180025600  sub     rsp, 28h
0x180025604  lea     rcx, ?CRpcCS@@3VCCriticalSection@@A; lpCriticalSection
0x18002560b  call    cs:__imp_DeleteCriticalSection
0x180025611  nop
0x180025612  add     rsp, 28h
0x180025616  retn
```
