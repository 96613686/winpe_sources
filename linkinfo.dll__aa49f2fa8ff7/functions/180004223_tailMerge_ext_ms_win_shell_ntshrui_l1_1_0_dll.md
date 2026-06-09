# __tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll

- ea: `0x180004223`
- end: `0x18000429c`
- name: `__tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042a2`
- `0x1800042b4`

## callees

- `0x1800036d0`
- `0x180004223`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_ntshrui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180004223  mov     [rsp+arg_0], rcx
0x180004228  mov     [rsp+arg_8], rdx
0x18000422d  mov     [rsp+arg_10], r8
0x180004232  mov     [rsp+arg_18], r9
0x180004237  sub     rsp, 68h
0x18000423b  movdqa  [rsp+68h+var_48], xmm0
0x180004241  movdqa  [rsp+68h+var_38], xmm1
0x180004247  movdqa  [rsp+68h+var_28], xmm2
0x18000424d  movdqa  [rsp+68h+var_18], xmm3
0x180004253  mov     rdx, rax
0x180004256  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_ntshrui_l1_1_0_dll
0x18000425d  call    __delayLoadHelper2
0x180004262  movdqa  xmm0, [rsp+68h+var_48]
0x180004268  movdqa  xmm1, [rsp+68h+var_38]
0x18000426e  movdqa  xmm2, [rsp+68h+var_28]
0x180004274  movdqa  xmm3, [rsp+68h+var_18]
0x18000427a  mov     rcx, [rsp+68h+arg_0]
0x18000427f  mov     rdx, [rsp+68h+arg_8]
0x180004284  mov     r8, [rsp+68h+arg_10]
0x18000428c  mov     r9, [rsp+68h+arg_18]
0x180004294  add     rsp, 68h
0x180004298  jmp     short $+2
0x18000429a  jmp     rax
```
