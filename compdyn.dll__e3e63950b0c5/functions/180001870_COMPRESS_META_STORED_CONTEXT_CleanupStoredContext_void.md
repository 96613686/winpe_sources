# COMPRESS_META_STORED_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001870`
- end: `0x180001887`
- name: `?CleanupStoredContext@COMPRESS_META_STORED_CONTEXT@@UEAAXXZ`
- size: `23`
- prototype: `void __fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001870`
- `0x180008010`

## pseudocode

```c
void __fastcall COMPRESS_META_STORED_CONTEXT::CleanupStoredContext(COMPRESS_META_STORED_CONTEXT *this)
{
  if ( this )
    (*(void (__fastcall **)(COMPRESS_META_STORED_CONTEXT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
}

```

## disassembly

```asm
0x180001870  test    rcx, rcx
0x180001873  jz      short locret_180001886
0x180001875  mov     rax, [rcx]
0x180001878  mov     edx, 1
0x18000187d  mov     rax, [rax+8]
0x180001881  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001886  retn
```
