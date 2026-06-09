# _Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession_::_1_::catch$5

- ea: `0x1800190ff`
- end: `0x180019122`
- name: `_Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession_::_1_::catch$5`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000887c`

## string_xrefs

- `0x180019110`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
void __fastcall __noreturn Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x3A,
    (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
    a4);
}

```

## disassembly

```asm
0x1800190ff  mov     [rsp+arg_8], rdx
0x180019104  push    rbp
0x180019105  sub     rsp, 30h
0x180019109  mov     rbp, rdx
0x18001910c  mov     rcx, [rbp+78h]; this
0x180019110  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180019117  mov     edx, 3Ah ; ':'; void *
0x18001911c  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
