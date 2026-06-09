# __tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll

- ea: `0x1800154b1`
- end: `0x18001552a`
- name: `__tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015530`
- `0x180015542`
- `0x180015554`
- `0x180015566`

## callees

- `0x1800154b1`
- `0x18002e3c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_rtcore_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800154b1  mov     [rsp+arg_0], rcx
0x1800154b6  mov     [rsp+arg_8], rdx
0x1800154bb  mov     [rsp+arg_10], r8
0x1800154c0  mov     [rsp+arg_18], r9
0x1800154c5  sub     rsp, 68h
0x1800154c9  movdqa  [rsp+68h+var_48], xmm0
0x1800154cf  movdqa  [rsp+68h+var_38], xmm1
0x1800154d5  movdqa  [rsp+68h+var_28], xmm2
0x1800154db  movdqa  [rsp+68h+var_18], xmm3
0x1800154e1  mov     rdx, rax
0x1800154e4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_rtcore_ntuser_window_l1_1_0_dll
0x1800154eb  call    __delayLoadHelper2
0x1800154f0  movdqa  xmm0, [rsp+68h+var_48]
0x1800154f6  movdqa  xmm1, [rsp+68h+var_38]
0x1800154fc  movdqa  xmm2, [rsp+68h+var_28]
0x180015502  movdqa  xmm3, [rsp+68h+var_18]
0x180015508  mov     rcx, [rsp+68h+arg_0]
0x18001550d  mov     rdx, [rsp+68h+arg_8]
0x180015512  mov     r8, [rsp+68h+arg_10]
0x18001551a  mov     r9, [rsp+68h+arg_18]
0x180015522  add     rsp, 68h
0x180015526  jmp     short $+2
0x180015528  jmp     rax
```
