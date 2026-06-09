# __tailMerge_advapi32_dll

- ea: `0x18000aa85`
- end: `0x18000aafe`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ab04`
- `0x18000ab16`
- `0x18000ab28`
- `0x18000ab3a`
- `0x18000ab4c`
- `0x18000ab5e`
- `0x18000ab70`
- `0x18000ab82`
- `0x18000ab94`

## callees

- `0x1800079c0`
- `0x18000aa85`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aa85  mov     [rsp+arg_0], rcx
0x18000aa8a  mov     [rsp+arg_8], rdx
0x18000aa8f  mov     [rsp+arg_10], r8
0x18000aa94  mov     [rsp+arg_18], r9
0x18000aa99  sub     rsp, 68h
0x18000aa9d  movdqa  [rsp+68h+var_48], xmm0
0x18000aaa3  movdqa  [rsp+68h+var_38], xmm1
0x18000aaa9  movdqa  [rsp+68h+var_28], xmm2
0x18000aaaf  movdqa  [rsp+68h+var_18], xmm3
0x18000aab5  mov     rdx, rax
0x18000aab8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x18000aabf  call    __delayLoadHelper2
0x18000aac4  movdqa  xmm0, [rsp+68h+var_48]
0x18000aaca  movdqa  xmm1, [rsp+68h+var_38]
0x18000aad0  movdqa  xmm2, [rsp+68h+var_28]
0x18000aad6  movdqa  xmm3, [rsp+68h+var_18]
0x18000aadc  mov     rcx, [rsp+68h+arg_0]
0x18000aae1  mov     rdx, [rsp+68h+arg_8]
0x18000aae6  mov     r8, [rsp+68h+arg_10]
0x18000aaee  mov     r9, [rsp+68h+arg_18]
0x18000aaf6  add     rsp, 68h
0x18000aafa  jmp     short $+2
0x18000aafc  jmp     rax
```
