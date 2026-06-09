# __tailMerge_davhlpr_dll

- ea: `0x18000acda`
- end: `0x18000ad53`
- name: `__tailMerge_davhlpr_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ad59`
- `0x18000ad6b`
- `0x18000ad7d`
- `0x18000ad8f`

## callees

- `0x1800079c0`
- `0x18000acda`

## pseudocode

```c
__int64 __fastcall _tailMerge_davhlpr_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_davhlpr_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000acda  mov     [rsp+arg_0], rcx
0x18000acdf  mov     [rsp+arg_8], rdx
0x18000ace4  mov     [rsp+arg_10], r8
0x18000ace9  mov     [rsp+arg_18], r9
0x18000acee  sub     rsp, 68h
0x18000acf2  movdqa  [rsp+68h+var_48], xmm0
0x18000acf8  movdqa  [rsp+68h+var_38], xmm1
0x18000acfe  movdqa  [rsp+68h+var_28], xmm2
0x18000ad04  movdqa  [rsp+68h+var_18], xmm3
0x18000ad0a  mov     rdx, rax
0x18000ad0d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_davhlpr_dll
0x18000ad14  call    __delayLoadHelper2
0x18000ad19  movdqa  xmm0, [rsp+68h+var_48]
0x18000ad1f  movdqa  xmm1, [rsp+68h+var_38]
0x18000ad25  movdqa  xmm2, [rsp+68h+var_28]
0x18000ad2b  movdqa  xmm3, [rsp+68h+var_18]
0x18000ad31  mov     rcx, [rsp+68h+arg_0]
0x18000ad36  mov     rdx, [rsp+68h+arg_8]
0x18000ad3b  mov     r8, [rsp+68h+arg_10]
0x18000ad43  mov     r9, [rsp+68h+arg_18]
0x18000ad4b  add     rsp, 68h
0x18000ad4f  jmp     short $+2
0x18000ad51  jmp     rax
```
