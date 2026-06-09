# __tailMerge_rpcrt4_dll

- ea: `0x18000aba0`
- end: `0x18000ac19`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ac1f`
- `0x18000ac31`
- `0x18000ac43`
- `0x18000b3ae`
- `0x18000b3c0`
- `0x18000b3d2`

## callees

- `0x1800079c0`
- `0x18000aba0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aba0  mov     [rsp+arg_0], rcx
0x18000aba5  mov     [rsp+arg_8], rdx
0x18000abaa  mov     [rsp+arg_10], r8
0x18000abaf  mov     [rsp+arg_18], r9
0x18000abb4  sub     rsp, 68h
0x18000abb8  movdqa  [rsp+68h+var_48], xmm0
0x18000abbe  movdqa  [rsp+68h+var_38], xmm1
0x18000abc4  movdqa  [rsp+68h+var_28], xmm2
0x18000abca  movdqa  [rsp+68h+var_18], xmm3
0x18000abd0  mov     rdx, rax
0x18000abd3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000abda  call    __delayLoadHelper2
0x18000abdf  movdqa  xmm0, [rsp+68h+var_48]
0x18000abe5  movdqa  xmm1, [rsp+68h+var_38]
0x18000abeb  movdqa  xmm2, [rsp+68h+var_28]
0x18000abf1  movdqa  xmm3, [rsp+68h+var_18]
0x18000abf7  mov     rcx, [rsp+68h+arg_0]
0x18000abfc  mov     rdx, [rsp+68h+arg_8]
0x18000ac01  mov     r8, [rsp+68h+arg_10]
0x18000ac09  mov     r9, [rsp+68h+arg_18]
0x18000ac11  add     rsp, 68h
0x18000ac15  jmp     short $+2
0x18000ac17  jmp     rax
```
