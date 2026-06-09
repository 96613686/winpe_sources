# _Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize_::_1_::catch$15

- ea: `0x180018ee7`
- end: `0x180018f0d`
- name: `_Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize_::_1_::catch$15`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000887c`

## string_xrefs

- `0x180018efb`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
void __fastcall __noreturn Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 248),
    (void *)0x64,
    (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
    a4);
}

```

## disassembly

```asm
0x180018ee7  mov     [rsp+arg_8], rdx
0x180018eec  push    rbp
0x180018eed  sub     rsp, 20h
0x180018ef1  mov     rbp, rdx
0x180018ef4  mov     rcx, [rbp+0F8h]; this
0x180018efb  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180018f02  mov     edx, 64h ; 'd'; void *
0x180018f07  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
