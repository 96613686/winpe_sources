# __tailMerge_crypt32_dll

- ea: `0x180001d88`
- end: `0x180001e01`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e07`
- `0x180001f2f`

## callees

- `0x180001d88`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d88  mov     [rsp+arg_0], rcx
0x180001d8d  mov     [rsp+arg_8], rdx
0x180001d92  mov     [rsp+arg_10], r8
0x180001d97  mov     [rsp+arg_18], r9
0x180001d9c  sub     rsp, 68h
0x180001da0  movdqa  [rsp+68h+var_48], xmm0
0x180001da6  movdqa  [rsp+68h+var_38], xmm1
0x180001dac  movdqa  [rsp+68h+var_28], xmm2
0x180001db2  movdqa  [rsp+68h+var_18], xmm3
0x180001db8  mov     rdx, rax
0x180001dbb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180001dc2  call    __delayLoadHelper2
0x180001dc7  movdqa  xmm0, [rsp+68h+var_48]
0x180001dcd  movdqa  xmm1, [rsp+68h+var_38]
0x180001dd3  movdqa  xmm2, [rsp+68h+var_28]
0x180001dd9  movdqa  xmm3, [rsp+68h+var_18]
0x180001ddf  mov     rcx, [rsp+68h+arg_0]
0x180001de4  mov     rdx, [rsp+68h+arg_8]
0x180001de9  mov     r8, [rsp+68h+arg_10]
0x180001df1  mov     r9, [rsp+68h+arg_18]
0x180001df9  add     rsp, 68h
0x180001dfd  jmp     short $+2
0x180001dff  jmp     rax
```
