# _Utils::Strings::EscapeXml_::_1_::catch$4

- ea: `0x180021655`
- end: `0x180021689`
- name: `_Utils::Strings::EscapeXml_::_1_::catch$4`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000e2f0`

## pseudocode

```c
__int64 __fastcall Utils::Strings::EscapeXml_::_1_::catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x49,
    (int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180021655  mov     [rsp+arg_8], rdx
0x18002165a  push    rbp
0x18002165b  sub     rsp, 20h
0x18002165f  mov     rbp, rdx
0x180021662  mov     rcx, [rbp+38h]; this
0x180021666  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18002166d  mov     edx, 49h ; 'I'; void *
0x180021672  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180021677  nop
0x180021678  mov     rax, 0
0x180021682  add     rsp, 20h
0x180021686  pop     rbp
0x180021687  retn
```
