# __tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll

- ea: `0x140003d22`
- end: `0x140003d9b`
- name: `__tailMerge_ext_ms_win_devmgmt_policy_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140003da1`

## callees

- `0x140003d22`
- `0x1400183b0`

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
0x140003d22  mov     [rsp+arg_0], rcx
0x140003d27  mov     [rsp+arg_8], rdx
0x140003d2c  mov     [rsp+arg_10], r8
0x140003d31  mov     [rsp+arg_18], r9
0x140003d36  sub     rsp, 68h
0x140003d3a  movdqa  [rsp+68h+var_48], xmm0
0x140003d40  movdqa  [rsp+68h+var_38], xmm1
0x140003d46  movdqa  [rsp+68h+var_28], xmm2
0x140003d4c  movdqa  [rsp+68h+var_18], xmm3
0x140003d52  mov     rdx, rax
0x140003d55  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_devmgmt_policy_l1_1_0_dll
0x140003d5c  call    __delayLoadHelper2
0x140003d61  movdqa  xmm0, [rsp+68h+var_48]
0x140003d67  movdqa  xmm1, [rsp+68h+var_38]
0x140003d6d  movdqa  xmm2, [rsp+68h+var_28]
0x140003d73  movdqa  xmm3, [rsp+68h+var_18]
0x140003d79  mov     rcx, [rsp+68h+arg_0]
0x140003d7e  mov     rdx, [rsp+68h+arg_8]
0x140003d83  mov     r8, [rsp+68h+arg_10]
0x140003d8b  mov     r9, [rsp+68h+arg_18]
0x140003d93  add     rsp, 68h
0x140003d97  jmp     short $+2
0x140003d99  jmp     rax
```
