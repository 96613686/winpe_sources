# _dynamic_atexit_destructor_for__ThreadList__

- ea: `0x180006dc0`
- end: `0x180006dcc`
- name: `_dynamic_atexit_destructor_for__ThreadList__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006dd4`

## pseudocode

```c
void dynamic_atexit_destructor_for__ThreadList__()
{
  std::list<PIXEventsThreadInfo>::_Tidy((void **)&qword_18001E8A0);
}

```

## disassembly

```asm
0x180006dc0  lea     rcx, qword_18001E8A0
0x180006dc7  jmp     ?_Tidy@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@AEAAXXZ; std::list<PIXEventsThreadInfo>::_Tidy(void)
```
