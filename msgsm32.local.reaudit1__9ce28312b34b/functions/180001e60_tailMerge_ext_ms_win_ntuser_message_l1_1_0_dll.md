# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x180001e60`
- end: `0x180001ed9`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001edf`

## callees

- `0x180001e60`
- `0x1800063b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e60  mov     [rsp+arg_0], rcx
0x180001e65  mov     [rsp+arg_8], rdx
0x180001e6a  mov     [rsp+arg_10], r8
0x180001e6f  mov     [rsp+arg_18], r9
0x180001e74  sub     rsp, 68h
0x180001e78  movdqa  [rsp+68h+var_48], xmm0
0x180001e7e  movdqa  [rsp+68h+var_38], xmm1
0x180001e84  movdqa  [rsp+68h+var_28], xmm2
0x180001e8a  movdqa  [rsp+68h+var_18], xmm3
0x180001e90  mov     rdx, rax
0x180001e93  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x180001e9a  call    __delayLoadHelper2
0x180001e9f  movdqa  xmm0, [rsp+68h+var_48]
0x180001ea5  movdqa  xmm1, [rsp+68h+var_38]
0x180001eab  movdqa  xmm2, [rsp+68h+var_28]
0x180001eb1  movdqa  xmm3, [rsp+68h+var_18]
0x180001eb7  mov     rcx, [rsp+68h+arg_0]
0x180001ebc  mov     rdx, [rsp+68h+arg_8]
0x180001ec1  mov     r8, [rsp+68h+arg_10]
0x180001ec9  mov     r9, [rsp+68h+arg_18]
0x180001ed1  add     rsp, 68h
0x180001ed5  jmp     short $+2
0x180001ed7  jmp     rax
```
