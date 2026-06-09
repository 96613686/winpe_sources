# __tailMerge_user32_dll

- ea: `0x1800175eb`
- end: `0x180017664`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001766a`
- `0x18001767c`

## callees

- `0x18000e1a0`
- `0x1800175eb`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800175eb  mov     [rsp+arg_0], rcx
0x1800175f0  mov     [rsp+arg_8], rdx
0x1800175f5  mov     [rsp+arg_10], r8
0x1800175fa  mov     [rsp+arg_18], r9
0x1800175ff  sub     rsp, 68h
0x180017603  movdqa  [rsp+68h+var_48], xmm0
0x180017609  movdqa  [rsp+68h+var_38], xmm1
0x18001760f  movdqa  [rsp+68h+var_28], xmm2
0x180017615  movdqa  [rsp+68h+var_18], xmm3
0x18001761b  mov     rdx, rax
0x18001761e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180017625  call    __delayLoadHelper2
0x18001762a  movdqa  xmm0, [rsp+68h+var_48]
0x180017630  movdqa  xmm1, [rsp+68h+var_38]
0x180017636  movdqa  xmm2, [rsp+68h+var_28]
0x18001763c  movdqa  xmm3, [rsp+68h+var_18]
0x180017642  mov     rcx, [rsp+68h+arg_0]
0x180017647  mov     rdx, [rsp+68h+arg_8]
0x18001764c  mov     r8, [rsp+68h+arg_10]
0x180017654  mov     r9, [rsp+68h+arg_18]
0x18001765c  add     rsp, 68h
0x180017660  jmp     short $+2
0x180017662  jmp     rax
```
