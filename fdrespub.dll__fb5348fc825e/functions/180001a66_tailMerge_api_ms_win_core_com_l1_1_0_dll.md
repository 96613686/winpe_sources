# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180001a66`
- end: `0x180001adf`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ae5`
- `0x180001af7`
- `0x180001b09`

## callees

- `0x180001a66`
- `0x180005170`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001a66  mov     [rsp+arg_0], rcx
0x180001a6b  mov     [rsp+arg_8], rdx
0x180001a70  mov     [rsp+arg_10], r8
0x180001a75  mov     [rsp+arg_18], r9
0x180001a7a  sub     rsp, 68h
0x180001a7e  movdqa  [rsp+68h+var_48], xmm0
0x180001a84  movdqa  [rsp+68h+var_38], xmm1
0x180001a8a  movdqa  [rsp+68h+var_28], xmm2
0x180001a90  movdqa  [rsp+68h+var_18], xmm3
0x180001a96  mov     rdx, rax
0x180001a99  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180001aa0  call    __delayLoadHelper2
0x180001aa5  movdqa  xmm0, [rsp+68h+var_48]
0x180001aab  movdqa  xmm1, [rsp+68h+var_38]
0x180001ab1  movdqa  xmm2, [rsp+68h+var_28]
0x180001ab7  movdqa  xmm3, [rsp+68h+var_18]
0x180001abd  mov     rcx, [rsp+68h+arg_0]
0x180001ac2  mov     rdx, [rsp+68h+arg_8]
0x180001ac7  mov     r8, [rsp+68h+arg_10]
0x180001acf  mov     r9, [rsp+68h+arg_18]
0x180001ad7  add     rsp, 68h
0x180001adb  jmp     short $+2
0x180001add  jmp     rax
```
