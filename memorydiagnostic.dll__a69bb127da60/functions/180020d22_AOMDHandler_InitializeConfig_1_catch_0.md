# _AOMDHandler::InitializeConfig_::_1_::catch$0

- ea: `0x180020d22`
- end: `0x180020d56`
- name: `_AOMDHandler::InitializeConfig_::_1_::catch$0`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e2f0`

## pseudocode

```c
__int64 __fastcall AOMDHandler::InitializeConfig_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x27B,
    (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180020d22  mov     [rsp+arg_8], rdx
0x180020d27  push    rbp
0x180020d28  sub     rsp, 20h
0x180020d2c  mov     rbp, rdx
0x180020d2f  mov     rcx, [rbp+58h]; this
0x180020d33  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180020d3a  mov     edx, 27Bh; void *
0x180020d3f  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180020d44  nop
0x180020d45  mov     rax, 0
0x180020d4f  add     rsp, 20h
0x180020d53  pop     rbp
0x180020d54  retn
```
