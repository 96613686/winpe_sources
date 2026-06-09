# __tailMerge_dsrole_dll

- ea: `0x180001e08`
- end: `0x180001e81`
- name: `__tailMerge_dsrole_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e87`
- `0x180001e99`

## callees

- `0x180001e08`
- `0x18000d7b0`

## pseudocode

```c
__int64 __fastcall _tailMerge_dsrole_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dsrole_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e08  mov     [rsp+arg_0], rcx
0x180001e0d  mov     [rsp+arg_8], rdx
0x180001e12  mov     [rsp+arg_10], r8
0x180001e17  mov     [rsp+arg_18], r9
0x180001e1c  sub     rsp, 68h
0x180001e20  movdqa  [rsp+68h+var_48], xmm0
0x180001e26  movdqa  [rsp+68h+var_38], xmm1
0x180001e2c  movdqa  [rsp+68h+var_28], xmm2
0x180001e32  movdqa  [rsp+68h+var_18], xmm3
0x180001e38  mov     rdx, rax
0x180001e3b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsrole_dll
0x180001e42  call    __delayLoadHelper2
0x180001e47  movdqa  xmm0, [rsp+68h+var_48]
0x180001e4d  movdqa  xmm1, [rsp+68h+var_38]
0x180001e53  movdqa  xmm2, [rsp+68h+var_28]
0x180001e59  movdqa  xmm3, [rsp+68h+var_18]
0x180001e5f  mov     rcx, [rsp+68h+arg_0]
0x180001e64  mov     rdx, [rsp+68h+arg_8]
0x180001e69  mov     r8, [rsp+68h+arg_10]
0x180001e71  mov     r9, [rsp+68h+arg_18]
0x180001e79  add     rsp, 68h
0x180001e7d  jmp     short $+2
0x180001e7f  jmp     rax
```
