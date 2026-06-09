# _std::_Uninit_move_ATL::CComVariant___ATL::CComVariant___std::allocator_ATL::CComVariant__ATL::CComVariant__::_1_::catch$0

- ea: `0x18001be5d`
- end: `0x18001bea0`
- name: `_std::_Uninit_move_ATL::CComVariant___ATL::CComVariant___std::allocator_ATL::CComVariant__ATL::CComVariant__::_1_::catch$0`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a4ec`
- `0x18001be5d`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001be86`
- `OLEAUT32!__imp_VariantClear` at `0x18001be86`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_ATL::CComVariant___ATL::CComVariant___std::allocator_ATL::CComVariant__ATL::CComVariant__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  VARIANTARG *i; // rbx

  for ( i = *(VARIANTARG **)(a2 + 72); i != *(VARIANTARG **)(a2 + 64); ++i )
  {
    if ( i->vt == 4095 )
      i->vt = 8;
    VariantClear(i);
  }
  throw;
}

```

## disassembly

```asm
0x18001be5d  mov     [rsp+arg_8], rdx
0x18001be62  push    rbx
0x18001be63  push    rbp
0x18001be64  sub     rsp, 28h
0x18001be68  mov     rbp, rdx
0x18001be6b  mov     rbx, [rbp+48h]
0x18001be6f  jmp     short loc_18001BE90
0x18001be71  mov     eax, 0FFFh
0x18001be76  cmp     [rbx], ax
0x18001be79  jnz     short loc_18001BE83
0x18001be7b  mov     eax, 8
0x18001be80  mov     [rbx], ax
0x18001be83  mov     rcx, rbx; pvarg
0x18001be86  call    cs:__imp_VariantClear
0x18001be8c  add     rbx, 18h
0x18001be90  cmp     rbx, [rbp+40h]
0x18001be94  jnz     short loc_18001BE71
0x18001be96  xor     edx, edx; pThrowInfo
0x18001be98  xor     ecx, ecx; pExceptionObject
0x18001be9a  call    _CxxThrowException_0
```
