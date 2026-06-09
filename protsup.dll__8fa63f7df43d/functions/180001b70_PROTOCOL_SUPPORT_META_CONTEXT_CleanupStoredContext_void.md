# PROTOCOL_SUPPORT_META_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001b70`
- end: `0x180001b90`
- name: `?CleanupStoredContext@PROTOCOL_SUPPORT_META_CONTEXT@@UEAAXXZ`
- size: `32`
- prototype: `void __fastcall(PROTOCOL_SUPPORT_META_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b70`
- `0x180001ba0`
- `0x180001dc0`

## pseudocode

```c
void __fastcall PROTOCOL_SUPPORT_META_CONTEXT::CleanupStoredContext(PROTOCOL_SUPPORT_META_CONTEXT *this)
{
  if ( this )
  {
    PROTOCOL_SUPPORT_META_CONTEXT::~PROTOCOL_SUPPORT_META_CONTEXT(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180001b70  test    rcx, rcx
0x180001b73  jz      short locret_180001B8F
0x180001b75  push    rbx
0x180001b76  sub     rsp, 20h
0x180001b7a  mov     rbx, rcx
0x180001b7d  call    ??1PROTOCOL_SUPPORT_META_CONTEXT@@QEAA@XZ
0x180001b82  mov     rcx, rbx; Block
0x180001b85  call    ??3@YAXPEAX@Z
0x180001b8a  add     rsp, 20h
0x180001b8e  pop     rbx
0x180001b8f  retn
```
