# _DelegationConfig::s_GetAvailablePackages_::_1_::catch$33

- ea: `0x1800195c9`
- end: `0x1800195fb`
- name: `_DelegationConfig::s_GetAvailablePackages_::_1_::catch$33`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180015680`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_GetAvailablePackages_::_1_::catch_33(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 424),
                           (void *)0xD6,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800195c9  mov     [rsp+arg_8], rdx
0x1800195ce  push    rbp
0x1800195cf  sub     rsp, 20h
0x1800195d3  mov     rbp, rdx
0x1800195d6  mov     rcx, [rbp+1A8h]; this
0x1800195dd  mov     edx, 0D6h; void *
0x1800195e2  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800195e7  mov     [rbp+58h], eax
0x1800195ea  mov     rax, 0
0x1800195f4  add     rsp, 20h
0x1800195f8  pop     rbp
0x1800195f9  retn
```
