# _std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor$0

- ea: `0x18001dcff`
- end: `0x18001dd0b`
- name: `_std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800184f8`

## pseudocode

```c
void __fastcall std::tr1::unordered_map_HardwareAddress_VisibleDock_std::hash_HardwareAddress__std::equal_to_HardwareAddress__std::allocator_std::pair_HardwareAddress_const__VisibleDock_____::operator[]_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  VisibleDock::~VisibleDock((VisibleDock *)(a2 + 1232));
}

```

## disassembly

```asm
0x18001dcff  lea     rcx, [rdx+4D0h]; this
0x18001dd06  jmp     ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
```
