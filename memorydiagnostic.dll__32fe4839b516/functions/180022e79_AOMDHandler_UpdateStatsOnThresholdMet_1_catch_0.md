# _AOMDHandler::UpdateStatsOnThresholdMet_::_1_::catch$0

- ea: `0x180022e79`
- end: `0x180022eaf`
- name: `_AOMDHandler::UpdateStatsOnThresholdMet_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180011364`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnThresholdMet_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x461,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180022e79  mov     [rsp+arg_8], rdx
0x180022e7e  push    rbp
0x180022e7f  sub     rsp, 20h
0x180022e83  mov     rbp, rdx
0x180022e86  mov     rcx, [rbp+28h]; this
0x180022e8a  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180022e91  mov     edx, 461h; void *
0x180022e96  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180022e9b  mov     [rbp+30h], eax
0x180022e9e  mov     rax, 0
0x180022ea8  add     rsp, 20h
0x180022eac  pop     rbp
0x180022ead  retn
```
