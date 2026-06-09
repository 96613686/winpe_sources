# _std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::reserve_::_1_::catch$0

- ea: `0x18001d794`
- end: `0x18001d7b7`
- name: `_std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::reserve_::_1_::catch$0`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800020bd`
- `0x18001320c`

## pseudocode

```c
void __fastcall __noreturn std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::reserve_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::allocator<Dock>::deallocate(a1, *(_QWORD *)(a2 + 136));
  throw;
}

```

## disassembly

```asm
0x18001d794  mov     [rsp+arg_8], rdx
0x18001d799  push    rbp
0x18001d79a  sub     rsp, 30h
0x18001d79e  mov     rbp, rdx
0x18001d7a1  mov     rdx, [rbp+88h]
0x18001d7a8  call    ?deallocate@?$allocator@VDock@@@std@@QEAAXPEAVDock@@_K@Z; std::allocator<Dock>::deallocate(Dock *,unsigned __int64)
0x18001d7ad  xor     edx, edx; pThrowInfo
0x18001d7af  xor     ecx, ecx; pExceptionObject
0x18001d7b1  call    _CxxThrowException_0
```
