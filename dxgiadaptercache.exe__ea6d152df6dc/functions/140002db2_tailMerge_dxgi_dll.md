# __tailMerge_dxgi_dll

- ea: `0x140002db2`
- end: `0x140002e2b`
- name: `__tailMerge_dxgi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002e31`

## callees

- `0x140002db2`
- `0x140011270`

## pseudocode

```c
__int64 __fastcall _tailMerge_dxgi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dxgi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002db2  mov     [rsp+arg_0], rcx
0x140002db7  mov     [rsp+arg_8], rdx
0x140002dbc  mov     [rsp+arg_10], r8
0x140002dc1  mov     [rsp+arg_18], r9
0x140002dc6  sub     rsp, 68h
0x140002dca  movdqa  [rsp+68h+var_48], xmm0
0x140002dd0  movdqa  [rsp+68h+var_38], xmm1
0x140002dd6  movdqa  [rsp+68h+var_28], xmm2
0x140002ddc  movdqa  [rsp+68h+var_18], xmm3
0x140002de2  mov     rdx, rax
0x140002de5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dxgi_dll
0x140002dec  call    __delayLoadHelper2
0x140002df1  movdqa  xmm0, [rsp+68h+var_48]
0x140002df7  movdqa  xmm1, [rsp+68h+var_38]
0x140002dfd  movdqa  xmm2, [rsp+68h+var_28]
0x140002e03  movdqa  xmm3, [rsp+68h+var_18]
0x140002e09  mov     rcx, [rsp+68h+arg_0]
0x140002e0e  mov     rdx, [rsp+68h+arg_8]
0x140002e13  mov     r8, [rsp+68h+arg_10]
0x140002e1b  mov     r9, [rsp+68h+arg_18]
0x140002e23  add     rsp, 68h
0x140002e27  jmp     short $+2
0x140002e29  jmp     rax
```
