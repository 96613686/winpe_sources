# __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll

- ea: `0x1800020ee`
- end: `0x180002167`
- name: `__tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000216d`

## callees

- `0x1800020ee`
- `0x180018ae0`

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
0x1800020ee  mov     [rsp+arg_0], rcx
0x1800020f3  mov     [rsp+arg_8], rdx
0x1800020f8  mov     [rsp+arg_10], r8
0x1800020fd  mov     [rsp+arg_18], r9
0x180002102  sub     rsp, 68h
0x180002106  movdqa  [rsp+68h+var_48], xmm0
0x18000210c  movdqa  [rsp+68h+var_38], xmm1
0x180002112  movdqa  [rsp+68h+var_28], xmm2
0x180002118  movdqa  [rsp+68h+var_18], xmm3
0x18000211e  mov     rdx, rax
0x180002121  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell32_shellfolders_l1_1_0_dll
0x180002128  call    __delayLoadHelper2
0x18000212d  movdqa  xmm0, [rsp+68h+var_48]
0x180002133  movdqa  xmm1, [rsp+68h+var_38]
0x180002139  movdqa  xmm2, [rsp+68h+var_28]
0x18000213f  movdqa  xmm3, [rsp+68h+var_18]
0x180002145  mov     rcx, [rsp+68h+arg_0]
0x18000214a  mov     rdx, [rsp+68h+arg_8]
0x18000214f  mov     r8, [rsp+68h+arg_10]
0x180002157  mov     r9, [rsp+68h+arg_18]
0x18000215f  add     rsp, 68h
0x180002163  jmp     short $+2
0x180002165  jmp     rax
```
