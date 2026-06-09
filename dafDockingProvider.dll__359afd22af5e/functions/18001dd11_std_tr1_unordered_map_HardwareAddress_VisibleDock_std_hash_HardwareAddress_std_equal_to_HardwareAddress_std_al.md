# _std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor$1

- ea: `0x18001dd11`
- end: `0x18001dd1d`
- name: `_std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800183d4`

## pseudocode

```c
void __fastcall std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  std::pair<HardwareAddress const,VisibleDock>::~pair<HardwareAddress const,VisibleDock>(a2 + 48);
}

```

## disassembly

```asm
0x18001dd11  lea     rcx, [rdx+30h]
0x18001dd18  jmp     ??1?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@QEAA@XZ; std::pair<HardwareAddress const,VisibleDock>::~pair<HardwareAddress const,VisibleDock>(void)
```
