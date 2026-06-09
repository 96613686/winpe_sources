# __tailMerge_certca_dll

- ea: `0x18000637d`
- end: `0x1800063f6`
- name: `__tailMerge_certca_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800063fc`
- `0x18000640e`
- `0x180006420`
- `0x180006432`
- `0x180006444`
- `0x180006456`
- `0x180006468`
- `0x18000647a`
- `0x18000648c`

## callees

- `0x1800046b0`
- `0x18000637d`

## pseudocode

```c
__int64 __fastcall _tailMerge_certca_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_certca_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000637d  mov     [rsp+arg_0], rcx
0x180006382  mov     [rsp+arg_8], rdx
0x180006387  mov     [rsp+arg_10], r8
0x18000638c  mov     [rsp+arg_18], r9
0x180006391  sub     rsp, 68h
0x180006395  movdqa  [rsp+68h+var_48], xmm0
0x18000639b  movdqa  [rsp+68h+var_38], xmm1
0x1800063a1  movdqa  [rsp+68h+var_28], xmm2
0x1800063a7  movdqa  [rsp+68h+var_18], xmm3
0x1800063ad  mov     rdx, rax
0x1800063b0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_certca_dll
0x1800063b7  call    __delayLoadHelper2
0x1800063bc  movdqa  xmm0, [rsp+68h+var_48]
0x1800063c2  movdqa  xmm1, [rsp+68h+var_38]
0x1800063c8  movdqa  xmm2, [rsp+68h+var_28]
0x1800063ce  movdqa  xmm3, [rsp+68h+var_18]
0x1800063d4  mov     rcx, [rsp+68h+arg_0]
0x1800063d9  mov     rdx, [rsp+68h+arg_8]
0x1800063de  mov     r8, [rsp+68h+arg_10]
0x1800063e6  mov     r9, [rsp+68h+arg_18]
0x1800063ee  add     rsp, 68h
0x1800063f2  jmp     short $+2
0x1800063f4  jmp     rax
```
