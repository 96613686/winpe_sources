# _AOMDHandler::UpdateStatsOnThresholdMet_::_1_::catch$0

- ea: `0x1800214b3`
- end: `0x1800214e9`
- name: `_AOMDHandler::UpdateStatsOnThresholdMet_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180010994`

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
                           (void *)0x402,
                           (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800214b3  mov     [rsp+arg_8], rdx
0x1800214b8  push    rbp
0x1800214b9  sub     rsp, 20h
0x1800214bd  mov     rbp, rdx
0x1800214c0  mov     rcx, [rbp+28h]; this
0x1800214c4  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800214cb  mov     edx, 402h; void *
0x1800214d0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800214d5  mov     [rbp+30h], eax
0x1800214d8  mov     rax, 0
0x1800214e2  add     rsp, 20h
0x1800214e6  pop     rbp
0x1800214e7  retn
```
