# _std::_List_val_HardwareAddress_std::allocator_HardwareAddress___::_Buynode_::_1_::catch$0

- ea: `0x18001dc38`
- end: `0x18001dc58`
- name: `_std::_List_val_HardwareAddress_std::allocator_HardwareAddress___::_Buynode_::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800020bd`
- `0x18001320c`

## pseudocode

```c
void __fastcall __noreturn std::_List_val_HardwareAddress_std::allocator_HardwareAddress___::_Buynode_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::allocator<Dock>::deallocate(a1, *(_QWORD *)(a2 + 80));
  throw;
}

```

## disassembly

```asm
0x18001dc38  mov     [rsp+arg_8], rdx
0x18001dc3d  push    rbp
0x18001dc3e  sub     rsp, 20h
0x18001dc42  mov     rbp, rdx
0x18001dc45  mov     rdx, [rbp+50h]
0x18001dc49  call    ?deallocate@?$allocator@VDock@@@std@@QEAAXPEAVDock@@_K@Z; std::allocator<Dock>::deallocate(Dock *,unsigned __int64)
0x18001dc4e  xor     edx, edx; pThrowInfo
0x18001dc50  xor     ecx, ecx; pExceptionObject
0x18001dc52  call    _CxxThrowException_0
```
