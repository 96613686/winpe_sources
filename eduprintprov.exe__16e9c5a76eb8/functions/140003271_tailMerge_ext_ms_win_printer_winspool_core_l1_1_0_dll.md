# __tailMerge_ext_ms_win_printer_winspool_core_l1_1_0_dll

- ea: `0x140003271`
- end: `0x1400032ea`
- name: `__tailMerge_ext_ms_win_printer_winspool_core_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400032f0`

## callees

- `0x140003271`
- `0x140013030`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_printer_winspool_core_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_printer_winspool_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003271  mov     [rsp+arg_0], rcx
0x140003276  mov     [rsp+arg_8], rdx
0x14000327b  mov     [rsp+arg_10], r8
0x140003280  mov     [rsp+arg_18], r9
0x140003285  sub     rsp, 68h
0x140003289  movdqa  [rsp+68h+var_48], xmm0
0x14000328f  movdqa  [rsp+68h+var_38], xmm1
0x140003295  movdqa  [rsp+68h+var_28], xmm2
0x14000329b  movdqa  [rsp+68h+var_18], xmm3
0x1400032a1  mov     rdx, rax
0x1400032a4  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_printer_winspool_core_l1_1_0_dll
0x1400032ab  call    __delayLoadHelper2
0x1400032b0  movdqa  xmm0, [rsp+68h+var_48]
0x1400032b6  movdqa  xmm1, [rsp+68h+var_38]
0x1400032bc  movdqa  xmm2, [rsp+68h+var_28]
0x1400032c2  movdqa  xmm3, [rsp+68h+var_18]
0x1400032c8  mov     rcx, [rsp+68h+arg_0]
0x1400032cd  mov     rdx, [rsp+68h+arg_8]
0x1400032d2  mov     r8, [rsp+68h+arg_10]
0x1400032da  mov     r9, [rsp+68h+arg_18]
0x1400032e2  add     rsp, 68h
0x1400032e6  jmp     short $+2
0x1400032e8  jmp     rax
```
