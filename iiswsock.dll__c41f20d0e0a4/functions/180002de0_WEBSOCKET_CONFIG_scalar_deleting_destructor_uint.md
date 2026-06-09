# WEBSOCKET_CONFIG::`scalar deleting destructor'(uint)

- ea: `0x180002de0`
- end: `0x180002e06`
- name: `??_GWEBSOCKET_CONFIG@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(WEBSOCKET_CONFIG *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`
- `0x180002de0`

## pseudocode

```c
WEBSOCKET_CONFIG *__fastcall WEBSOCKET_CONFIG::`scalar deleting destructor'(WEBSOCKET_CONFIG *this, char a2)
{
  *(_QWORD *)this = &WEBSOCKET_CONFIG::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002de0  push    rbx
0x180002de2  sub     rsp, 20h
0x180002de6  lea     rax, ??_7WEBSOCKET_CONFIG@@6B@; const WEBSOCKET_CONFIG::`vftable'
0x180002ded  mov     rbx, rcx
0x180002df0  mov     [rcx], rax
0x180002df3  test    dl, 1
0x180002df6  jz      short loc_180002DFD
0x180002df8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dfd  mov     rax, rbx
0x180002e00  add     rsp, 20h
0x180002e04  pop     rbx
0x180002e05  retn
```
