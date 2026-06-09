# __tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll

- ea: `0x1800062ce`
- end: `0x180006347`
- name: `__tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000634d`
- `0x18000635f`
- `0x180006371`

## callees

- `0x1800046b0`
- `0x1800062ce`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800062ce  mov     [rsp+arg_0], rcx
0x1800062d3  mov     [rsp+arg_8], rdx
0x1800062d8  mov     [rsp+arg_10], r8
0x1800062dd  mov     [rsp+arg_18], r9
0x1800062e2  sub     rsp, 68h
0x1800062e6  movdqa  [rsp+68h+var_48], xmm0
0x1800062ec  movdqa  [rsp+68h+var_38], xmm1
0x1800062f2  movdqa  [rsp+68h+var_28], xmm2
0x1800062f8  movdqa  [rsp+68h+var_18], xmm3
0x1800062fe  mov     rdx, rax
0x180006301  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll
0x180006308  call    __delayLoadHelper2
0x18000630d  movdqa  xmm0, [rsp+68h+var_48]
0x180006313  movdqa  xmm1, [rsp+68h+var_38]
0x180006319  movdqa  xmm2, [rsp+68h+var_28]
0x18000631f  movdqa  xmm3, [rsp+68h+var_18]
0x180006325  mov     rcx, [rsp+68h+arg_0]
0x18000632a  mov     rdx, [rsp+68h+arg_8]
0x18000632f  mov     r8, [rsp+68h+arg_10]
0x180006337  mov     r9, [rsp+68h+arg_18]
0x18000633f  add     rsp, 68h
0x180006343  jmp     short $+2
0x180006345  jmp     rax
```
