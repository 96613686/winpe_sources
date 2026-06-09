# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180005baa`
- end: `0x180005c23`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005c29`
- `0x180005c3b`

## callees

- `0x1800023e0`
- `0x180005baa`

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
0x180005baa  mov     [rsp+arg_0], rcx
0x180005baf  mov     [rsp+arg_8], rdx
0x180005bb4  mov     [rsp+arg_10], r8
0x180005bb9  mov     [rsp+arg_18], r9
0x180005bbe  sub     rsp, 68h
0x180005bc2  movdqa  [rsp+68h+var_48], xmm0
0x180005bc8  movdqa  [rsp+68h+var_38], xmm1
0x180005bce  movdqa  [rsp+68h+var_28], xmm2
0x180005bd4  movdqa  [rsp+68h+var_18], xmm3
0x180005bda  mov     rdx, rax
0x180005bdd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180005be4  call    __delayLoadHelper2
0x180005be9  movdqa  xmm0, [rsp+68h+var_48]
0x180005bef  movdqa  xmm1, [rsp+68h+var_38]
0x180005bf5  movdqa  xmm2, [rsp+68h+var_28]
0x180005bfb  movdqa  xmm3, [rsp+68h+var_18]
0x180005c01  mov     rcx, [rsp+68h+arg_0]
0x180005c06  mov     rdx, [rsp+68h+arg_8]
0x180005c0b  mov     r8, [rsp+68h+arg_10]
0x180005c13  mov     r9, [rsp+68h+arg_18]
0x180005c1b  add     rsp, 68h
0x180005c1f  jmp     short $+2
0x180005c21  jmp     rax
```
