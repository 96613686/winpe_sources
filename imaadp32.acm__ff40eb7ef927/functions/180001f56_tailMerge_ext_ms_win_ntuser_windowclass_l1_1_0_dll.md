# __tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll

- ea: `0x180001f56`
- end: `0x180001fcf`
- name: `__tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001fd5`
- `0x180001fe7`

## callees

- `0x180001f56`
- `0x180004f50`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_windowclass_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f56  mov     [rsp+arg_0], rcx
0x180001f5b  mov     [rsp+arg_8], rdx
0x180001f60  mov     [rsp+arg_10], r8
0x180001f65  mov     [rsp+arg_18], r9
0x180001f6a  sub     rsp, 68h
0x180001f6e  movdqa  [rsp+68h+var_48], xmm0
0x180001f74  movdqa  [rsp+68h+var_38], xmm1
0x180001f7a  movdqa  [rsp+68h+var_28], xmm2
0x180001f80  movdqa  [rsp+68h+var_18], xmm3
0x180001f86  mov     rdx, rax
0x180001f89  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_windowclass_l1_1_0_dll
0x180001f90  call    __delayLoadHelper2
0x180001f95  movdqa  xmm0, [rsp+68h+var_48]
0x180001f9b  movdqa  xmm1, [rsp+68h+var_38]
0x180001fa1  movdqa  xmm2, [rsp+68h+var_28]
0x180001fa7  movdqa  xmm3, [rsp+68h+var_18]
0x180001fad  mov     rcx, [rsp+68h+arg_0]
0x180001fb2  mov     rdx, [rsp+68h+arg_8]
0x180001fb7  mov     r8, [rsp+68h+arg_10]
0x180001fbf  mov     r9, [rsp+68h+arg_18]
0x180001fc7  add     rsp, 68h
0x180001fcb  jmp     short $+2
0x180001fcd  jmp     rax
```
