# __tailMerge_ws2_32_dll

- ea: `0x180001920`
- end: `0x180001999`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000199f`

## callees

- `0x180001920`
- `0x1800036c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_0], rcx
0x180001925  mov     [rsp+arg_8], rdx
0x18000192a  mov     [rsp+arg_10], r8
0x18000192f  mov     [rsp+arg_18], r9
0x180001934  sub     rsp, 68h
0x180001938  movdqa  [rsp+68h+var_48], xmm0
0x18000193e  movdqa  [rsp+68h+var_38], xmm1
0x180001944  movdqa  [rsp+68h+var_28], xmm2
0x18000194a  movdqa  [rsp+68h+var_18], xmm3
0x180001950  mov     rdx, rax
0x180001953  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x18000195a  call    __delayLoadHelper2
0x18000195f  movdqa  xmm0, [rsp+68h+var_48]
0x180001965  movdqa  xmm1, [rsp+68h+var_38]
0x18000196b  movdqa  xmm2, [rsp+68h+var_28]
0x180001971  movdqa  xmm3, [rsp+68h+var_18]
0x180001977  mov     rcx, [rsp+68h+arg_0]
0x18000197c  mov     rdx, [rsp+68h+arg_8]
0x180001981  mov     r8, [rsp+68h+arg_10]
0x180001989  mov     r9, [rsp+68h+arg_18]
0x180001991  add     rsp, 68h
0x180001995  jmp     short $+2
0x180001997  jmp     rax
```
