# __tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll

- ea: `0x180002f51`
- end: `0x180002fca`
- name: `__tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002fd0`

## callees

- `0x180002f51`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002f51  mov     [rsp+arg_0], rcx
0x180002f56  mov     [rsp+arg_8], rdx
0x180002f5b  mov     [rsp+arg_10], r8
0x180002f60  mov     [rsp+arg_18], r9
0x180002f65  sub     rsp, 68h
0x180002f69  movdqa  [rsp+68h+var_48], xmm0
0x180002f6f  movdqa  [rsp+68h+var_38], xmm1
0x180002f75  movdqa  [rsp+68h+var_28], xmm2
0x180002f7b  movdqa  [rsp+68h+var_18], xmm3
0x180002f81  mov     rdx, rax
0x180002f84  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_2_dll
0x180002f8b  call    __delayLoadHelper2
0x180002f90  movdqa  xmm0, [rsp+68h+var_48]
0x180002f96  movdqa  xmm1, [rsp+68h+var_38]
0x180002f9c  movdqa  xmm2, [rsp+68h+var_28]
0x180002fa2  movdqa  xmm3, [rsp+68h+var_18]
0x180002fa8  mov     rcx, [rsp+68h+arg_0]
0x180002fad  mov     rdx, [rsp+68h+arg_8]
0x180002fb2  mov     r8, [rsp+68h+arg_10]
0x180002fba  mov     r9, [rsp+68h+arg_18]
0x180002fc2  add     rsp, 68h
0x180002fc6  jmp     short $+2
0x180002fc8  jmp     rax
```
