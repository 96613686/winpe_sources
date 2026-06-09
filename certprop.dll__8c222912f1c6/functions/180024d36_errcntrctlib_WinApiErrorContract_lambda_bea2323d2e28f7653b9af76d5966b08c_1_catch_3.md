# _errcntrctlib::WinApiErrorContract__lambda_bea2323d2e28f7653b9af76d5966b08c____::_1_::catch$3

- ea: `0x180024d36`
- end: `0x180024d59`
- name: `_errcntrctlib::WinApiErrorContract__lambda_bea2323d2e28f7653b9af76d5966b08c____::_1_::catch$3`
- size: `35`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c890`

## string_xrefs

- `0x180024d47`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn errcntrctlib::WinApiErrorContract__lambda_bea2323d2e28f7653b9af76d5966b08c____::_1_::catch_3(
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
0x180024d36  mov     [rsp+arg_8], rdx
0x180024d3b  push    rbp
0x180024d3c  sub     rsp, 20h
0x180024d40  mov     rbp, rdx
0x180024d43  mov     rcx, [rbp+38h]; this
0x180024d47  lea     r8, aDsSecurityScar_1; "ds\\security\\scard\\common\\devhlpr\\l"...
0x180024d4e  mov     edx, 68h ; 'h'; void *
0x180024d53  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
