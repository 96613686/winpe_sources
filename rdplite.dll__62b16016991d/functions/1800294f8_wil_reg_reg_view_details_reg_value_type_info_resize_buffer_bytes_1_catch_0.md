# _wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes_::_1_::catch$0

- ea: `0x1800294f8`
- end: `0x18002952e`
- name: `_wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007b4c`

## string_xrefs

- `0x180029509`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x249,
                           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800294f8  mov     [rsp+arg_8], rdx
0x1800294fd  push    rbp
0x1800294fe  sub     rsp, 20h
0x180029502  mov     rbp, rdx
0x180029505  mov     rcx, [rbp+28h]; this
0x180029509  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029510  mov     edx, 249h; void *
0x180029515  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002951a  mov     [rbp+38h], eax
0x18002951d  mov     rax, 0
0x180029527  add     rsp, 20h
0x18002952b  pop     rbp
0x18002952c  retn
```
