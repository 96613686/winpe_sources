# _AOMDHandler::InitializeConfig_::_1_::catch$0

- ea: `0x18002264e`
- end: `0x180022682`
- name: `_AOMDHandler::InitializeConfig_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000eacc`

## pseudocode

```c
__int64 __fastcall AOMDHandler::InitializeConfig_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 104),
    (void *)0x2D9,
    (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18002264e  mov     [rsp+arg_8], rdx
0x180022653  push    rbp
0x180022654  sub     rsp, 30h
0x180022658  mov     rbp, rdx
0x18002265b  mov     rcx, [rbp+68h]; this
0x18002265f  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180022666  mov     edx, 2D9h; void *
0x18002266b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180022670  nop
0x180022671  mov     rax, 0
0x18002267b  add     rsp, 30h
0x18002267f  pop     rbp
0x180022680  retn
```
