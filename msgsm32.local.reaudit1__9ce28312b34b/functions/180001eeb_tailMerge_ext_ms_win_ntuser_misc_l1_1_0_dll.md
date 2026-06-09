# __tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll

- ea: `0x180001eeb`
- end: `0x180001f64`
- name: `__tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f6a`

## callees

- `0x180001eeb`
- `0x1800063b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_misc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_misc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001eeb  mov     [rsp+arg_0], rcx
0x180001ef0  mov     [rsp+arg_8], rdx
0x180001ef5  mov     [rsp+arg_10], r8
0x180001efa  mov     [rsp+arg_18], r9
0x180001eff  sub     rsp, 68h
0x180001f03  movdqa  [rsp+68h+var_48], xmm0
0x180001f09  movdqa  [rsp+68h+var_38], xmm1
0x180001f0f  movdqa  [rsp+68h+var_28], xmm2
0x180001f15  movdqa  [rsp+68h+var_18], xmm3
0x180001f1b  mov     rdx, rax
0x180001f1e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_misc_l1_1_0_dll
0x180001f25  call    __delayLoadHelper2
0x180001f2a  movdqa  xmm0, [rsp+68h+var_48]
0x180001f30  movdqa  xmm1, [rsp+68h+var_38]
0x180001f36  movdqa  xmm2, [rsp+68h+var_28]
0x180001f3c  movdqa  xmm3, [rsp+68h+var_18]
0x180001f42  mov     rcx, [rsp+68h+arg_0]
0x180001f47  mov     rdx, [rsp+68h+arg_8]
0x180001f4c  mov     r8, [rsp+68h+arg_10]
0x180001f54  mov     r9, [rsp+68h+arg_18]
0x180001f5c  add     rsp, 68h
0x180001f60  jmp     short $+2
0x180001f62  jmp     rax
```
