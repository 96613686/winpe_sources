# __tailMerge_shell32_dll

- ea: `0x18000a9b8`
- end: `0x18000aa31`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa37`

## callees

- `0x180006bb0`
- `0x18000a9b8`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a9b8  mov     [rsp+arg_0], rcx
0x18000a9bd  mov     [rsp+arg_8], rdx
0x18000a9c2  mov     [rsp+arg_10], r8
0x18000a9c7  mov     [rsp+arg_18], r9
0x18000a9cc  sub     rsp, 68h
0x18000a9d0  movdqa  [rsp+68h+var_48], xmm0
0x18000a9d6  movdqa  [rsp+68h+var_38], xmm1
0x18000a9dc  movdqa  [rsp+68h+var_28], xmm2
0x18000a9e2  movdqa  [rsp+68h+var_18], xmm3
0x18000a9e8  mov     rdx, rax
0x18000a9eb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x18000a9f2  call    __delayLoadHelper2
0x18000a9f7  movdqa  xmm0, [rsp+68h+var_48]
0x18000a9fd  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa03  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa09  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa0f  mov     rcx, [rsp+68h+arg_0]
0x18000aa14  mov     rdx, [rsp+68h+arg_8]
0x18000aa19  mov     r8, [rsp+68h+arg_10]
0x18000aa21  mov     r9, [rsp+68h+arg_18]
0x18000aa29  add     rsp, 68h
0x18000aa2d  jmp     short $+2
0x18000aa2f  jmp     rax
```
