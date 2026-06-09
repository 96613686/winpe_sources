# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x1800021ab`
- end: `0x180002224`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000222a`

## callees

- `0x1800021ab`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021ab  mov     [rsp+arg_0], rcx
0x1800021b0  mov     [rsp+arg_8], rdx
0x1800021b5  mov     [rsp+arg_10], r8
0x1800021ba  mov     [rsp+arg_18], r9
0x1800021bf  sub     rsp, 68h
0x1800021c3  movdqa  [rsp+68h+var_48], xmm0
0x1800021c9  movdqa  [rsp+68h+var_38], xmm1
0x1800021cf  movdqa  [rsp+68h+var_28], xmm2
0x1800021d5  movdqa  [rsp+68h+var_18], xmm3
0x1800021db  mov     rdx, rax
0x1800021de  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x1800021e5  call    __delayLoadHelper2
0x1800021ea  movdqa  xmm0, [rsp+68h+var_48]
0x1800021f0  movdqa  xmm1, [rsp+68h+var_38]
0x1800021f6  movdqa  xmm2, [rsp+68h+var_28]
0x1800021fc  movdqa  xmm3, [rsp+68h+var_18]
0x180002202  mov     rcx, [rsp+68h+arg_0]
0x180002207  mov     rdx, [rsp+68h+arg_8]
0x18000220c  mov     r8, [rsp+68h+arg_10]
0x180002214  mov     r9, [rsp+68h+arg_18]
0x18000221c  add     rsp, 68h
0x180002220  jmp     short $+2
0x180002222  jmp     rax
```
