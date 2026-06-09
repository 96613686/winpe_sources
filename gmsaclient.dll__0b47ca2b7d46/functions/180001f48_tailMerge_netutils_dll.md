# __tailMerge_netutils_dll

- ea: `0x180001f48`
- end: `0x180001fc1`
- name: `__tailMerge_netutils_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001fc7`
- `0x180002021`

## callees

- `0x180001f48`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall _tailMerge_netutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_netutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f48  mov     [rsp+arg_0], rcx
0x180001f4d  mov     [rsp+arg_8], rdx
0x180001f52  mov     [rsp+arg_10], r8
0x180001f57  mov     [rsp+arg_18], r9
0x180001f5c  sub     rsp, 68h
0x180001f60  movdqa  [rsp+68h+var_48], xmm0
0x180001f66  movdqa  [rsp+68h+var_38], xmm1
0x180001f6c  movdqa  [rsp+68h+var_28], xmm2
0x180001f72  movdqa  [rsp+68h+var_18], xmm3
0x180001f78  mov     rdx, rax
0x180001f7b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_netutils_dll
0x180001f82  call    __delayLoadHelper2
0x180001f87  movdqa  xmm0, [rsp+68h+var_48]
0x180001f8d  movdqa  xmm1, [rsp+68h+var_38]
0x180001f93  movdqa  xmm2, [rsp+68h+var_28]
0x180001f99  movdqa  xmm3, [rsp+68h+var_18]
0x180001f9f  mov     rcx, [rsp+68h+arg_0]
0x180001fa4  mov     rdx, [rsp+68h+arg_8]
0x180001fa9  mov     r8, [rsp+68h+arg_10]
0x180001fb1  mov     r9, [rsp+68h+arg_18]
0x180001fb9  add     rsp, 68h
0x180001fbd  jmp     short $+2
0x180001fbf  jmp     rax
```
