# _AOMDHandler::UpdateStatsOnExit_::_1_::catch$0

- ea: `0x180022e3d`
- end: `0x180022e73`
- name: `_AOMDHandler::UpdateStatsOnExit_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180011364`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnExit_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x486,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180022e3d  mov     [rsp+arg_8], rdx
0x180022e42  push    rbp
0x180022e43  sub     rsp, 30h
0x180022e47  mov     rbp, rdx
0x180022e4a  mov     rcx, [rbp+38h]; this
0x180022e4e  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180022e55  mov     edx, 486h; void *
0x180022e5a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180022e5f  mov     [rbp+48h], eax
0x180022e62  mov     rax, 0
0x180022e6c  add     rsp, 30h
0x180022e70  pop     rbp
0x180022e71  retn
```
