# _Utils::Strings::EscapeXml_::_1_::catch$4

- ea: `0x180023023`
- end: `0x180023057`
- name: `_Utils::Strings::EscapeXml_::_1_::catch$4`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000eacc`

## pseudocode

```c
__int64 __fastcall Utils::Strings::EscapeXml_::_1_::catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x49,
    (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\utils.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180023023  mov     [rsp+arg_8], rdx
0x180023028  push    rbp
0x180023029  sub     rsp, 20h
0x18002302d  mov     rbp, rdx
0x180023030  mov     rcx, [rbp+38h]; this
0x180023034  lea     r8, aBaseDiagnosisM_0; "base\\diagnosis\\memdiag\\onlinemd\\uti"...
0x18002303b  mov     edx, 49h ; 'I'; void *
0x180023040  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180023045  nop
0x180023046  mov     rax, 0
0x180023050  add     rsp, 20h
0x180023054  pop     rbp
0x180023055  retn
```
