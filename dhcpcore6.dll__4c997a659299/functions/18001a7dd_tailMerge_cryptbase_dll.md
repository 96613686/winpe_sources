# __tailMerge_cryptbase_dll

- ea: `0x18001a7dd`
- end: `0x18001a856`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a85c`

## callees

- `0x18000f880`
- `0x18001a7dd`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a7dd  mov     [rsp+arg_0], rcx
0x18001a7e2  mov     [rsp+arg_8], rdx
0x18001a7e7  mov     [rsp+arg_10], r8
0x18001a7ec  mov     [rsp+arg_18], r9
0x18001a7f1  sub     rsp, 68h
0x18001a7f5  movdqa  [rsp+68h+var_48], xmm0
0x18001a7fb  movdqa  [rsp+68h+var_38], xmm1
0x18001a801  movdqa  [rsp+68h+var_28], xmm2
0x18001a807  movdqa  [rsp+68h+var_18], xmm3
0x18001a80d  mov     rdx, rax
0x18001a810  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x18001a817  call    __delayLoadHelper2
0x18001a81c  movdqa  xmm0, [rsp+68h+var_48]
0x18001a822  movdqa  xmm1, [rsp+68h+var_38]
0x18001a828  movdqa  xmm2, [rsp+68h+var_28]
0x18001a82e  movdqa  xmm3, [rsp+68h+var_18]
0x18001a834  mov     rcx, [rsp+68h+arg_0]
0x18001a839  mov     rdx, [rsp+68h+arg_8]
0x18001a83e  mov     r8, [rsp+68h+arg_10]
0x18001a846  mov     r9, [rsp+68h+arg_18]
0x18001a84e  add     rsp, 68h
0x18001a852  jmp     short $+2
0x18001a854  jmp     rax
```
