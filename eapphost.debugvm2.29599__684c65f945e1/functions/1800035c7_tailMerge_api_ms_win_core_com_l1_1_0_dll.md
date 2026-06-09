# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x1800035c7`
- end: `0x180003640`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003646`
- `0x180003658`
- `0x18000366a`
- `0x18000367c`
- `0x18000368e`
- `0x1800036a0`
- `0x1800036b2`
- `0x1800036d6`
- `0x1800036e8`
- `0x1800036fa`
- `0x18000372c`
- `0x18000373e`

## callees

- `0x1800035c7`
- `0x180033bc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800035c7  mov     [rsp+arg_0], rcx
0x1800035cc  mov     [rsp+arg_8], rdx
0x1800035d1  mov     [rsp+arg_10], r8
0x1800035d6  mov     [rsp+arg_18], r9
0x1800035db  sub     rsp, 68h
0x1800035df  movdqa  [rsp+68h+var_48], xmm0
0x1800035e5  movdqa  [rsp+68h+var_38], xmm1
0x1800035eb  movdqa  [rsp+68h+var_28], xmm2
0x1800035f1  movdqa  [rsp+68h+var_18], xmm3
0x1800035f7  mov     rdx, rax
0x1800035fa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180003601  call    __delayLoadHelper2
0x180003606  movdqa  xmm0, [rsp+68h+var_48]
0x18000360c  movdqa  xmm1, [rsp+68h+var_38]
0x180003612  movdqa  xmm2, [rsp+68h+var_28]
0x180003618  movdqa  xmm3, [rsp+68h+var_18]
0x18000361e  mov     rcx, [rsp+68h+arg_0]
0x180003623  mov     rdx, [rsp+68h+arg_8]
0x180003628  mov     r8, [rsp+68h+arg_10]
0x180003630  mov     r9, [rsp+68h+arg_18]
0x180003638  add     rsp, 68h
0x18000363c  jmp     short $+2
0x18000363e  jmp     rax
```
