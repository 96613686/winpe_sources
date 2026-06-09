# _Rdp::Stack::Graphics::CMonitorConfigChannel::OnDataReceived_::_1_::catch$0

- ea: `0x180029570`
- end: `0x1800295a9`
- name: `_Rdp::Stack::Graphics::CMonitorConfigChannel::OnDataReceived_::_1_::catch$0`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007b4c`

## string_xrefs

- `0x180029581`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::OnDataReceived_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 136) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0xA7,
                            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029570  mov     [rsp+arg_8], rdx
0x180029575  push    rbp
0x180029576  sub     rsp, 50h
0x18002957a  mov     rbp, rdx
0x18002957d  mov     rcx, [rbp+78h]; this
0x180029581  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180029588  mov     edx, 0A7h; void *
0x18002958d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029592  mov     [rbp+88h], eax
0x180029598  mov     rax, 0
0x1800295a2  add     rsp, 50h
0x1800295a6  pop     rbp
0x1800295a7  retn
```
