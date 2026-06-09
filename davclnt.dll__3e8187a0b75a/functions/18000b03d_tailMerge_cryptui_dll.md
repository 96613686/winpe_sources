# __tailMerge_cryptui_dll

- ea: `0x18000b03d`
- end: `0x18000b0b6`
- name: `__tailMerge_cryptui_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b0bc`

## callees

- `0x1800079c0`
- `0x18000b03d`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptui_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_cryptui_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b03d  mov     [rsp+arg_0], rcx
0x18000b042  mov     [rsp+arg_8], rdx
0x18000b047  mov     [rsp+arg_10], r8
0x18000b04c  mov     [rsp+arg_18], r9
0x18000b051  sub     rsp, 68h
0x18000b055  movdqa  [rsp+68h+var_48], xmm0
0x18000b05b  movdqa  [rsp+68h+var_38], xmm1
0x18000b061  movdqa  [rsp+68h+var_28], xmm2
0x18000b067  movdqa  [rsp+68h+var_18], xmm3
0x18000b06d  mov     rdx, rax
0x18000b070  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptui_dll
0x18000b077  call    __delayLoadHelper2
0x18000b07c  movdqa  xmm0, [rsp+68h+var_48]
0x18000b082  movdqa  xmm1, [rsp+68h+var_38]
0x18000b088  movdqa  xmm2, [rsp+68h+var_28]
0x18000b08e  movdqa  xmm3, [rsp+68h+var_18]
0x18000b094  mov     rcx, [rsp+68h+arg_0]
0x18000b099  mov     rdx, [rsp+68h+arg_8]
0x18000b09e  mov     r8, [rsp+68h+arg_10]
0x18000b0a6  mov     r9, [rsp+68h+arg_18]
0x18000b0ae  add     rsp, 68h
0x18000b0b2  jmp     short $+2
0x18000b0b4  jmp     rax
```
