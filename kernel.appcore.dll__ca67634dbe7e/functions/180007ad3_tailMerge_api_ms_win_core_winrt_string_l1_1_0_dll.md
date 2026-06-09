# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x180007ad3`
- end: `0x180007b4c`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007b52`
- `0x180007cb0`
- `0x180007cc2`

## callees

- `0x180005080`
- `0x180007ad3`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180007ad3  mov     [rsp+arg_0], rcx
0x180007ad8  mov     [rsp+arg_8], rdx
0x180007add  mov     [rsp+arg_10], r8
0x180007ae2  mov     [rsp+arg_18], r9
0x180007ae7  sub     rsp, 68h
0x180007aeb  movdqa  [rsp+68h+var_48], xmm0
0x180007af1  movdqa  [rsp+68h+var_38], xmm1
0x180007af7  movdqa  [rsp+68h+var_28], xmm2
0x180007afd  movdqa  [rsp+68h+var_18], xmm3
0x180007b03  mov     rdx, rax
0x180007b06  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x180007b0d  call    __delayLoadHelper2
0x180007b12  movdqa  xmm0, [rsp+68h+var_48]
0x180007b18  movdqa  xmm1, [rsp+68h+var_38]
0x180007b1e  movdqa  xmm2, [rsp+68h+var_28]
0x180007b24  movdqa  xmm3, [rsp+68h+var_18]
0x180007b2a  mov     rcx, [rsp+68h+arg_0]
0x180007b2f  mov     rdx, [rsp+68h+arg_8]
0x180007b34  mov     r8, [rsp+68h+arg_10]
0x180007b3c  mov     r9, [rsp+68h+arg_18]
0x180007b44  add     rsp, 68h
0x180007b48  jmp     short $+2
0x180007b4a  jmp     rax
```
