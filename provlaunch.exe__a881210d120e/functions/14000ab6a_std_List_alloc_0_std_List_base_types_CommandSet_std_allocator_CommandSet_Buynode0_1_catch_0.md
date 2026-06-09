# _std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0

- ea: `0x14000ab6a`
- end: `0x14000ab8a`
- name: `_std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006634`
- `0x14000a21a`

## pseudocode

```c
void __fastcall __noreturn std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(a1, *(_QWORD *)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x14000ab6a  mov     [rsp+arg_8], rdx
0x14000ab6f  push    rbp
0x14000ab70  sub     rsp, 20h
0x14000ab74  mov     rbp, rdx
0x14000ab77  mov     rdx, [rbp+30h]
0x14000ab7b  call    ?deallocate@?$_Wrap_alloc@V?$allocator@G@std@@@std@@QEAAXPEAG_K@Z; std::_Wrap_alloc<std::allocator<ushort>>::deallocate(ushort *,unsigned __int64)
0x14000ab80  xor     edx, edx; pThrowInfo
0x14000ab82  xor     ecx, ecx; pExceptionObject
0x14000ab84  call    _CxxThrowException_0
```
