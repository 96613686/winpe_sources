# wmainCRTStartup

- ea: `0x140001310`
- end: `0x140001322`
- name: `wmainCRTStartup`
- size: `18`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001160`
- `0x140001544`

## pseudocode

```c
__int64 wmainCRTStartup()
{
  _security_init_cookie();
  return _wmainCRTStartup();
}

```

## disassembly

```asm
0x140001310  sub     rsp, 28h
0x140001314  call    __security_init_cookie
0x140001319  add     rsp, 28h
0x14000131d  jmp     __wmainCRTStartup
```
