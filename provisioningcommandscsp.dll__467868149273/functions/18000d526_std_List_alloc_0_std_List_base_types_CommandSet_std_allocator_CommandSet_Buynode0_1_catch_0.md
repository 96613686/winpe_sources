# _std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0

- ea: `0x18000d526`
- end: `0x18000d546`
- name: `_std::_List_alloc_0_std::_List_base_types_CommandSet_std::allocator_CommandSet_____::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008128`
- `0x18000cb69`

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
0x18000d526  mov     [rsp+arg_8], rdx
0x18000d52b  push    rbp
0x18000d52c  sub     rsp, 20h
0x18000d530  mov     rbp, rdx
0x18000d533  mov     rdx, [rbp+30h]
0x18000d537  call    ?deallocate@?$_Wrap_alloc@V?$allocator@G@std@@@std@@QEAAXPEAG_K@Z; std::_Wrap_alloc<std::allocator<ushort>>::deallocate(ushort *,unsigned __int64)
0x18000d53c  xor     edx, edx; pThrowInfo
0x18000d53e  xor     ecx, ecx; pExceptionObject
0x18000d540  call    _CxxThrowException_0
```
