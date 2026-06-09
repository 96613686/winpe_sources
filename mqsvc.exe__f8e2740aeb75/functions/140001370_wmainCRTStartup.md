# wmainCRTStartup

- ea: `0x140001370`
- end: `0x140001382`
- name: `wmainCRTStartup`
- size: `18`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400011c0`
- `0x1400015b4`

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
0x140001370  sub     rsp, 28h
0x140001374  call    __security_init_cookie
0x140001379  add     rsp, 28h
0x14000137d  jmp     __wmainCRTStartup
```
