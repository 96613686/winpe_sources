# __tailMerge_winnsi_dll

- ea: `0x18001a917`
- end: `0x18001a990`
- name: `__tailMerge_winnsi_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a996`
- `0x18001a9a8`
- `0x18001a9ba`
- `0x18001a9cc`

## callees

- `0x18000f880`
- `0x18001a917`

## pseudocode

```c
__int64 __fastcall _tailMerge_winnsi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winnsi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a917  mov     [rsp+arg_0], rcx
0x18001a91c  mov     [rsp+arg_8], rdx
0x18001a921  mov     [rsp+arg_10], r8
0x18001a926  mov     [rsp+arg_18], r9
0x18001a92b  sub     rsp, 68h
0x18001a92f  movdqa  [rsp+68h+var_48], xmm0
0x18001a935  movdqa  [rsp+68h+var_38], xmm1
0x18001a93b  movdqa  [rsp+68h+var_28], xmm2
0x18001a941  movdqa  [rsp+68h+var_18], xmm3
0x18001a947  mov     rdx, rax
0x18001a94a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winnsi_dll
0x18001a951  call    __delayLoadHelper2
0x18001a956  movdqa  xmm0, [rsp+68h+var_48]
0x18001a95c  movdqa  xmm1, [rsp+68h+var_38]
0x18001a962  movdqa  xmm2, [rsp+68h+var_28]
0x18001a968  movdqa  xmm3, [rsp+68h+var_18]
0x18001a96e  mov     rcx, [rsp+68h+arg_0]
0x18001a973  mov     rdx, [rsp+68h+arg_8]
0x18001a978  mov     r8, [rsp+68h+arg_10]
0x18001a980  mov     r9, [rsp+68h+arg_18]
0x18001a988  add     rsp, 68h
0x18001a98c  jmp     short $+2
0x18001a98e  jmp     rax
```
