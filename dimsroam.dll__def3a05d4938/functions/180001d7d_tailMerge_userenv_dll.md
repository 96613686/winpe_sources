# __tailMerge_userenv_dll

- ea: `0x180001d7d`
- end: `0x180001df6`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001dfc`

## callees

- `0x180001d7d`
- `0x18000d7b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d7d  mov     [rsp+arg_0], rcx
0x180001d82  mov     [rsp+arg_8], rdx
0x180001d87  mov     [rsp+arg_10], r8
0x180001d8c  mov     [rsp+arg_18], r9
0x180001d91  sub     rsp, 68h
0x180001d95  movdqa  [rsp+68h+var_48], xmm0
0x180001d9b  movdqa  [rsp+68h+var_38], xmm1
0x180001da1  movdqa  [rsp+68h+var_28], xmm2
0x180001da7  movdqa  [rsp+68h+var_18], xmm3
0x180001dad  mov     rdx, rax
0x180001db0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180001db7  call    __delayLoadHelper2
0x180001dbc  movdqa  xmm0, [rsp+68h+var_48]
0x180001dc2  movdqa  xmm1, [rsp+68h+var_38]
0x180001dc8  movdqa  xmm2, [rsp+68h+var_28]
0x180001dce  movdqa  xmm3, [rsp+68h+var_18]
0x180001dd4  mov     rcx, [rsp+68h+arg_0]
0x180001dd9  mov     rdx, [rsp+68h+arg_8]
0x180001dde  mov     r8, [rsp+68h+arg_10]
0x180001de6  mov     r9, [rsp+68h+arg_18]
0x180001dee  add     rsp, 68h
0x180001df2  jmp     short $+2
0x180001df4  jmp     rax
```
