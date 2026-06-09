# __tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll

- ea: `0x180004198`
- end: `0x180004211`
- name: `__tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004217`

## callees

- `0x1800036d0`
- `0x180004198`

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
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_rtcore_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004198  mov     [rsp+arg_0], rcx
0x18000419d  mov     [rsp+arg_8], rdx
0x1800041a2  mov     [rsp+arg_10], r8
0x1800041a7  mov     [rsp+arg_18], r9
0x1800041ac  sub     rsp, 68h
0x1800041b0  movdqa  [rsp+68h+var_48], xmm0
0x1800041b6  movdqa  [rsp+68h+var_38], xmm1
0x1800041bc  movdqa  [rsp+68h+var_28], xmm2
0x1800041c2  movdqa  [rsp+68h+var_18], xmm3
0x1800041c8  mov     rdx, rax
0x1800041cb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_rtcore_ntuser_window_l1_1_0_dll
0x1800041d2  call    __delayLoadHelper2
0x1800041d7  movdqa  xmm0, [rsp+68h+var_48]
0x1800041dd  movdqa  xmm1, [rsp+68h+var_38]
0x1800041e3  movdqa  xmm2, [rsp+68h+var_28]
0x1800041e9  movdqa  xmm3, [rsp+68h+var_18]
0x1800041ef  mov     rcx, [rsp+68h+arg_0]
0x1800041f4  mov     rdx, [rsp+68h+arg_8]
0x1800041f9  mov     r8, [rsp+68h+arg_10]
0x180004201  mov     r9, [rsp+68h+arg_18]
0x180004209  add     rsp, 68h
0x18000420d  jmp     short $+2
0x18000420f  jmp     rax
```
