# _Microsoft::IoT::Utility::MTAThread::WorkerThread_::_1_::catch$16

- ea: `0x1800194e0`
- end: `0x180019506`
- name: `_Microsoft::IoT::Utility::MTAThread::WorkerThread_::_1_::catch$16`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000887c`

## string_xrefs

- `0x1800194f4`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
void __fastcall __noreturn Microsoft::IoT::Utility::MTAThread::WorkerThread_::_1_::catch_16(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0xCA,
    (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
    a4);
}

```

## disassembly

```asm
0x1800194e0  mov     [rsp+arg_8], rdx
0x1800194e5  push    rbp
0x1800194e6  sub     rsp, 30h
0x1800194ea  mov     rbp, rdx
0x1800194ed  mov     rcx, [rbp+98h]; this
0x1800194f4  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800194fb  mov     edx, 0CAh; void *
0x180019500  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
