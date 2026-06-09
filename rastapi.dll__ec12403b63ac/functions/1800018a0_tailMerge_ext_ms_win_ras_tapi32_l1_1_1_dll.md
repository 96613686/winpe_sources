# __tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll

- ea: `0x1800018a0`
- end: `0x180001919`
- name: `__tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000191f`
- `0x180001931`
- `0x180001943`
- `0x180001955`
- `0x180001967`
- `0x180001979`
- `0x18000198b`
- `0x18000199d`
- `0x1800019af`
- `0x1800019c1`
- `0x1800019d3`
- `0x1800019e5`
- `0x1800019f7`
- `0x180001a09`
- `0x180001a1b`
- `0x180001a2d`
- `0x180001a3f`
- `0x180001a51`
- `0x180001a63`
- `0x180001a75`
- `0x180001a87`
- `0x180001a99`

## callees

- `0x1800018a0`
- `0x180029190`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ras_tapi32_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ras_tapi32_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800018a0  mov     [rsp+arg_0], rcx
0x1800018a5  mov     [rsp+arg_8], rdx
0x1800018aa  mov     [rsp+arg_10], r8
0x1800018af  mov     [rsp+arg_18], r9
0x1800018b4  sub     rsp, 68h
0x1800018b8  movdqa  [rsp+68h+var_48], xmm0
0x1800018be  movdqa  [rsp+68h+var_38], xmm1
0x1800018c4  movdqa  [rsp+68h+var_28], xmm2
0x1800018ca  movdqa  [rsp+68h+var_18], xmm3
0x1800018d0  mov     rdx, rax
0x1800018d3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ras_tapi32_l1_1_1_dll
0x1800018da  call    __delayLoadHelper2
0x1800018df  movdqa  xmm0, [rsp+68h+var_48]
0x1800018e5  movdqa  xmm1, [rsp+68h+var_38]
0x1800018eb  movdqa  xmm2, [rsp+68h+var_28]
0x1800018f1  movdqa  xmm3, [rsp+68h+var_18]
0x1800018f7  mov     rcx, [rsp+68h+arg_0]
0x1800018fc  mov     rdx, [rsp+68h+arg_8]
0x180001901  mov     r8, [rsp+68h+arg_10]
0x180001909  mov     r9, [rsp+68h+arg_18]
0x180001911  add     rsp, 68h
0x180001915  jmp     short $+2
0x180001917  jmp     rax
```
