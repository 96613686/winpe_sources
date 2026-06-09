# _std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::operator__::_1_::catch$0

- ea: `0x18001bf3b`
- end: `0x18001bf5b`
- name: `_std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::operator__::_1_::catch$0`
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
void __fastcall __noreturn std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::operator__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::vector<ATL::CComVariant>::_Tidy(*(_QWORD **)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x18001bf3b  mov     [rsp+arg_8], rdx
0x18001bf40  push    rbp
0x18001bf41  sub     rsp, 30h
0x18001bf45  mov     rbp, rdx
0x18001bf48  mov     rcx, [rbp+40h]
0x18001bf4c  call    ?_Tidy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXXZ; std::vector<ATL::CComVariant>::_Tidy(void)
0x18001bf51  xor     edx, edx; pThrowInfo
0x18001bf53  xor     ecx, ecx; pExceptionObject
0x18001bf55  call    _CxxThrowException_0
```
