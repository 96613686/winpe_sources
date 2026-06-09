# __tailMerge_ext_ms_win_core_psm_service_l1_1_2_dll

- ea: `0x18001c246`
- end: `0x18001c2bf`
- name: `__tailMerge_ext_ms_win_core_psm_service_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001c2c5`
- `0x18001c2d7`
- `0x18001c386`
- `0x18001c435`
- `0x18001c447`
- `0x18001c46b`

## callees

- `0x1800174f0`
- `0x18001c246`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_core_psm_service_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c246  mov     [rsp+arg_0], rcx
0x18001c24b  mov     [rsp+arg_8], rdx
0x18001c250  mov     [rsp+arg_10], r8
0x18001c255  mov     [rsp+arg_18], r9
0x18001c25a  sub     rsp, 68h
0x18001c25e  movdqa  [rsp+68h+var_48], xmm0
0x18001c264  movdqa  [rsp+68h+var_38], xmm1
0x18001c26a  movdqa  [rsp+68h+var_28], xmm2
0x18001c270  movdqa  [rsp+68h+var_18], xmm3
0x18001c276  mov     rdx, rax
0x18001c279  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_core_psm_service_l1_1_2_dll
0x18001c280  call    __delayLoadHelper2
0x18001c285  movdqa  xmm0, [rsp+68h+var_48]
0x18001c28b  movdqa  xmm1, [rsp+68h+var_38]
0x18001c291  movdqa  xmm2, [rsp+68h+var_28]
0x18001c297  movdqa  xmm3, [rsp+68h+var_18]
0x18001c29d  mov     rcx, [rsp+68h+arg_0]
0x18001c2a2  mov     rdx, [rsp+68h+arg_8]
0x18001c2a7  mov     r8, [rsp+68h+arg_10]
0x18001c2af  mov     r9, [rsp+68h+arg_18]
0x18001c2b7  add     rsp, 68h
0x18001c2bb  jmp     short $+2
0x18001c2bd  jmp     rax
```
