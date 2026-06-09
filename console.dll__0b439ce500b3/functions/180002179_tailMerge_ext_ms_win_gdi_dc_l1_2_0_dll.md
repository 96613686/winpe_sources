# __tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll

- ea: `0x180002179`
- end: `0x1800021f2`
- name: `__tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800021f8`
- `0x18000220a`
- `0x18000221c`

## callees

- `0x180002179`
- `0x180018ae0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_gdi_dc_l1_2_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002179  mov     [rsp+arg_0], rcx
0x18000217e  mov     [rsp+arg_8], rdx
0x180002183  mov     [rsp+arg_10], r8
0x180002188  mov     [rsp+arg_18], r9
0x18000218d  sub     rsp, 68h
0x180002191  movdqa  [rsp+68h+var_48], xmm0
0x180002197  movdqa  [rsp+68h+var_38], xmm1
0x18000219d  movdqa  [rsp+68h+var_28], xmm2
0x1800021a3  movdqa  [rsp+68h+var_18], xmm3
0x1800021a9  mov     rdx, rax
0x1800021ac  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_gdi_dc_l1_2_0_dll
0x1800021b3  call    __delayLoadHelper2
0x1800021b8  movdqa  xmm0, [rsp+68h+var_48]
0x1800021be  movdqa  xmm1, [rsp+68h+var_38]
0x1800021c4  movdqa  xmm2, [rsp+68h+var_28]
0x1800021ca  movdqa  xmm3, [rsp+68h+var_18]
0x1800021d0  mov     rcx, [rsp+68h+arg_0]
0x1800021d5  mov     rdx, [rsp+68h+arg_8]
0x1800021da  mov     r8, [rsp+68h+arg_10]
0x1800021e2  mov     r9, [rsp+68h+arg_18]
0x1800021ea  add     rsp, 68h
0x1800021ee  jmp     short $+2
0x1800021f0  jmp     rax
```
