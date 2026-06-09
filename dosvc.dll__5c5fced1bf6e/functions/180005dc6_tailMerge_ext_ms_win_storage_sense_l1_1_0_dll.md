# __tailMerge_ext_ms_win_storage_sense_l1_1_0_dll

- ea: `0x180005dc6`
- end: `0x180005e3f`
- name: `__tailMerge_ext_ms_win_storage_sense_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005e45`
- `0x180005e57`
- `0x180005e69`

## callees

- `0x1800023e0`
- `0x180005dc6`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_storage_sense_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005dc6  mov     [rsp+arg_0], rcx
0x180005dcb  mov     [rsp+arg_8], rdx
0x180005dd0  mov     [rsp+arg_10], r8
0x180005dd5  mov     [rsp+arg_18], r9
0x180005dda  sub     rsp, 68h
0x180005dde  movdqa  [rsp+68h+var_48], xmm0
0x180005de4  movdqa  [rsp+68h+var_38], xmm1
0x180005dea  movdqa  [rsp+68h+var_28], xmm2
0x180005df0  movdqa  [rsp+68h+var_18], xmm3
0x180005df6  mov     rdx, rax
0x180005df9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll
0x180005e00  call    __delayLoadHelper2
0x180005e05  movdqa  xmm0, [rsp+68h+var_48]
0x180005e0b  movdqa  xmm1, [rsp+68h+var_38]
0x180005e11  movdqa  xmm2, [rsp+68h+var_28]
0x180005e17  movdqa  xmm3, [rsp+68h+var_18]
0x180005e1d  mov     rcx, [rsp+68h+arg_0]
0x180005e22  mov     rdx, [rsp+68h+arg_8]
0x180005e27  mov     r8, [rsp+68h+arg_10]
0x180005e2f  mov     r9, [rsp+68h+arg_18]
0x180005e37  add     rsp, 68h
0x180005e3b  jmp     short $+2
0x180005e3d  jmp     rax
```
