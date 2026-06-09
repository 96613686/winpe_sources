# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x180002c26`
- end: `0x180002c9f`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002ca5`

## callees

- `0x180002c26`
- `0x180030460`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002c26  mov     [rsp+arg_0], rcx
0x180002c2b  mov     [rsp+arg_8], rdx
0x180002c30  mov     [rsp+arg_10], r8
0x180002c35  mov     [rsp+arg_18], r9
0x180002c3a  sub     rsp, 68h
0x180002c3e  movdqa  [rsp+68h+var_48], xmm0
0x180002c44  movdqa  [rsp+68h+var_38], xmm1
0x180002c4a  movdqa  [rsp+68h+var_28], xmm2
0x180002c50  movdqa  [rsp+68h+var_18], xmm3
0x180002c56  mov     rdx, rax
0x180002c59  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x180002c60  call    __delayLoadHelper2
0x180002c65  movdqa  xmm0, [rsp+68h+var_48]
0x180002c6b  movdqa  xmm1, [rsp+68h+var_38]
0x180002c71  movdqa  xmm2, [rsp+68h+var_28]
0x180002c77  movdqa  xmm3, [rsp+68h+var_18]
0x180002c7d  mov     rcx, [rsp+68h+arg_0]
0x180002c82  mov     rdx, [rsp+68h+arg_8]
0x180002c87  mov     r8, [rsp+68h+arg_10]
0x180002c8f  mov     r9, [rsp+68h+arg_18]
0x180002c97  add     rsp, 68h
0x180002c9b  jmp     short $+2
0x180002c9d  jmp     rax
```
