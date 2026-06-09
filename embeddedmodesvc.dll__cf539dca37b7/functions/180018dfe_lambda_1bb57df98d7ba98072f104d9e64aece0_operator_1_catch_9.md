# __lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()_::_1_::catch$9

- ea: `0x180018dfe`
- end: `0x180018e24`
- name: `__lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()_::_1_::catch$9`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000887c`

## string_xrefs

- `0x180018e12`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
void __fastcall __noreturn _lambda_1bb57df98d7ba98072f104d9e64aece0_::operator()_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 456),
    (void *)0x61,
    (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
    a4);
}

```

## disassembly

```asm
0x180018dfe  mov     [rsp+arg_8], rdx
0x180018e03  push    rbp
0x180018e04  sub     rsp, 20h
0x180018e08  mov     rbp, rdx
0x180018e0b  mov     rcx, [rbp+1C8h]; this
0x180018e12  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180018e19  mov     edx, 61h ; 'a'; void *
0x180018e1e  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
