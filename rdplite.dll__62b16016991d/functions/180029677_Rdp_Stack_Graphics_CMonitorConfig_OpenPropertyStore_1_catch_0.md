# _Rdp::Stack::Graphics::CMonitorConfig::OpenPropertyStore_::_1_::catch$0

- ea: `0x180029677`
- end: `0x1800296b0`
- name: `_Rdp::Stack::Graphics::CMonitorConfig::OpenPropertyStore_::_1_::catch$0`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007b4c`

## string_xrefs

- `0x180029688`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfig.cpp`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfig::OpenPropertyStore_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 136) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x1D4,
                            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029677  mov     [rsp+arg_8], rdx
0x18002967c  push    rbp
0x18002967d  sub     rsp, 50h
0x180029681  mov     rbp, rdx
0x180029684  mov     rcx, [rbp+78h]; this
0x180029688  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002968f  mov     edx, 1D4h; void *
0x180029694  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029699  mov     [rbp+88h], eax
0x18002969f  mov     rax, 0
0x1800296a9  add     rsp, 50h
0x1800296ad  pop     rbp
0x1800296ae  retn
```
