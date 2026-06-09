# __tailMerge_api_ms_win_devices_config_l1_1_1_dll

- ea: `0x180016dad`
- end: `0x180016e26`
- name: `__tailMerge_api_ms_win_devices_config_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016e2c`
- `0x180016e3e`
- `0x180016e50`

## callees

- `0x18000e1a0`
- `0x180016dad`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_devices_config_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180016dad  mov     [rsp+arg_0], rcx
0x180016db2  mov     [rsp+arg_8], rdx
0x180016db7  mov     [rsp+arg_10], r8
0x180016dbc  mov     [rsp+arg_18], r9
0x180016dc1  sub     rsp, 68h
0x180016dc5  movdqa  [rsp+68h+var_48], xmm0
0x180016dcb  movdqa  [rsp+68h+var_38], xmm1
0x180016dd1  movdqa  [rsp+68h+var_28], xmm2
0x180016dd7  movdqa  [rsp+68h+var_18], xmm3
0x180016ddd  mov     rdx, rax
0x180016de0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_devices_config_l1_1_1_dll
0x180016de7  call    __delayLoadHelper2
0x180016dec  movdqa  xmm0, [rsp+68h+var_48]
0x180016df2  movdqa  xmm1, [rsp+68h+var_38]
0x180016df8  movdqa  xmm2, [rsp+68h+var_28]
0x180016dfe  movdqa  xmm3, [rsp+68h+var_18]
0x180016e04  mov     rcx, [rsp+68h+arg_0]
0x180016e09  mov     rdx, [rsp+68h+arg_8]
0x180016e0e  mov     r8, [rsp+68h+arg_10]
0x180016e16  mov     r9, [rsp+68h+arg_18]
0x180016e1e  add     rsp, 68h
0x180016e22  jmp     short $+2
0x180016e24  jmp     rax
```
