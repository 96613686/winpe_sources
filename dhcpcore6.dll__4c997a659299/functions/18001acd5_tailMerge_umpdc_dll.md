# __tailMerge_umpdc_dll

- ea: `0x18001acd5`
- end: `0x18001ad4e`
- name: `__tailMerge_umpdc_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001ad54`
- `0x18001ad66`
- `0x18001ad78`
- `0x18001ad8a`

## callees

- `0x18000f880`
- `0x18001acd5`

## pseudocode

```c
__int64 __fastcall _tailMerge_umpdc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_umpdc_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001acd5  mov     [rsp+arg_0], rcx
0x18001acda  mov     [rsp+arg_8], rdx
0x18001acdf  mov     [rsp+arg_10], r8
0x18001ace4  mov     [rsp+arg_18], r9
0x18001ace9  sub     rsp, 68h
0x18001aced  movdqa  [rsp+68h+var_48], xmm0
0x18001acf3  movdqa  [rsp+68h+var_38], xmm1
0x18001acf9  movdqa  [rsp+68h+var_28], xmm2
0x18001acff  movdqa  [rsp+68h+var_18], xmm3
0x18001ad05  mov     rdx, rax
0x18001ad08  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_umpdc_dll
0x18001ad0f  call    __delayLoadHelper2
0x18001ad14  movdqa  xmm0, [rsp+68h+var_48]
0x18001ad1a  movdqa  xmm1, [rsp+68h+var_38]
0x18001ad20  movdqa  xmm2, [rsp+68h+var_28]
0x18001ad26  movdqa  xmm3, [rsp+68h+var_18]
0x18001ad2c  mov     rcx, [rsp+68h+arg_0]
0x18001ad31  mov     rdx, [rsp+68h+arg_8]
0x18001ad36  mov     r8, [rsp+68h+arg_10]
0x18001ad3e  mov     r9, [rsp+68h+arg_18]
0x18001ad46  add     rsp, 68h
0x18001ad4a  jmp     short $+2
0x18001ad4c  jmp     rax
```
