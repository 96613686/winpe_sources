# __tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll

- ea: `0x18000a082`
- end: `0x18000a0fb`
- name: `__tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a101`
- `0x18000a113`

## callees

- `0x180007cb0`
- `0x18000a082`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_draw_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a082  mov     [rsp+arg_0], rcx
0x18000a087  mov     [rsp+arg_8], rdx
0x18000a08c  mov     [rsp+arg_10], r8
0x18000a091  mov     [rsp+arg_18], r9
0x18000a096  sub     rsp, 68h
0x18000a09a  movdqa  [rsp+68h+var_48], xmm0
0x18000a0a0  movdqa  [rsp+68h+var_38], xmm1
0x18000a0a6  movdqa  [rsp+68h+var_28], xmm2
0x18000a0ac  movdqa  [rsp+68h+var_18], xmm3
0x18000a0b2  mov     rdx, rax
0x18000a0b5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_draw_l1_1_0_dll
0x18000a0bc  call    __delayLoadHelper2
0x18000a0c1  movdqa  xmm0, [rsp+68h+var_48]
0x18000a0c7  movdqa  xmm1, [rsp+68h+var_38]
0x18000a0cd  movdqa  xmm2, [rsp+68h+var_28]
0x18000a0d3  movdqa  xmm3, [rsp+68h+var_18]
0x18000a0d9  mov     rcx, [rsp+68h+arg_0]
0x18000a0de  mov     rdx, [rsp+68h+arg_8]
0x18000a0e3  mov     r8, [rsp+68h+arg_10]
0x18000a0eb  mov     r9, [rsp+68h+arg_18]
0x18000a0f3  add     rsp, 68h
0x18000a0f7  jmp     short $+2
0x18000a0f9  jmp     rax
```
