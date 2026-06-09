# __tailMerge_loadperf_dll

- ea: `0x1800021ef`
- end: `0x180002268`
- name: `__tailMerge_loadperf_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000226e`

## callees

- `0x1800021ef`
- `0x180017e60`

## pseudocode

```c
__int64 __fastcall _tailMerge_loadperf_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_loadperf_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021ef  mov     [rsp+arg_0], rcx
0x1800021f4  mov     [rsp+arg_8], rdx
0x1800021f9  mov     [rsp+arg_10], r8
0x1800021fe  mov     [rsp+arg_18], r9
0x180002203  sub     rsp, 68h
0x180002207  movdqa  [rsp+68h+var_48], xmm0
0x18000220d  movdqa  [rsp+68h+var_38], xmm1
0x180002213  movdqa  [rsp+68h+var_28], xmm2
0x180002219  movdqa  [rsp+68h+var_18], xmm3
0x18000221f  mov     rdx, rax
0x180002222  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_loadperf_dll
0x180002229  call    __delayLoadHelper2
0x18000222e  movdqa  xmm0, [rsp+68h+var_48]
0x180002234  movdqa  xmm1, [rsp+68h+var_38]
0x18000223a  movdqa  xmm2, [rsp+68h+var_28]
0x180002240  movdqa  xmm3, [rsp+68h+var_18]
0x180002246  mov     rcx, [rsp+68h+arg_0]
0x18000224b  mov     rdx, [rsp+68h+arg_8]
0x180002250  mov     r8, [rsp+68h+arg_10]
0x180002258  mov     r9, [rsp+68h+arg_18]
0x180002260  add     rsp, 68h
0x180002264  jmp     short $+2
0x180002266  jmp     rax
```
