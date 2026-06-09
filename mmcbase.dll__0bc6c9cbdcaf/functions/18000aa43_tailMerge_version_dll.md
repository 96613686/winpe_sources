# __tailMerge_version_dll

- ea: `0x18000aa43`
- end: `0x18000aabc`
- name: `__tailMerge_version_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aac2`
- `0x18000aad4`
- `0x18000aae6`

## callees

- `0x180006bb0`
- `0x18000aa43`

## pseudocode

```c
__int64 __fastcall _tailMerge_version_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_version_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aa43  mov     [rsp+arg_0], rcx
0x18000aa48  mov     [rsp+arg_8], rdx
0x18000aa4d  mov     [rsp+arg_10], r8
0x18000aa52  mov     [rsp+arg_18], r9
0x18000aa57  sub     rsp, 68h
0x18000aa5b  movdqa  [rsp+68h+var_48], xmm0
0x18000aa61  movdqa  [rsp+68h+var_38], xmm1
0x18000aa67  movdqa  [rsp+68h+var_28], xmm2
0x18000aa6d  movdqa  [rsp+68h+var_18], xmm3
0x18000aa73  mov     rdx, rax
0x18000aa76  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_version_dll
0x18000aa7d  call    __delayLoadHelper2
0x18000aa82  movdqa  xmm0, [rsp+68h+var_48]
0x18000aa88  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa8e  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa94  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa9a  mov     rcx, [rsp+68h+arg_0]
0x18000aa9f  mov     rdx, [rsp+68h+arg_8]
0x18000aaa4  mov     r8, [rsp+68h+arg_10]
0x18000aaac  mov     r9, [rsp+68h+arg_18]
0x18000aab4  add     rsp, 68h
0x18000aab8  jmp     short $+2
0x18000aaba  jmp     rax
```
