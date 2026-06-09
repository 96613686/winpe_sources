# __tailMerge_user32_dll

- ea: `0x180001f5f`
- end: `0x180001fd8`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001fde`
- `0x180001ff0`
- `0x180002002`
- `0x180002014`
- `0x180002026`

## callees

- `0x180001f5f`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f5f  mov     [rsp+arg_0], rcx
0x180001f64  mov     [rsp+arg_8], rdx
0x180001f69  mov     [rsp+arg_10], r8
0x180001f6e  mov     [rsp+arg_18], r9
0x180001f73  sub     rsp, 68h
0x180001f77  movdqa  [rsp+68h+var_48], xmm0
0x180001f7d  movdqa  [rsp+68h+var_38], xmm1
0x180001f83  movdqa  [rsp+68h+var_28], xmm2
0x180001f89  movdqa  [rsp+68h+var_18], xmm3
0x180001f8f  mov     rdx, rax
0x180001f92  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180001f99  call    __delayLoadHelper2
0x180001f9e  movdqa  xmm0, [rsp+68h+var_48]
0x180001fa4  movdqa  xmm1, [rsp+68h+var_38]
0x180001faa  movdqa  xmm2, [rsp+68h+var_28]
0x180001fb0  movdqa  xmm3, [rsp+68h+var_18]
0x180001fb6  mov     rcx, [rsp+68h+arg_0]
0x180001fbb  mov     rdx, [rsp+68h+arg_8]
0x180001fc0  mov     r8, [rsp+68h+arg_10]
0x180001fc8  mov     r9, [rsp+68h+arg_18]
0x180001fd0  add     rsp, 68h
0x180001fd4  jmp     short $+2
0x180001fd6  jmp     rax
```
