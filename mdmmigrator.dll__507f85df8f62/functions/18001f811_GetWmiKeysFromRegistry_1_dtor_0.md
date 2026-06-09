# _GetWmiKeysFromRegistry_::_1_::dtor$0

- ea: `0x18001f811`
- end: `0x18001f81d`
- name: `_GetWmiKeysFromRegistry_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d9d0`

## pseudocode

```c
void __fastcall GetWmiKeysFromRegistry_::_1_::dtor_0(__int64 a1, void **a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(a2 + 9, (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x18001f811  lea     rcx, [rdx+48h]
0x18001f818  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
