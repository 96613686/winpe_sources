# __tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll

- ea: `0x18000a5f2`
- end: `0x18000a66b`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a671`

## callees

- `0x180007cb0`
- `0x18000a5f2`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a5f2  mov     [rsp+arg_0], rcx
0x18000a5f7  mov     [rsp+arg_8], rdx
0x18000a5fc  mov     [rsp+arg_10], r8
0x18000a601  mov     [rsp+arg_18], r9
0x18000a606  sub     rsp, 68h
0x18000a60a  movdqa  [rsp+68h+var_48], xmm0
0x18000a610  movdqa  [rsp+68h+var_38], xmm1
0x18000a616  movdqa  [rsp+68h+var_28], xmm2
0x18000a61c  movdqa  [rsp+68h+var_18], xmm3
0x18000a622  mov     rdx, rax
0x18000a625  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_2_dll
0x18000a62c  call    __delayLoadHelper2
0x18000a631  movdqa  xmm0, [rsp+68h+var_48]
0x18000a637  movdqa  xmm1, [rsp+68h+var_38]
0x18000a63d  movdqa  xmm2, [rsp+68h+var_28]
0x18000a643  movdqa  xmm3, [rsp+68h+var_18]
0x18000a649  mov     rcx, [rsp+68h+arg_0]
0x18000a64e  mov     rdx, [rsp+68h+arg_8]
0x18000a653  mov     r8, [rsp+68h+arg_10]
0x18000a65b  mov     r9, [rsp+68h+arg_18]
0x18000a663  add     rsp, 68h
0x18000a667  jmp     short $+2
0x18000a669  jmp     rax
```
