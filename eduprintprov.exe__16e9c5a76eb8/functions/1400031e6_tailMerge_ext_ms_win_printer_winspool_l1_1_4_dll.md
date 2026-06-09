# __tailMerge_ext_ms_win_printer_winspool_l1_1_4_dll

- ea: `0x1400031e6`
- end: `0x14000325f`
- name: `__tailMerge_ext_ms_win_printer_winspool_l1_1_4_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003265`

## callees

- `0x1400031e6`
- `0x140013030`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_printer_winspool_l1_1_4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_printer_winspool_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400031e6  mov     [rsp+arg_0], rcx
0x1400031eb  mov     [rsp+arg_8], rdx
0x1400031f0  mov     [rsp+arg_10], r8
0x1400031f5  mov     [rsp+arg_18], r9
0x1400031fa  sub     rsp, 68h
0x1400031fe  movdqa  [rsp+68h+var_48], xmm0
0x140003204  movdqa  [rsp+68h+var_38], xmm1
0x14000320a  movdqa  [rsp+68h+var_28], xmm2
0x140003210  movdqa  [rsp+68h+var_18], xmm3
0x140003216  mov     rdx, rax
0x140003219  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_printer_winspool_l1_1_4_dll
0x140003220  call    __delayLoadHelper2
0x140003225  movdqa  xmm0, [rsp+68h+var_48]
0x14000322b  movdqa  xmm1, [rsp+68h+var_38]
0x140003231  movdqa  xmm2, [rsp+68h+var_28]
0x140003237  movdqa  xmm3, [rsp+68h+var_18]
0x14000323d  mov     rcx, [rsp+68h+arg_0]
0x140003242  mov     rdx, [rsp+68h+arg_8]
0x140003247  mov     r8, [rsp+68h+arg_10]
0x14000324f  mov     r9, [rsp+68h+arg_18]
0x140003257  add     rsp, 68h
0x14000325b  jmp     short $+2
0x14000325d  jmp     rax
```
