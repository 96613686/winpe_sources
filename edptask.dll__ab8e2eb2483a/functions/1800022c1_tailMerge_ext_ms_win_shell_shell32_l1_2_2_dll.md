# __tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll

- ea: `0x1800022c1`
- end: `0x18000233a`
- name: `__tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002340`

## callees

- `0x1800022c1`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_shell_shell32_l1_2_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022c1  mov     [rsp+arg_0], rcx
0x1800022c6  mov     [rsp+arg_8], rdx
0x1800022cb  mov     [rsp+arg_10], r8
0x1800022d0  mov     [rsp+arg_18], r9
0x1800022d5  sub     rsp, 68h
0x1800022d9  movdqa  [rsp+68h+var_48], xmm0
0x1800022df  movdqa  [rsp+68h+var_38], xmm1
0x1800022e5  movdqa  [rsp+68h+var_28], xmm2
0x1800022eb  movdqa  [rsp+68h+var_18], xmm3
0x1800022f1  mov     rdx, rax
0x1800022f4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_shell_shell32_l1_2_2_dll
0x1800022fb  call    __delayLoadHelper2
0x180002300  movdqa  xmm0, [rsp+68h+var_48]
0x180002306  movdqa  xmm1, [rsp+68h+var_38]
0x18000230c  movdqa  xmm2, [rsp+68h+var_28]
0x180002312  movdqa  xmm3, [rsp+68h+var_18]
0x180002318  mov     rcx, [rsp+68h+arg_0]
0x18000231d  mov     rdx, [rsp+68h+arg_8]
0x180002322  mov     r8, [rsp+68h+arg_10]
0x18000232a  mov     r9, [rsp+68h+arg_18]
0x180002332  add     rsp, 68h
0x180002336  jmp     short $+2
0x180002338  jmp     rax
```
