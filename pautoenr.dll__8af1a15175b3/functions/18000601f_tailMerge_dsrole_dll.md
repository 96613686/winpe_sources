# __tailMerge_dsrole_dll

- ea: `0x18000601f`
- end: `0x180006098`
- name: `__tailMerge_dsrole_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000609e`
- `0x1800060b0`

## callees

- `0x1800046b0`
- `0x18000601f`

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
0x18000601f  mov     [rsp+arg_0], rcx
0x180006024  mov     [rsp+arg_8], rdx
0x180006029  mov     [rsp+arg_10], r8
0x18000602e  mov     [rsp+arg_18], r9
0x180006033  sub     rsp, 68h
0x180006037  movdqa  [rsp+68h+var_48], xmm0
0x18000603d  movdqa  [rsp+68h+var_38], xmm1
0x180006043  movdqa  [rsp+68h+var_28], xmm2
0x180006049  movdqa  [rsp+68h+var_18], xmm3
0x18000604f  mov     rdx, rax
0x180006052  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dsrole_dll
0x180006059  call    __delayLoadHelper2
0x18000605e  movdqa  xmm0, [rsp+68h+var_48]
0x180006064  movdqa  xmm1, [rsp+68h+var_38]
0x18000606a  movdqa  xmm2, [rsp+68h+var_28]
0x180006070  movdqa  xmm3, [rsp+68h+var_18]
0x180006076  mov     rcx, [rsp+68h+arg_0]
0x18000607b  mov     rdx, [rsp+68h+arg_8]
0x180006080  mov     r8, [rsp+68h+arg_10]
0x180006088  mov     r9, [rsp+68h+arg_18]
0x180006090  add     rsp, 68h
0x180006094  jmp     short $+2
0x180006096  jmp     rax
```
