# mainCRTStartup

- ea: `0x1400012f0`
- end: `0x140001302`
- name: `mainCRTStartup`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001140`
- `0x140001524`

## pseudocode

```c
int mainCRTStartup()
{
  _security_init_cookie();
  return _mainCRTStartup();
}

```

## disassembly

```asm
0x1400012f0  sub     rsp, 28h
0x1400012f4  call    __security_init_cookie
0x1400012f9  add     rsp, 28h
0x1400012fd  jmp     __mainCRTStartup
```
