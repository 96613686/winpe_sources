# __tailMerge_wintrust_dll

- ea: `0x140010dd2`
- end: `0x140010e4b`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010e51`
- `0x140010e63`

## callees

- `0x1400083b0`
- `0x140010dd2`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010dd2  mov     [rsp+arg_0], rcx
0x140010dd7  mov     [rsp+arg_8], rdx
0x140010ddc  mov     [rsp+arg_10], r8
0x140010de1  mov     [rsp+arg_18], r9
0x140010de6  sub     rsp, 68h
0x140010dea  movdqa  [rsp+68h+var_48], xmm0
0x140010df0  movdqa  [rsp+68h+var_38], xmm1
0x140010df6  movdqa  [rsp+68h+var_28], xmm2
0x140010dfc  movdqa  [rsp+68h+var_18], xmm3
0x140010e02  mov     rdx, rax
0x140010e05  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x140010e0c  call    __delayLoadHelper2
0x140010e11  movdqa  xmm0, [rsp+68h+var_48]
0x140010e17  movdqa  xmm1, [rsp+68h+var_38]
0x140010e1d  movdqa  xmm2, [rsp+68h+var_28]
0x140010e23  movdqa  xmm3, [rsp+68h+var_18]
0x140010e29  mov     rcx, [rsp+68h+arg_0]
0x140010e2e  mov     rdx, [rsp+68h+arg_8]
0x140010e33  mov     r8, [rsp+68h+arg_10]
0x140010e3b  mov     r9, [rsp+68h+arg_18]
0x140010e43  add     rsp, 68h
0x140010e47  jmp     short $+2
0x140010e49  jmp     rax
```
