# __tailMerge_fveapi_dll

- ea: `0x180002120`
- end: `0x180002199`
- name: `__tailMerge_fveapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000219f`

## callees

- `0x180002120`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_fveapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_fveapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002120  mov     [rsp+arg_0], rcx
0x180002125  mov     [rsp+arg_8], rdx
0x18000212a  mov     [rsp+arg_10], r8
0x18000212f  mov     [rsp+arg_18], r9
0x180002134  sub     rsp, 68h
0x180002138  movdqa  [rsp+68h+var_48], xmm0
0x18000213e  movdqa  [rsp+68h+var_38], xmm1
0x180002144  movdqa  [rsp+68h+var_28], xmm2
0x18000214a  movdqa  [rsp+68h+var_18], xmm3
0x180002150  mov     rdx, rax
0x180002153  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_fveapi_dll
0x18000215a  call    __delayLoadHelper2
0x18000215f  movdqa  xmm0, [rsp+68h+var_48]
0x180002165  movdqa  xmm1, [rsp+68h+var_38]
0x18000216b  movdqa  xmm2, [rsp+68h+var_28]
0x180002171  movdqa  xmm3, [rsp+68h+var_18]
0x180002177  mov     rcx, [rsp+68h+arg_0]
0x18000217c  mov     rdx, [rsp+68h+arg_8]
0x180002181  mov     r8, [rsp+68h+arg_10]
0x180002189  mov     r9, [rsp+68h+arg_18]
0x180002191  add     rsp, 68h
0x180002195  jmp     short $+2
0x180002197  jmp     rax
```
