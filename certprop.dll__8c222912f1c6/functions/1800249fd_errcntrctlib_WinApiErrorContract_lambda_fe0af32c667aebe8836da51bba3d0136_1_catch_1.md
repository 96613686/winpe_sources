# _errcntrctlib::WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136____::_1_::catch$1

- ea: `0x1800249fd`
- end: `0x180024a20`
- name: `_errcntrctlib::WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136____::_1_::catch$1`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c890`

## string_xrefs

- `0x180024a0e`: `ds\security\scard\common\certhlpr\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn errcntrctlib::WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136____::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x1B,
    (int)"ds\\security\\scard\\common\\certhlpr\\errorcontract.h",
    a4);
}

```

## disassembly

```asm
0x1800249fd  mov     [rsp+arg_8], rdx
0x180024a02  push    rbp
0x180024a03  sub     rsp, 20h
0x180024a07  mov     rbp, rdx
0x180024a0a  mov     rcx, [rbp+28h]; this
0x180024a0e  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\certhlpr\\"...
0x180024a15  mov     edx, 1Bh; void *
0x180024a1a  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
