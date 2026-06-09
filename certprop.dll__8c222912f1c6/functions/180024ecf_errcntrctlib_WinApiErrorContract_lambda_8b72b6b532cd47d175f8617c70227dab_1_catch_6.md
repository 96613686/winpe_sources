# _errcntrctlib::WinApiErrorContract__lambda_8b72b6b532cd47d175f8617c70227dab____::_1_::catch$6

- ea: `0x180024ecf`
- end: `0x180024ef2`
- name: `_errcntrctlib::WinApiErrorContract__lambda_8b72b6b532cd47d175f8617c70227dab____::_1_::catch$6`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c890`

## string_xrefs

- `0x180024ee0`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn errcntrctlib::WinApiErrorContract__lambda_8b72b6b532cd47d175f8617c70227dab____::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x68,
    (int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
    a4);
}

```

## disassembly

```asm
0x180024ecf  mov     [rsp+arg_8], rdx
0x180024ed4  push    rbp
0x180024ed5  sub     rsp, 20h
0x180024ed9  mov     rbp, rdx
0x180024edc  mov     rcx, [rbp+58h]; this
0x180024ee0  lea     r8, aDsSecurityScar_1; "ds\\security\\scard\\common\\devhlpr\\l"...
0x180024ee7  mov     edx, 68h ; 'h'; void *
0x180024eec  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
