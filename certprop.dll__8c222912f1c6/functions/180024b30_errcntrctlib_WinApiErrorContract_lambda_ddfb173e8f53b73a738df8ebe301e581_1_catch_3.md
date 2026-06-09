# _errcntrctlib::WinApiErrorContract__lambda_ddfb173e8f53b73a738df8ebe301e581____::_1_::catch$3

- ea: `0x180024b30`
- end: `0x180024b53`
- name: `_errcntrctlib::WinApiErrorContract__lambda_ddfb173e8f53b73a738df8ebe301e581____::_1_::catch$3`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c890`

## string_xrefs

- `0x180024b41`: `ds\security\scard\services\certprop\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn errcntrctlib::WinApiErrorContract__lambda_ddfb173e8f53b73a738df8ebe301e581____::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x39,
    (int)"ds\\security\\scard\\services\\certprop\\errorcontract.h",
    a4);
}

```

## disassembly

```asm
0x180024b30  mov     [rsp+arg_8], rdx
0x180024b35  push    rbp
0x180024b36  sub     rsp, 20h
0x180024b3a  mov     rbp, rdx
0x180024b3d  mov     rcx, [rbp+38h]; this
0x180024b41  lea     r8, aDsSecurityScar_0; "ds\\security\\scard\\services\\certprop"...
0x180024b48  mov     edx, 39h ; '9'; void *
0x180024b4d  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
