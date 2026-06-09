# _PackageSecurity::CreateCatalog_::_1_::dtor$3

- ea: `0x1800187d5`
- end: `0x1800187e1`
- name: `_PackageSecurity::CreateCatalog_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005fec`

## pseudocode

```c
void __fastcall PackageSecurity::CreateCatalog_::_1_::dtor_3(__int64 a1, void **a2)
{
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>(
    a2 + 18,
    (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x1800187d5  lea     rcx, [rdx+90h]
0x1800187dc  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::~unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>(void)
```
