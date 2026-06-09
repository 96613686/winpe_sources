# mainCRTStartup

- ea: `0x140001340`
- end: `0x140001352`
- name: `mainCRTStartup`
- size: `18`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001190`
- `0x140001584`

## pseudocode

```c
__int64 mainCRTStartup()
{
  _security_init_cookie();
  return _mainCRTStartup();
}

```

## disassembly

```asm
0x140001340  sub     rsp, 28h
0x140001344  call    __security_init_cookie
0x140001349  add     rsp, 28h
0x14000134d  jmp     __mainCRTStartup
```
