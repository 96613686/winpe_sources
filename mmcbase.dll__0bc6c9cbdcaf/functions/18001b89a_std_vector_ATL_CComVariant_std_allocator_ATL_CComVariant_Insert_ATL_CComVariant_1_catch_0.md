# _std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::_Insert_ATL::CComVariant____::_1_::catch$0

- ea: `0x18001b89a`
- end: `0x18001b8c8`
- name: `_std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::_Insert_ATL::CComVariant____::_1_::catch$0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a4ec`
- `0x180013e30`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001b8b8`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001b8b8`

## pseudocode

```c
void __fastcall __noreturn std::vector_ATL::CComVariant_std::allocator_ATL::CComVariant___::_Insert_ATL::CComVariant____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::vector<ATL::CComVariant>::_Destroy(a1, *(VARIANTARG **)(a2 + 120), *(VARIANTARG **)(a2 + 112));
  operator delete(*(void **)(a2 + 120));
  throw;
}

```

## disassembly

```asm
0x18001b89a  mov     [rsp+arg_8], rdx
0x18001b89f  push    rbp
0x18001b8a0  sub     rsp, 30h
0x18001b8a4  mov     rbp, rdx
0x18001b8a7  mov     r8, [rbp+70h]
0x18001b8ab  mov     rdx, [rbp+78h]
0x18001b8af  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x18001b8b4  mov     rcx, [rbp+78h]
0x18001b8b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b8be  xor     edx, edx; pThrowInfo
0x18001b8c0  xor     ecx, ecx; pExceptionObject
0x18001b8c2  call    _CxxThrowException_0
```
