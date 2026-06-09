# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000c9ac`
- end: `0x18000ca25`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca2b`
- `0x18000cb9b`
- `0x18000cbad`

## callees

- `0x18000c9ac`
- `0x1800213a0`

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
0x18000c9ac  mov     [rsp+arg_0], rcx
0x18000c9b1  mov     [rsp+arg_8], rdx
0x18000c9b6  mov     [rsp+arg_10], r8
0x18000c9bb  mov     [rsp+arg_18], r9
0x18000c9c0  sub     rsp, 68h
0x18000c9c4  movdqa  [rsp+68h+var_48], xmm0
0x18000c9ca  movdqa  [rsp+68h+var_38], xmm1
0x18000c9d0  movdqa  [rsp+68h+var_28], xmm2
0x18000c9d6  movdqa  [rsp+68h+var_18], xmm3
0x18000c9dc  mov     rdx, rax
0x18000c9df  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000c9e6  call    __delayLoadHelper2
0x18000c9eb  movdqa  xmm0, [rsp+68h+var_48]
0x18000c9f1  movdqa  xmm1, [rsp+68h+var_38]
0x18000c9f7  movdqa  xmm2, [rsp+68h+var_28]
0x18000c9fd  movdqa  xmm3, [rsp+68h+var_18]
0x18000ca03  mov     rcx, [rsp+68h+arg_0]
0x18000ca08  mov     rdx, [rsp+68h+arg_8]
0x18000ca0d  mov     r8, [rsp+68h+arg_10]
0x18000ca15  mov     r9, [rsp+68h+arg_18]
0x18000ca1d  add     rsp, 68h
0x18000ca21  jmp     short $+2
0x18000ca23  jmp     rax
```
