# __tailMerge_oleaut32_dll

- ea: `0x180001c60`
- end: `0x180001cd9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001cdf`
- `0x180001cf1`

## callees

- `0x180001c60`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c60  mov     [rsp+arg_0], rcx
0x180001c65  mov     [rsp+arg_8], rdx
0x180001c6a  mov     [rsp+arg_10], r8
0x180001c6f  mov     [rsp+arg_18], r9
0x180001c74  sub     rsp, 68h
0x180001c78  movdqa  [rsp+68h+var_48], xmm0
0x180001c7e  movdqa  [rsp+68h+var_38], xmm1
0x180001c84  movdqa  [rsp+68h+var_28], xmm2
0x180001c8a  movdqa  [rsp+68h+var_18], xmm3
0x180001c90  mov     rdx, rax
0x180001c93  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180001c9a  call    __delayLoadHelper2
0x180001c9f  movdqa  xmm0, [rsp+68h+var_48]
0x180001ca5  movdqa  xmm1, [rsp+68h+var_38]
0x180001cab  movdqa  xmm2, [rsp+68h+var_28]
0x180001cb1  movdqa  xmm3, [rsp+68h+var_18]
0x180001cb7  mov     rcx, [rsp+68h+arg_0]
0x180001cbc  mov     rdx, [rsp+68h+arg_8]
0x180001cc1  mov     r8, [rsp+68h+arg_10]
0x180001cc9  mov     r9, [rsp+68h+arg_18]
0x180001cd1  add     rsp, 68h
0x180001cd5  jmp     short $+2
0x180001cd7  jmp     rax
```
