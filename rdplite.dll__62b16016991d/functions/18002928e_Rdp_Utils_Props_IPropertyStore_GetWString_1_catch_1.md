# _Rdp::Utils::Props::IPropertyStore_GetWString_::_1_::catch$1

- ea: `0x18002928e`
- end: `0x1800292c4`
- name: `_Rdp::Utils::Props::IPropertyStore_GetWString_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007b4c`

## string_xrefs

- `0x18002929f`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetWString_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x104,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002928e  mov     [rsp+arg_8], rdx
0x180029293  push    rbp
0x180029294  sub     rsp, 20h
0x180029298  mov     rbp, rdx
0x18002929b  mov     rcx, [rbp+48h]; this
0x18002929f  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800292a6  mov     edx, 104h; void *
0x1800292ab  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800292b0  mov     [rbp+50h], eax
0x1800292b3  mov     rax, 0
0x1800292bd  add     rsp, 20h
0x1800292c1  pop     rbp
0x1800292c2  retn
```
