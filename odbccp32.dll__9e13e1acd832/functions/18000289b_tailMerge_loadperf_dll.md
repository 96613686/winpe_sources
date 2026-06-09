# __tailMerge_loadperf_dll

- ea: `0x18000289b`
- end: `0x180002914`
- name: `__tailMerge_loadperf_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000291a`
- `0x18000292c`

## callees

- `0x18000289b`
- `0x1800149c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_loadperf_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_loadperf_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000289b  mov     [rsp+arg_0], rcx
0x1800028a0  mov     [rsp+arg_8], rdx
0x1800028a5  mov     [rsp+arg_10], r8
0x1800028aa  mov     [rsp+arg_18], r9
0x1800028af  sub     rsp, 68h
0x1800028b3  movdqa  [rsp+68h+var_48], xmm0
0x1800028b9  movdqa  [rsp+68h+var_38], xmm1
0x1800028bf  movdqa  [rsp+68h+var_28], xmm2
0x1800028c5  movdqa  [rsp+68h+var_18], xmm3
0x1800028cb  mov     rdx, rax
0x1800028ce  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_loadperf_dll
0x1800028d5  call    __delayLoadHelper2
0x1800028da  movdqa  xmm0, [rsp+68h+var_48]
0x1800028e0  movdqa  xmm1, [rsp+68h+var_38]
0x1800028e6  movdqa  xmm2, [rsp+68h+var_28]
0x1800028ec  movdqa  xmm3, [rsp+68h+var_18]
0x1800028f2  mov     rcx, [rsp+68h+arg_0]
0x1800028f7  mov     rdx, [rsp+68h+arg_8]
0x1800028fc  mov     r8, [rsp+68h+arg_10]
0x180002904  mov     r9, [rsp+68h+arg_18]
0x18000290c  add     rsp, 68h
0x180002910  jmp     short $+2
0x180002912  jmp     rax
```
