# _Microsoft::IoT::Utility::MTAEventThread::WorkerThread_::_1_::catch$26

- ea: `0x180019395`
- end: `0x1800193bb`
- name: `_Microsoft::IoT::Utility::MTAEventThread::WorkerThread_::_1_::catch$26`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000887c`

## string_xrefs

- `0x1800193a9`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
void __fastcall __noreturn Microsoft::IoT::Utility::MTAEventThread::WorkerThread_::_1_::catch_26(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::FailFast_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 1368),
    (void *)0x118,
    (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
    a4);
}

```

## disassembly

```asm
0x180019395  mov     [rsp+arg_8], rdx
0x18001939a  push    rbp
0x18001939b  sub     rsp, 30h
0x18001939f  mov     rbp, rdx
0x1800193a2  mov     rcx, [rbp+558h]; this
0x1800193a9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800193b0  mov     edx, 118h; void *
0x1800193b5  call    ?FailFast_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_CaughtException(void *,uint,char const *)
```
