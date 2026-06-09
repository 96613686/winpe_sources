# __tailMerge_ext_ms_win_core_psm_service_l1_1_5_dll

- ea: `0x18001c477`
- end: `0x18001c4f0`
- name: `__tailMerge_ext_ms_win_core_psm_service_l1_1_5_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001c4f6`
- `0x18001c508`

## callees

- `0x1800174f0`
- `0x18001c477`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_service_l1_1_5_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_5_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c477  mov     [rsp+arg_0], rcx
0x18001c47c  mov     [rsp+arg_8], rdx
0x18001c481  mov     [rsp+arg_10], r8
0x18001c486  mov     [rsp+arg_18], r9
0x18001c48b  sub     rsp, 68h
0x18001c48f  movdqa  [rsp+68h+var_48], xmm0
0x18001c495  movdqa  [rsp+68h+var_38], xmm1
0x18001c49b  movdqa  [rsp+68h+var_28], xmm2
0x18001c4a1  movdqa  [rsp+68h+var_18], xmm3
0x18001c4a7  mov     rdx, rax
0x18001c4aa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_5_dll
0x18001c4b1  call    __delayLoadHelper2
0x18001c4b6  movdqa  xmm0, [rsp+68h+var_48]
0x18001c4bc  movdqa  xmm1, [rsp+68h+var_38]
0x18001c4c2  movdqa  xmm2, [rsp+68h+var_28]
0x18001c4c8  movdqa  xmm3, [rsp+68h+var_18]
0x18001c4ce  mov     rcx, [rsp+68h+arg_0]
0x18001c4d3  mov     rdx, [rsp+68h+arg_8]
0x18001c4d8  mov     r8, [rsp+68h+arg_10]
0x18001c4e0  mov     r9, [rsp+68h+arg_18]
0x18001c4e8  add     rsp, 68h
0x18001c4ec  jmp     short $+2
0x18001c4ee  jmp     rax
```
