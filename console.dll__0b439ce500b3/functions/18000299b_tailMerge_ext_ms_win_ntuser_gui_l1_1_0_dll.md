# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x18000299b`
- end: `0x180002a14`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a1a`
- `0x180002ab7`

## callees

- `0x18000299b`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000299b  mov     [rsp+arg_0], rcx
0x1800029a0  mov     [rsp+arg_8], rdx
0x1800029a5  mov     [rsp+arg_10], r8
0x1800029aa  mov     [rsp+arg_18], r9
0x1800029af  sub     rsp, 68h
0x1800029b3  movdqa  [rsp+68h+var_48], xmm0
0x1800029b9  movdqa  [rsp+68h+var_38], xmm1
0x1800029bf  movdqa  [rsp+68h+var_28], xmm2
0x1800029c5  movdqa  [rsp+68h+var_18], xmm3
0x1800029cb  mov     rdx, rax
0x1800029ce  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x1800029d5  call    __delayLoadHelper2
0x1800029da  movdqa  xmm0, [rsp+68h+var_48]
0x1800029e0  movdqa  xmm1, [rsp+68h+var_38]
0x1800029e6  movdqa  xmm2, [rsp+68h+var_28]
0x1800029ec  movdqa  xmm3, [rsp+68h+var_18]
0x1800029f2  mov     rcx, [rsp+68h+arg_0]
0x1800029f7  mov     rdx, [rsp+68h+arg_8]
0x1800029fc  mov     r8, [rsp+68h+arg_10]
0x180002a04  mov     r9, [rsp+68h+arg_18]
0x180002a0c  add     rsp, 68h
0x180002a10  jmp     short $+2
0x180002a12  jmp     rax
```
