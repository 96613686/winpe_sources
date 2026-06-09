# __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll

- ea: `0x180001d2f`
- end: `0x180001da8`
- name: `__tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001dae`
- `0x180001dc0`
- `0x180001ee8`
- `0x180001f1e`
- `0x180001f54`
- `0x180001f66`
- `0x180001f8a`
- `0x180002027`
- `0x180002039`
- `0x18000204b`
- `0x18000205d`
- `0x18000206f`
- `0x180002093`
- `0x1800020a5`
- `0x1800020c9`
- `0x1800020ed`
- `0x1800020ff`
- `0x180002111`

## callees

- `0x180001d2f`
- `0x18000b340`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d2f  mov     [rsp+arg_0], rcx
0x180001d34  mov     [rsp+arg_8], rdx
0x180001d39  mov     [rsp+arg_10], r8
0x180001d3e  mov     [rsp+arg_18], r9
0x180001d43  sub     rsp, 68h
0x180001d47  movdqa  [rsp+68h+var_48], xmm0
0x180001d4d  movdqa  [rsp+68h+var_38], xmm1
0x180001d53  movdqa  [rsp+68h+var_28], xmm2
0x180001d59  movdqa  [rsp+68h+var_18], xmm3
0x180001d5f  mov     rdx, rax
0x180001d62  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_window_l1_1_0_dll
0x180001d69  call    __delayLoadHelper2
0x180001d6e  movdqa  xmm0, [rsp+68h+var_48]
0x180001d74  movdqa  xmm1, [rsp+68h+var_38]
0x180001d7a  movdqa  xmm2, [rsp+68h+var_28]
0x180001d80  movdqa  xmm3, [rsp+68h+var_18]
0x180001d86  mov     rcx, [rsp+68h+arg_0]
0x180001d8b  mov     rdx, [rsp+68h+arg_8]
0x180001d90  mov     r8, [rsp+68h+arg_10]
0x180001d98  mov     r9, [rsp+68h+arg_18]
0x180001da0  add     rsp, 68h
0x180001da4  jmp     short $+2
0x180001da6  jmp     rax
```
