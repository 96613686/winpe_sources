# __tailMerge_certenroll_dll

- ea: `0x180006498`
- end: `0x180006511`
- name: `__tailMerge_certenroll_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006517`
- `0x180006529`

## callees

- `0x1800046b0`
- `0x180006498`

## pseudocode

```c
__int64 __fastcall _tailMerge_certenroll_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_certenroll_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006498  mov     [rsp+arg_0], rcx
0x18000649d  mov     [rsp+arg_8], rdx
0x1800064a2  mov     [rsp+arg_10], r8
0x1800064a7  mov     [rsp+arg_18], r9
0x1800064ac  sub     rsp, 68h
0x1800064b0  movdqa  [rsp+68h+var_48], xmm0
0x1800064b6  movdqa  [rsp+68h+var_38], xmm1
0x1800064bc  movdqa  [rsp+68h+var_28], xmm2
0x1800064c2  movdqa  [rsp+68h+var_18], xmm3
0x1800064c8  mov     rdx, rax
0x1800064cb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_certenroll_dll
0x1800064d2  call    __delayLoadHelper2
0x1800064d7  movdqa  xmm0, [rsp+68h+var_48]
0x1800064dd  movdqa  xmm1, [rsp+68h+var_38]
0x1800064e3  movdqa  xmm2, [rsp+68h+var_28]
0x1800064e9  movdqa  xmm3, [rsp+68h+var_18]
0x1800064ef  mov     rcx, [rsp+68h+arg_0]
0x1800064f4  mov     rdx, [rsp+68h+arg_8]
0x1800064f9  mov     r8, [rsp+68h+arg_10]
0x180006501  mov     r9, [rsp+68h+arg_18]
0x180006509  add     rsp, 68h
0x18000650d  jmp     short $+2
0x18000650f  jmp     rax
```
