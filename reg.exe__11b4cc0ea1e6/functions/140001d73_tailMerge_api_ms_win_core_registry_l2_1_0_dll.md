# __tailMerge_api_ms_win_core_registry_l2_1_0_dll

- ea: `0x140001d73`
- end: `0x140001dec`
- name: `__tailMerge_api_ms_win_core_registry_l2_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140001df2`

## callees

- `0x140001d73`
- `0x14000ec80`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_registry_l2_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001d73  mov     [rsp+arg_0], rcx
0x140001d78  mov     [rsp+arg_8], rdx
0x140001d7d  mov     [rsp+arg_10], r8
0x140001d82  mov     [rsp+arg_18], r9
0x140001d87  sub     rsp, 68h
0x140001d8b  movdqa  [rsp+68h+var_48], xmm0
0x140001d91  movdqa  [rsp+68h+var_38], xmm1
0x140001d97  movdqa  [rsp+68h+var_28], xmm2
0x140001d9d  movdqa  [rsp+68h+var_18], xmm3
0x140001da3  mov     rdx, rax
0x140001da6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_registry_l2_1_0_dll
0x140001dad  call    __delayLoadHelper2
0x140001db2  movdqa  xmm0, [rsp+68h+var_48]
0x140001db8  movdqa  xmm1, [rsp+68h+var_38]
0x140001dbe  movdqa  xmm2, [rsp+68h+var_28]
0x140001dc4  movdqa  xmm3, [rsp+68h+var_18]
0x140001dca  mov     rcx, [rsp+68h+arg_0]
0x140001dcf  mov     rdx, [rsp+68h+arg_8]
0x140001dd4  mov     r8, [rsp+68h+arg_10]
0x140001ddc  mov     r9, [rsp+68h+arg_18]
0x140001de4  add     rsp, 68h
0x140001de8  jmp     short $+2
0x140001dea  jmp     rax
```
