# _Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo_::_1_::catch$0

- ea: `0x180029534`
- end: `0x18002956a`
- name: `_Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007b4c`

## string_xrefs

- `0x180029545`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x1B1,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029534  mov     [rsp+arg_8], rdx
0x180029539  push    rbp
0x18002953a  sub     rsp, 30h
0x18002953e  mov     rbp, rdx
0x180029541  mov     rcx, [rbp+48h]; this
0x180029545  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002954c  mov     edx, 1B1h; void *
0x180029551  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029556  mov     [rbp+50h], eax
0x180029559  mov     rax, 0
0x180029563  add     rsp, 30h
0x180029567  pop     rbp
0x180029568  retn
```
