# __tailMerge_advapi32_dll

- ea: `0x180001311`
- end: `0x18000138a`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001390`
- `0x180002036`
- `0x180002048`
- `0x18000205a`

## callees

- `0x180001311`
- `0x180012630`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001311  mov     [rsp+arg_0], rcx
0x180001316  mov     [rsp+arg_8], rdx
0x18000131b  mov     [rsp+arg_10], r8
0x180001320  mov     [rsp+arg_18], r9
0x180001325  sub     rsp, 68h
0x180001329  movdqa  [rsp+68h+var_48], xmm0
0x18000132f  movdqa  [rsp+68h+var_38], xmm1
0x180001335  movdqa  [rsp+68h+var_28], xmm2
0x18000133b  movdqa  [rsp+68h+var_18], xmm3
0x180001341  mov     rdx, rax
0x180001344  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x18000134b  call    __delayLoadHelper2
0x180001350  movdqa  xmm0, [rsp+68h+var_48]
0x180001356  movdqa  xmm1, [rsp+68h+var_38]
0x18000135c  movdqa  xmm2, [rsp+68h+var_28]
0x180001362  movdqa  xmm3, [rsp+68h+var_18]
0x180001368  mov     rcx, [rsp+68h+arg_0]
0x18000136d  mov     rdx, [rsp+68h+arg_8]
0x180001372  mov     r8, [rsp+68h+arg_10]
0x18000137a  mov     r9, [rsp+68h+arg_18]
0x180001382  add     rsp, 68h
0x180001386  jmp     short $+2
0x180001388  jmp     rax
```
