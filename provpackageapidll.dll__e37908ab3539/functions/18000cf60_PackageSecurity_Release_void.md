# PackageSecurity::Release(void)

- ea: `0x18000cf60`
- end: `0x18000cf6a`
- name: `?Release@PackageSecurity@@EEAAXXZ`
- size: `10`
- prototype: `void __fastcall(PackageSecurity *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800020a8`

## pseudocode

```c
void __fastcall PackageSecurity::Release(PackageSecurity *this)
{
  operator delete(this, (const struct std::nothrow_t *)8);
}

```

## disassembly

```asm
0x18000cf60  mov     edx, 8; struct std::nothrow_t *
0x18000cf65  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
