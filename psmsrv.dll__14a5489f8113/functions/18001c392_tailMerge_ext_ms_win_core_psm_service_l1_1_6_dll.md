# __tailMerge_ext_ms_win_core_psm_service_l1_1_6_dll

- ea: `0x18001c392`
- end: `0x18001c40b`
- name: `__tailMerge_ext_ms_win_core_psm_service_l1_1_6_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001c411`
- `0x18001c459`

## callees

- `0x1800174f0`
- `0x18001c392`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_service_l1_1_6_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_6_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c392  mov     [rsp+arg_0], rcx
0x18001c397  mov     [rsp+arg_8], rdx
0x18001c39c  mov     [rsp+arg_10], r8
0x18001c3a1  mov     [rsp+arg_18], r9
0x18001c3a6  sub     rsp, 68h
0x18001c3aa  movdqa  [rsp+68h+var_48], xmm0
0x18001c3b0  movdqa  [rsp+68h+var_38], xmm1
0x18001c3b6  movdqa  [rsp+68h+var_28], xmm2
0x18001c3bc  movdqa  [rsp+68h+var_18], xmm3
0x18001c3c2  mov     rdx, rax
0x18001c3c5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_6_dll
0x18001c3cc  call    __delayLoadHelper2
0x18001c3d1  movdqa  xmm0, [rsp+68h+var_48]
0x18001c3d7  movdqa  xmm1, [rsp+68h+var_38]
0x18001c3dd  movdqa  xmm2, [rsp+68h+var_28]
0x18001c3e3  movdqa  xmm3, [rsp+68h+var_18]
0x18001c3e9  mov     rcx, [rsp+68h+arg_0]
0x18001c3ee  mov     rdx, [rsp+68h+arg_8]
0x18001c3f3  mov     r8, [rsp+68h+arg_10]
0x18001c3fb  mov     r9, [rsp+68h+arg_18]
0x18001c403  add     rsp, 68h
0x18001c407  jmp     short $+2
0x18001c409  jmp     rax
```
