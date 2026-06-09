# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000210c`
- end: `0x180002185`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000218b`
- `0x18000219d`
- `0x1800021af`
- `0x1800021c1`
- `0x1800021d3`

## callees

- `0x18000210c`
- `0x18000dd70`

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
0x18000210c  mov     [rsp+arg_0], rcx
0x180002111  mov     [rsp+arg_8], rdx
0x180002116  mov     [rsp+arg_10], r8
0x18000211b  mov     [rsp+arg_18], r9
0x180002120  sub     rsp, 68h
0x180002124  movdqa  [rsp+68h+var_48], xmm0
0x18000212a  movdqa  [rsp+68h+var_38], xmm1
0x180002130  movdqa  [rsp+68h+var_28], xmm2
0x180002136  movdqa  [rsp+68h+var_18], xmm3
0x18000213c  mov     rdx, rax
0x18000213f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180002146  call    __delayLoadHelper2
0x18000214b  movdqa  xmm0, [rsp+68h+var_48]
0x180002151  movdqa  xmm1, [rsp+68h+var_38]
0x180002157  movdqa  xmm2, [rsp+68h+var_28]
0x18000215d  movdqa  xmm3, [rsp+68h+var_18]
0x180002163  mov     rcx, [rsp+68h+arg_0]
0x180002168  mov     rdx, [rsp+68h+arg_8]
0x18000216d  mov     r8, [rsp+68h+arg_10]
0x180002175  mov     r9, [rsp+68h+arg_18]
0x18000217d  add     rsp, 68h
0x180002181  jmp     short $+2
0x180002183  jmp     rax
```
