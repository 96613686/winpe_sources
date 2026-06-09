# _std::_Uninit_move_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________::_1_::catch$0

- ea: `0x18001dc5e`
- end: `0x18001dc75`
- name: `_std::_Uninit_move_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800020bd`

## pseudocode

```c
void __noreturn std::_Uninit_move_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock__________::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x18001dc5e  mov     [rsp+arg_8], rdx
0x18001dc63  push    rbp
0x18001dc64  sub     rsp, 20h
0x18001dc68  mov     rbp, rdx
0x18001dc6b  xor     edx, edx; pThrowInfo
0x18001dc6d  xor     ecx, ecx; pExceptionObject
0x18001dc6f  call    _CxxThrowException_0
```
