# _std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::vector_ATL::CComVariant_std::allocator_ATL::CComVariant____::_1_::catch$0

- ea: `0x18001b7b4`
- end: `0x18001b7d4`
- name: `_std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::vector_ATL::CComVariant_std::allocator_ATL::CComVariant____::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007a4c`
- `0x18000a4ec`

## pseudocode

```c
void __fastcall __noreturn std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::vector_ATL::CComVariant_std::allocator_ATL::CComVariant____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::vector<ATL::CComVariant>::_Tidy(*(_QWORD **)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x18001b7b4  mov     [rsp+arg_8], rdx
0x18001b7b9  push    rbp
0x18001b7ba  sub     rsp, 30h
0x18001b7be  mov     rbp, rdx
0x18001b7c1  mov     rcx, [rbp+40h]
0x18001b7c5  call    ?_Tidy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXXZ; std::vector<ATL::CComVariant>::_Tidy(void)
0x18001b7ca  xor     edx, edx; pThrowInfo
0x18001b7cc  xor     ecx, ecx; pExceptionObject
0x18001b7ce  call    _CxxThrowException_0
```
