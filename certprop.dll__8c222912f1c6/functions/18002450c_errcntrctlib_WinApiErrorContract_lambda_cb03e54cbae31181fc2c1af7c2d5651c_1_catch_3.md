# _errcntrctlib::WinApiErrorContract__lambda_cb03e54cbae31181fc2c1af7c2d5651c____::_1_::catch$3

- ea: `0x18002450c`
- end: `0x18002452f`
- name: `_errcntrctlib::WinApiErrorContract__lambda_cb03e54cbae31181fc2c1af7c2d5651c____::_1_::catch$3`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c890`

## string_xrefs

- `0x18002451d`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn errcntrctlib::WinApiErrorContract__lambda_cb03e54cbae31181fc2c1af7c2d5651c____::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x68,
    (int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
    a4);
}

```

## disassembly

```asm
0x18002450c  mov     [rsp+arg_8], rdx
0x180024511  push    rbp
0x180024512  sub     rsp, 20h
0x180024516  mov     rbp, rdx
0x180024519  mov     rcx, [rbp+38h]; this
0x18002451d  lea     r8, aDsSecurityScar_1; "ds\\security\\scard\\common\\devhlpr\\l"...
0x180024524  mov     edx, 68h ; 'h'; void *
0x180024529  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
