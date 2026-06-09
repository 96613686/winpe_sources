# __tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll

- ea: `0x18000a9c4`
- end: `0x18000aa3d`
- name: `__tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa43`
- `0x18000aa55`

## callees

- `0x180007cb0`
- `0x18000a9c4`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a9c4  mov     [rsp+arg_0], rcx
0x18000a9c9  mov     [rsp+arg_8], rdx
0x18000a9ce  mov     [rsp+arg_10], r8
0x18000a9d3  mov     [rsp+arg_18], r9
0x18000a9d8  sub     rsp, 68h
0x18000a9dc  movdqa  [rsp+68h+var_48], xmm0
0x18000a9e2  movdqa  [rsp+68h+var_38], xmm1
0x18000a9e8  movdqa  [rsp+68h+var_28], xmm2
0x18000a9ee  movdqa  [rsp+68h+var_18], xmm3
0x18000a9f4  mov     rdx, rax
0x18000a9f7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_rtcore_ntuser_cursor_l1_1_0_dll
0x18000a9fe  call    __delayLoadHelper2
0x18000aa03  movdqa  xmm0, [rsp+68h+var_48]
0x18000aa09  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa0f  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa15  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa1b  mov     rcx, [rsp+68h+arg_0]
0x18000aa20  mov     rdx, [rsp+68h+arg_8]
0x18000aa25  mov     r8, [rsp+68h+arg_10]
0x18000aa2d  mov     r9, [rsp+68h+arg_18]
0x18000aa35  add     rsp, 68h
0x18000aa39  jmp     short $+2
0x18000aa3b  jmp     rax
```
