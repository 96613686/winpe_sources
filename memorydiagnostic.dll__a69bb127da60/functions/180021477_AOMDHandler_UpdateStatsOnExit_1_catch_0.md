# _AOMDHandler::UpdateStatsOnExit_::_1_::catch$0

- ea: `0x180021477`
- end: `0x1800214ad`
- name: `_AOMDHandler::UpdateStatsOnExit_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180010994`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnExit_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x427,
                           (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180021477  mov     [rsp+arg_8], rdx
0x18002147c  push    rbp
0x18002147d  sub     rsp, 30h
0x180021481  mov     rbp, rdx
0x180021484  mov     rcx, [rbp+38h]; this
0x180021488  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18002148f  mov     edx, 427h; void *
0x180021494  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180021499  mov     [rbp+48h], eax
0x18002149c  mov     rax, 0
0x1800214a6  add     rsp, 30h
0x1800214aa  pop     rbp
0x1800214ab  retn
```
