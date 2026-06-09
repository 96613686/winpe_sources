# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180002a3e`
- end: `0x180002ab7`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002abd`
- `0x180002acf`
- `0x180002b6c`
- `0x180002c94`
- `0x180002ca6`
- `0x180002d43`

## callees

- `0x180002a3e`
- `0x18000d4b0`

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
0x180002a3e  mov     [rsp+arg_0], rcx
0x180002a43  mov     [rsp+arg_8], rdx
0x180002a48  mov     [rsp+arg_10], r8
0x180002a4d  mov     [rsp+arg_18], r9
0x180002a52  sub     rsp, 68h
0x180002a56  movdqa  [rsp+68h+var_48], xmm0
0x180002a5c  movdqa  [rsp+68h+var_38], xmm1
0x180002a62  movdqa  [rsp+68h+var_28], xmm2
0x180002a68  movdqa  [rsp+68h+var_18], xmm3
0x180002a6e  mov     rdx, rax
0x180002a71  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180002a78  call    __delayLoadHelper2
0x180002a7d  movdqa  xmm0, [rsp+68h+var_48]
0x180002a83  movdqa  xmm1, [rsp+68h+var_38]
0x180002a89  movdqa  xmm2, [rsp+68h+var_28]
0x180002a8f  movdqa  xmm3, [rsp+68h+var_18]
0x180002a95  mov     rcx, [rsp+68h+arg_0]
0x180002a9a  mov     rdx, [rsp+68h+arg_8]
0x180002a9f  mov     r8, [rsp+68h+arg_10]
0x180002aa7  mov     r9, [rsp+68h+arg_18]
0x180002aaf  add     rsp, 68h
0x180002ab3  jmp     short $+2
0x180002ab5  jmp     rax
```
