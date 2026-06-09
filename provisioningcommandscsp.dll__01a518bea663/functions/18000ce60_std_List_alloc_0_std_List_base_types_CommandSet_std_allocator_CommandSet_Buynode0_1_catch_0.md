# _std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0

- ea: `0x18000ce60`
- end: `0x18000ce80`
- name: `_std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007d88`
- `0x18000c4b0`

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
0x18000ce60  mov     [rsp+arg_8], rdx
0x18000ce65  push    rbp
0x18000ce66  sub     rsp, 20h
0x18000ce6a  mov     rbp, rdx
0x18000ce6d  mov     rdx, [rbp+30h]
0x18000ce71  call    ?deallocate@?$_Wrap_alloc@V?$allocator@G@std@@@std@@QEAAXPEAG_K@Z; std::_Wrap_alloc<std::allocator<ushort>>::deallocate(ushort *,unsigned __int64)
0x18000ce76  xor     edx, edx; pThrowInfo
0x18000ce78  xor     ecx, ecx; pExceptionObject
0x18000ce7a  call    _CxxThrowException_0
```
