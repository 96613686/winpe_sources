# _std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch$0

- ea: `0x18001e07b`
- end: `0x18001e09e`
- name: `_std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch$0`
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
void __fastcall __noreturn std::vector_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock________std::allocator_std::_List_iterator_std::_List_val_std::pair_HardwareAddress_const__VisibleDock__std::allocator_std::pair_HardwareAddress_const__VisibleDock___________::_Insert_n_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::allocator<Dock>::deallocate(a1, *(_QWORD *)(a2 + 144));
  throw;
}

```

## disassembly

```asm
0x18001e07b  mov     [rsp+arg_8], rdx
0x18001e080  push    rbp
0x18001e081  sub     rsp, 30h
0x18001e085  mov     rbp, rdx
0x18001e088  mov     rdx, [rbp+90h]
0x18001e08f  call    ?deallocate@?$allocator@VDock@@@std@@QEAAXPEAVDock@@_K@Z; std::allocator<Dock>::deallocate(Dock *,unsigned __int64)
0x18001e094  xor     edx, edx; pThrowInfo
0x18001e096  xor     ecx, ecx; pExceptionObject
0x18001e098  call    _CxxThrowException_0
```
