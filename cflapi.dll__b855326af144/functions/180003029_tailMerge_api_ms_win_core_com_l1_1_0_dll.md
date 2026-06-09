# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180003029`
- end: `0x1800030a2`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030a8`
- `0x1800030ba`
- `0x1800030cc`
- `0x1800032c7`
- `0x180003595`
- `0x1800035a7`

## callees

- `0x180003029`
- `0x18002de50`

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
0x180003029  mov     [rsp+arg_0], rcx
0x18000302e  mov     [rsp+arg_8], rdx
0x180003033  mov     [rsp+arg_10], r8
0x180003038  mov     [rsp+arg_18], r9
0x18000303d  sub     rsp, 68h
0x180003041  movdqa  [rsp+68h+var_48], xmm0
0x180003047  movdqa  [rsp+68h+var_38], xmm1
0x18000304d  movdqa  [rsp+68h+var_28], xmm2
0x180003053  movdqa  [rsp+68h+var_18], xmm3
0x180003059  mov     rdx, rax
0x18000305c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180003063  call    __delayLoadHelper2
0x180003068  movdqa  xmm0, [rsp+68h+var_48]
0x18000306e  movdqa  xmm1, [rsp+68h+var_38]
0x180003074  movdqa  xmm2, [rsp+68h+var_28]
0x18000307a  movdqa  xmm3, [rsp+68h+var_18]
0x180003080  mov     rcx, [rsp+68h+arg_0]
0x180003085  mov     rdx, [rsp+68h+arg_8]
0x18000308a  mov     r8, [rsp+68h+arg_10]
0x180003092  mov     r9, [rsp+68h+arg_18]
0x18000309a  add     rsp, 68h
0x18000309e  jmp     short $+2
0x1800030a0  jmp     rax
```
