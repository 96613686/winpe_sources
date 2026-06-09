# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll

- ea: `0x180009ebc`
- end: `0x180009f35`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009f3b`

## callees

- `0x180007cb0`
- `0x180009ebc`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009ebc  mov     [rsp+arg_0], rcx
0x180009ec1  mov     [rsp+arg_8], rdx
0x180009ec6  mov     [rsp+arg_10], r8
0x180009ecb  mov     [rsp+arg_18], r9
0x180009ed0  sub     rsp, 68h
0x180009ed4  movdqa  [rsp+68h+var_48], xmm0
0x180009eda  movdqa  [rsp+68h+var_38], xmm1
0x180009ee0  movdqa  [rsp+68h+var_28], xmm2
0x180009ee6  movdqa  [rsp+68h+var_18], xmm3
0x180009eec  mov     rdx, rax
0x180009eef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_1_dll
0x180009ef6  call    __delayLoadHelper2
0x180009efb  movdqa  xmm0, [rsp+68h+var_48]
0x180009f01  movdqa  xmm1, [rsp+68h+var_38]
0x180009f07  movdqa  xmm2, [rsp+68h+var_28]
0x180009f0d  movdqa  xmm3, [rsp+68h+var_18]
0x180009f13  mov     rcx, [rsp+68h+arg_0]
0x180009f18  mov     rdx, [rsp+68h+arg_8]
0x180009f1d  mov     r8, [rsp+68h+arg_10]
0x180009f25  mov     r9, [rsp+68h+arg_18]
0x180009f2d  add     rsp, 68h
0x180009f31  jmp     short $+2
0x180009f33  jmp     rax
```
