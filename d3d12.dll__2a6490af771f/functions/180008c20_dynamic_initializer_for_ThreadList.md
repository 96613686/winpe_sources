# _dynamic_initializer_for__ThreadList__

- ea: `0x180008c20`
- end: `0x180008c39`
- name: `_dynamic_initializer_for__ThreadList__`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008c40`
- `0x18000b7c0`

## pseudocode

```c
int dynamic_initializer_for__ThreadList__()
{
  std::list<PIXEventsThreadInfo>::_Alloc_sentinel_and_proxy();
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__ThreadList__);
}

```

## disassembly

```asm
0x180008c20  sub     rsp, 28h
0x180008c24  call    ?_Alloc_sentinel_and_proxy@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@AEAAXXZ; std::list<PIXEventsThreadInfo>::_Alloc_sentinel_and_proxy(void)
0x180008c29  lea     rcx, _dynamic_atexit_destructor_for__ThreadList__
0x180008c30  add     rsp, 28h
0x180008c34  jmp     atexit
```
