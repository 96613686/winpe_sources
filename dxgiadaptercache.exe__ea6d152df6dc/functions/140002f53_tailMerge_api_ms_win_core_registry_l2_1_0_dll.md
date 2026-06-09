# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x140002f53`
- end: `0x140002fcc`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140002fd2`
- `0x140002fe4`
- `0x140002ff6`

## callees

- `0x140002f53`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002f53  mov     [rsp+arg_0], rcx
0x140002f58  mov     [rsp+arg_8], rdx
0x140002f5d  mov     [rsp+arg_10], r8
0x140002f62  mov     [rsp+arg_18], r9
0x140002f67  sub     rsp, 68h
0x140002f6b  movdqa  [rsp+68h+var_48], xmm0
0x140002f71  movdqa  [rsp+68h+var_38], xmm1
0x140002f77  movdqa  [rsp+68h+var_28], xmm2
0x140002f7d  movdqa  [rsp+68h+var_18], xmm3
0x140002f83  mov     rdx, rax
0x140002f86  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x140002f8d  call    __delayLoadHelper2
0x140002f92  movdqa  xmm0, [rsp+68h+var_48]
0x140002f98  movdqa  xmm1, [rsp+68h+var_38]
0x140002f9e  movdqa  xmm2, [rsp+68h+var_28]
0x140002fa4  movdqa  xmm3, [rsp+68h+var_18]
0x140002faa  mov     rcx, [rsp+68h+arg_0]
0x140002faf  mov     rdx, [rsp+68h+arg_8]
0x140002fb4  mov     r8, [rsp+68h+arg_10]
0x140002fbc  mov     r9, [rsp+68h+arg_18]
0x140002fc4  add     rsp, 68h
0x140002fc8  jmp     short $+2
0x140002fca  jmp     rax
```
