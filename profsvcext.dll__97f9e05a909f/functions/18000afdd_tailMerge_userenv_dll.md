# __tailMerge_userenv_dll

- ea: `0x18000afdd`
- end: `0x18000b056`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b05c`
- `0x18000b221`
- `0x18000b2d0`
- `0x18000b2e2`
- `0x18000b37f`
- `0x18000b42e`

## callees

- `0x180004590`
- `0x18000afdd`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000afdd  mov     [rsp+arg_0], rcx
0x18000afe2  mov     [rsp+arg_8], rdx
0x18000afe7  mov     [rsp+arg_10], r8
0x18000afec  mov     [rsp+arg_18], r9
0x18000aff1  sub     rsp, 68h
0x18000aff5  movdqa  [rsp+68h+var_48], xmm0
0x18000affb  movdqa  [rsp+68h+var_38], xmm1
0x18000b001  movdqa  [rsp+68h+var_28], xmm2
0x18000b007  movdqa  [rsp+68h+var_18], xmm3
0x18000b00d  mov     rdx, rax
0x18000b010  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x18000b017  call    __delayLoadHelper2
0x18000b01c  movdqa  xmm0, [rsp+68h+var_48]
0x18000b022  movdqa  xmm1, [rsp+68h+var_38]
0x18000b028  movdqa  xmm2, [rsp+68h+var_28]
0x18000b02e  movdqa  xmm3, [rsp+68h+var_18]
0x18000b034  mov     rcx, [rsp+68h+arg_0]
0x18000b039  mov     rdx, [rsp+68h+arg_8]
0x18000b03e  mov     r8, [rsp+68h+arg_10]
0x18000b046  mov     r9, [rsp+68h+arg_18]
0x18000b04e  add     rsp, 68h
0x18000b052  jmp     short $+2
0x18000b054  jmp     rax
```
