# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x14000319d`
- end: `0x140003216`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000321c`

## callees

- `0x14000319d`
- `0x140018670`

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
0x14000319d  mov     [rsp+arg_0], rcx
0x1400031a2  mov     [rsp+arg_8], rdx
0x1400031a7  mov     [rsp+arg_10], r8
0x1400031ac  mov     [rsp+arg_18], r9
0x1400031b1  sub     rsp, 68h
0x1400031b5  movdqa  [rsp+68h+var_48], xmm0
0x1400031bb  movdqa  [rsp+68h+var_38], xmm1
0x1400031c1  movdqa  [rsp+68h+var_28], xmm2
0x1400031c7  movdqa  [rsp+68h+var_18], xmm3
0x1400031cd  mov     rdx, rax
0x1400031d0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x1400031d7  call    __delayLoadHelper2
0x1400031dc  movdqa  xmm0, [rsp+68h+var_48]
0x1400031e2  movdqa  xmm1, [rsp+68h+var_38]
0x1400031e8  movdqa  xmm2, [rsp+68h+var_28]
0x1400031ee  movdqa  xmm3, [rsp+68h+var_18]
0x1400031f4  mov     rcx, [rsp+68h+arg_0]
0x1400031f9  mov     rdx, [rsp+68h+arg_8]
0x1400031fe  mov     r8, [rsp+68h+arg_10]
0x140003206  mov     r9, [rsp+68h+arg_18]
0x14000320e  add     rsp, 68h
0x140003212  jmp     short $+2
0x140003214  jmp     rax
```
