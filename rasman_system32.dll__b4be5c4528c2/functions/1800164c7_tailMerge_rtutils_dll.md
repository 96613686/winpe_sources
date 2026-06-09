# __tailMerge_rtutils_dll

- ea: `0x1800164c7`
- end: `0x180016540`
- name: `__tailMerge_rtutils_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016546`
- `0x180016710`
- `0x180016722`

## callees

- `0x180014ae0`
- `0x1800164c7`

## pseudocode

```c
__int64 __fastcall _tailMerge_rtutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rtutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800164c7  mov     [rsp+arg_0], rcx
0x1800164cc  mov     [rsp+arg_8], rdx
0x1800164d1  mov     [rsp+arg_10], r8
0x1800164d6  mov     [rsp+arg_18], r9
0x1800164db  sub     rsp, 68h
0x1800164df  movdqa  [rsp+68h+var_48], xmm0
0x1800164e5  movdqa  [rsp+68h+var_38], xmm1
0x1800164eb  movdqa  [rsp+68h+var_28], xmm2
0x1800164f1  movdqa  [rsp+68h+var_18], xmm3
0x1800164f7  mov     rdx, rax
0x1800164fa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rtutils_dll
0x180016501  call    __delayLoadHelper2
0x180016506  movdqa  xmm0, [rsp+68h+var_48]
0x18001650c  movdqa  xmm1, [rsp+68h+var_38]
0x180016512  movdqa  xmm2, [rsp+68h+var_28]
0x180016518  movdqa  xmm3, [rsp+68h+var_18]
0x18001651e  mov     rcx, [rsp+68h+arg_0]
0x180016523  mov     rdx, [rsp+68h+arg_8]
0x180016528  mov     r8, [rsp+68h+arg_10]
0x180016530  mov     r9, [rsp+68h+arg_18]
0x180016538  add     rsp, 68h
0x18001653c  jmp     short $+2
0x18001653e  jmp     rax
```
