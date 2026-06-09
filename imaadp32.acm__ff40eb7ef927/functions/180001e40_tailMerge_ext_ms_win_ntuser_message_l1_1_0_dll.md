# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x180001e40`
- end: `0x180001eb9`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ebf`

## callees

- `0x180001e40`
- `0x180004f50`

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
0x180001e40  mov     [rsp+arg_0], rcx
0x180001e45  mov     [rsp+arg_8], rdx
0x180001e4a  mov     [rsp+arg_10], r8
0x180001e4f  mov     [rsp+arg_18], r9
0x180001e54  sub     rsp, 68h
0x180001e58  movdqa  [rsp+68h+var_48], xmm0
0x180001e5e  movdqa  [rsp+68h+var_38], xmm1
0x180001e64  movdqa  [rsp+68h+var_28], xmm2
0x180001e6a  movdqa  [rsp+68h+var_18], xmm3
0x180001e70  mov     rdx, rax
0x180001e73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x180001e7a  call    __delayLoadHelper2
0x180001e7f  movdqa  xmm0, [rsp+68h+var_48]
0x180001e85  movdqa  xmm1, [rsp+68h+var_38]
0x180001e8b  movdqa  xmm2, [rsp+68h+var_28]
0x180001e91  movdqa  xmm3, [rsp+68h+var_18]
0x180001e97  mov     rcx, [rsp+68h+arg_0]
0x180001e9c  mov     rdx, [rsp+68h+arg_8]
0x180001ea1  mov     r8, [rsp+68h+arg_10]
0x180001ea9  mov     r9, [rsp+68h+arg_18]
0x180001eb1  add     rsp, 68h
0x180001eb5  jmp     short $+2
0x180001eb7  jmp     rax
```
