# COMPRESSION_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001010`
- end: `0x18000101a`
- name: `?CleanupStoredContext@COMPRESSION_CONTEXT@@UEAAXXZ`
- size: `10`
- prototype: `void __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001f10`

## pseudocode

```c
void __fastcall COMPRESSION_CONTEXT::CleanupStoredContext(COMPRESSION_CONTEXT *this)
{
  if ( this )
    COMPRESSION_CONTEXT::~COMPRESSION_CONTEXT(this);
}

```

## disassembly

```asm
0x180001010  test    rcx, rcx
0x180001013  jnz     ??1COMPRESSION_CONTEXT@@QEAA@XZ; COMPRESSION_CONTEXT::~COMPRESSION_CONTEXT(void)
0x180001019  retn
```
