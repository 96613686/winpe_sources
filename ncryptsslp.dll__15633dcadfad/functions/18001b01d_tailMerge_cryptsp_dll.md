# __tailMerge_cryptsp_dll

- ea: `0x18001b01d`
- end: `0x18001b096`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001b09c`

## callees

- `0x18001b01d`
- `0x180024ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001b01d  mov     [rsp+arg_0], rcx
0x18001b022  mov     [rsp+arg_8], rdx
0x18001b027  mov     [rsp+arg_10], r8
0x18001b02c  mov     [rsp+arg_18], r9
0x18001b031  sub     rsp, 68h
0x18001b035  movdqa  [rsp+68h+var_48], xmm0
0x18001b03b  movdqa  [rsp+68h+var_38], xmm1
0x18001b041  movdqa  [rsp+68h+var_28], xmm2
0x18001b047  movdqa  [rsp+68h+var_18], xmm3
0x18001b04d  mov     rdx, rax
0x18001b050  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x18001b057  call    __delayLoadHelper2
0x18001b05c  movdqa  xmm0, [rsp+68h+var_48]
0x18001b062  movdqa  xmm1, [rsp+68h+var_38]
0x18001b068  movdqa  xmm2, [rsp+68h+var_28]
0x18001b06e  movdqa  xmm3, [rsp+68h+var_18]
0x18001b074  mov     rcx, [rsp+68h+arg_0]
0x18001b079  mov     rdx, [rsp+68h+arg_8]
0x18001b07e  mov     r8, [rsp+68h+arg_10]
0x18001b086  mov     r9, [rsp+68h+arg_18]
0x18001b08e  add     rsp, 68h
0x18001b092  jmp     short $+2
0x18001b094  jmp     rax
```
