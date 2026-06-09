# __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll

- ea: `0x140002d20`
- end: `0x140002d99`
- name: `__tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002d9f`

## callees

- `0x140002d20`
- `0x140019490`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002d20  mov     [rsp+arg_0], rcx
0x140002d25  mov     [rsp+arg_8], rdx
0x140002d2a  mov     [rsp+arg_10], r8
0x140002d2f  mov     [rsp+arg_18], r9
0x140002d34  sub     rsp, 68h
0x140002d38  movdqa  [rsp+68h+var_48], xmm0
0x140002d3e  movdqa  [rsp+68h+var_38], xmm1
0x140002d44  movdqa  [rsp+68h+var_28], xmm2
0x140002d4a  movdqa  [rsp+68h+var_18], xmm3
0x140002d50  mov     rdx, rax
0x140002d53  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll
0x140002d5a  call    __delayLoadHelper2
0x140002d5f  movdqa  xmm0, [rsp+68h+var_48]
0x140002d65  movdqa  xmm1, [rsp+68h+var_38]
0x140002d6b  movdqa  xmm2, [rsp+68h+var_28]
0x140002d71  movdqa  xmm3, [rsp+68h+var_18]
0x140002d77  mov     rcx, [rsp+68h+arg_0]
0x140002d7c  mov     rdx, [rsp+68h+arg_8]
0x140002d81  mov     r8, [rsp+68h+arg_10]
0x140002d89  mov     r9, [rsp+68h+arg_18]
0x140002d91  add     rsp, 68h
0x140002d95  jmp     short $+2
0x140002d97  jmp     rax
```
