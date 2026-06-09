# __tailMerge_iphlpapi_dll

- ea: `0x180001294`
- end: `0x18000130d`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001313`
- `0x180001325`

## callees

- `0x180001294`
- `0x180002f40`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001294  mov     [rsp+arg_0], rcx
0x180001299  mov     [rsp+arg_8], rdx
0x18000129e  mov     [rsp+arg_10], r8
0x1800012a3  mov     [rsp+arg_18], r9
0x1800012a8  sub     rsp, 68h
0x1800012ac  movdqa  [rsp+68h+var_48], xmm0
0x1800012b2  movdqa  [rsp+68h+var_38], xmm1
0x1800012b8  movdqa  [rsp+68h+var_28], xmm2
0x1800012be  movdqa  [rsp+68h+var_18], xmm3
0x1800012c4  mov     rdx, rax
0x1800012c7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x1800012ce  call    __delayLoadHelper2
0x1800012d3  movdqa  xmm0, [rsp+68h+var_48]
0x1800012d9  movdqa  xmm1, [rsp+68h+var_38]
0x1800012df  movdqa  xmm2, [rsp+68h+var_28]
0x1800012e5  movdqa  xmm3, [rsp+68h+var_18]
0x1800012eb  mov     rcx, [rsp+68h+arg_0]
0x1800012f0  mov     rdx, [rsp+68h+arg_8]
0x1800012f5  mov     r8, [rsp+68h+arg_10]
0x1800012fd  mov     r9, [rsp+68h+arg_18]
0x180001305  add     rsp, 68h
0x180001309  jmp     short $+2
0x18000130b  jmp     rax
```
