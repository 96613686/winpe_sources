# _std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch$1

- ea: `0x18001e0a4`
- end: `0x18001e0bb`
- name: `_std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch$1`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800020bd`

## pseudocode

```c
void __noreturn std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch_1()
{
  throw;
}

```

## disassembly

```asm
0x18001e0a4  mov     [rsp+arg_8], rdx
0x18001e0a9  push    rbp
0x18001e0aa  sub     rsp, 30h
0x18001e0ae  mov     rbp, rdx
0x18001e0b1  xor     edx, edx; pThrowInfo
0x18001e0b3  xor     ecx, ecx; pExceptionObject
0x18001e0b5  call    _CxxThrowException_0
```
