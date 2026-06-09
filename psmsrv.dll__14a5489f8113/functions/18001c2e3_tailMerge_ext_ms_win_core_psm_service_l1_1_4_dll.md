# __tailMerge_ext_ms_win_core_psm_service_l1_1_4_dll

- ea: `0x18001c2e3`
- end: `0x18001c35c`
- name: `__tailMerge_ext_ms_win_core_psm_service_l1_1_4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001c362`
- `0x18001c374`
- `0x18001c423`

## callees

- `0x1800174f0`
- `0x18001c2e3`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_service_l1_1_4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c2e3  mov     [rsp+arg_0], rcx
0x18001c2e8  mov     [rsp+arg_8], rdx
0x18001c2ed  mov     [rsp+arg_10], r8
0x18001c2f2  mov     [rsp+arg_18], r9
0x18001c2f7  sub     rsp, 68h
0x18001c2fb  movdqa  [rsp+68h+var_48], xmm0
0x18001c301  movdqa  [rsp+68h+var_38], xmm1
0x18001c307  movdqa  [rsp+68h+var_28], xmm2
0x18001c30d  movdqa  [rsp+68h+var_18], xmm3
0x18001c313  mov     rdx, rax
0x18001c316  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_4_dll
0x18001c31d  call    __delayLoadHelper2
0x18001c322  movdqa  xmm0, [rsp+68h+var_48]
0x18001c328  movdqa  xmm1, [rsp+68h+var_38]
0x18001c32e  movdqa  xmm2, [rsp+68h+var_28]
0x18001c334  movdqa  xmm3, [rsp+68h+var_18]
0x18001c33a  mov     rcx, [rsp+68h+arg_0]
0x18001c33f  mov     rdx, [rsp+68h+arg_8]
0x18001c344  mov     r8, [rsp+68h+arg_10]
0x18001c34c  mov     r9, [rsp+68h+arg_18]
0x18001c354  add     rsp, 68h
0x18001c358  jmp     short $+2
0x18001c35a  jmp     rax
```
