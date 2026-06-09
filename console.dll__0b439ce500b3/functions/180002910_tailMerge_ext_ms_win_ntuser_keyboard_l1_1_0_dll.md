# __tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll

- ea: `0x180002910`
- end: `0x180002989`
- name: `__tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000298f`

## callees

- `0x180002910`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_keyboard_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002910  mov     [rsp+arg_0], rcx
0x180002915  mov     [rsp+arg_8], rdx
0x18000291a  mov     [rsp+arg_10], r8
0x18000291f  mov     [rsp+arg_18], r9
0x180002924  sub     rsp, 68h
0x180002928  movdqa  [rsp+68h+var_48], xmm0
0x18000292e  movdqa  [rsp+68h+var_38], xmm1
0x180002934  movdqa  [rsp+68h+var_28], xmm2
0x18000293a  movdqa  [rsp+68h+var_18], xmm3
0x180002940  mov     rdx, rax
0x180002943  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_keyboard_l1_1_0_dll
0x18000294a  call    __delayLoadHelper2
0x18000294f  movdqa  xmm0, [rsp+68h+var_48]
0x180002955  movdqa  xmm1, [rsp+68h+var_38]
0x18000295b  movdqa  xmm2, [rsp+68h+var_28]
0x180002961  movdqa  xmm3, [rsp+68h+var_18]
0x180002967  mov     rcx, [rsp+68h+arg_0]
0x18000296c  mov     rdx, [rsp+68h+arg_8]
0x180002971  mov     r8, [rsp+68h+arg_10]
0x180002979  mov     r9, [rsp+68h+arg_18]
0x180002981  add     rsp, 68h
0x180002985  jmp     short $+2
0x180002987  jmp     rax
```
