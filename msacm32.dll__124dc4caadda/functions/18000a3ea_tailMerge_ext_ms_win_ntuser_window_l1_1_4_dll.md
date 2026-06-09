# __tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll

- ea: `0x18000a3ea`
- end: `0x18000a463`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a469`
- `0x18000a518`
- `0x18000a695`

## callees

- `0x180007cb0`
- `0x18000a3ea`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a3ea  mov     [rsp+arg_0], rcx
0x18000a3ef  mov     [rsp+arg_8], rdx
0x18000a3f4  mov     [rsp+arg_10], r8
0x18000a3f9  mov     [rsp+arg_18], r9
0x18000a3fe  sub     rsp, 68h
0x18000a402  movdqa  [rsp+68h+var_48], xmm0
0x18000a408  movdqa  [rsp+68h+var_38], xmm1
0x18000a40e  movdqa  [rsp+68h+var_28], xmm2
0x18000a414  movdqa  [rsp+68h+var_18], xmm3
0x18000a41a  mov     rdx, rax
0x18000a41d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_4_dll
0x18000a424  call    __delayLoadHelper2
0x18000a429  movdqa  xmm0, [rsp+68h+var_48]
0x18000a42f  movdqa  xmm1, [rsp+68h+var_38]
0x18000a435  movdqa  xmm2, [rsp+68h+var_28]
0x18000a43b  movdqa  xmm3, [rsp+68h+var_18]
0x18000a441  mov     rcx, [rsp+68h+arg_0]
0x18000a446  mov     rdx, [rsp+68h+arg_8]
0x18000a44b  mov     r8, [rsp+68h+arg_10]
0x18000a453  mov     r9, [rsp+68h+arg_18]
0x18000a45b  add     rsp, 68h
0x18000a45f  jmp     short $+2
0x18000a461  jmp     rax
```
