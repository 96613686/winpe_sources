# __tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll

- ea: `0x180001b10`
- end: `0x180001b89`
- name: `__tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b8f`
- `0x180001ba1`

## callees

- `0x180001b10`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_gui_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001b10  mov     [rsp+arg_0], rcx
0x180001b15  mov     [rsp+arg_8], rdx
0x180001b1a  mov     [rsp+arg_10], r8
0x180001b1f  mov     [rsp+arg_18], r9
0x180001b24  sub     rsp, 68h
0x180001b28  movdqa  [rsp+68h+var_48], xmm0
0x180001b2e  movdqa  [rsp+68h+var_38], xmm1
0x180001b34  movdqa  [rsp+68h+var_28], xmm2
0x180001b3a  movdqa  [rsp+68h+var_18], xmm3
0x180001b40  mov     rdx, rax
0x180001b43  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_gui_l1_1_0_dll
0x180001b4a  call    __delayLoadHelper2
0x180001b4f  movdqa  xmm0, [rsp+68h+var_48]
0x180001b55  movdqa  xmm1, [rsp+68h+var_38]
0x180001b5b  movdqa  xmm2, [rsp+68h+var_28]
0x180001b61  movdqa  xmm3, [rsp+68h+var_18]
0x180001b67  mov     rcx, [rsp+68h+arg_0]
0x180001b6c  mov     rdx, [rsp+68h+arg_8]
0x180001b71  mov     r8, [rsp+68h+arg_10]
0x180001b79  mov     r9, [rsp+68h+arg_18]
0x180001b81  add     rsp, 68h
0x180001b85  jmp     short $+2
0x180001b87  jmp     rax
```
