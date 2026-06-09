# __tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_2_dll

- ea: `0x1800025fa`
- end: `0x180002673`
- name: `__tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_2_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002679`
- `0x18000274c`
- `0x18000275e`
- `0x1800027b8`

## callees

- `0x1800025fa`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_dialogbox_l1_1_2_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025fa  mov     [rsp+arg_0], rcx
0x1800025ff  mov     [rsp+arg_8], rdx
0x180002604  mov     [rsp+arg_10], r8
0x180002609  mov     [rsp+arg_18], r9
0x18000260e  sub     rsp, 68h
0x180002612  movdqa  [rsp+68h+var_48], xmm0
0x180002618  movdqa  [rsp+68h+var_38], xmm1
0x18000261e  movdqa  [rsp+68h+var_28], xmm2
0x180002624  movdqa  [rsp+68h+var_18], xmm3
0x18000262a  mov     rdx, rax
0x18000262d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_dialogbox_l1_1_2_dll
0x180002634  call    __delayLoadHelper2
0x180002639  movdqa  xmm0, [rsp+68h+var_48]
0x18000263f  movdqa  xmm1, [rsp+68h+var_38]
0x180002645  movdqa  xmm2, [rsp+68h+var_28]
0x18000264b  movdqa  xmm3, [rsp+68h+var_18]
0x180002651  mov     rcx, [rsp+68h+arg_0]
0x180002656  mov     rdx, [rsp+68h+arg_8]
0x18000265b  mov     r8, [rsp+68h+arg_10]
0x180002663  mov     r9, [rsp+68h+arg_18]
0x18000266b  add     rsp, 68h
0x18000266f  jmp     short $+2
0x180002671  jmp     rax
```
