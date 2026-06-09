# _PackageSecurity::CryptWrapper_::_1_::dtor$9

- ea: `0x1800188ad`
- end: `0x1800188b9`
- name: `_PackageSecurity::CryptWrapper_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005fec`

## pseudocode

```c
void __fastcall PackageSecurity::CryptWrapper_::_1_::dtor_9(__int64 a1, void **a2)
{
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>(
    a2 + 16,
    (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x1800188ad  lea     rcx, [rdx+80h]
0x1800188b4  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::~unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>(void)
```
