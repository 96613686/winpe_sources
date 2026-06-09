# _Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks_::_1_::catch$6

- ea: `0x180018fed`
- end: `0x180019010`
- name: `_Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks_::_1_::catch$6`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000887c`

## string_xrefs

- `0x180018ffe`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
void __fastcall __noreturn Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x4F,
    (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
    a4);
}

```

## disassembly

```asm
0x180018fed  mov     [rsp+arg_8], rdx
0x180018ff2  push    rbp
0x180018ff3  sub     rsp, 20h
0x180018ff7  mov     rbp, rdx
0x180018ffa  mov     rcx, [rbp+58h]; this
0x180018ffe  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180019005  mov     edx, 4Fh ; 'O'; void *
0x18001900a  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
