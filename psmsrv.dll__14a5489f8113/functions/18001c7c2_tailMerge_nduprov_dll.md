# __tailMerge_nduprov_dll

- ea: `0x18001c7c2`
- end: `0x18001c83b`
- name: `__tailMerge_nduprov_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c841`
- `0x18001c853`
- `0x18001c865`
- `0x18001c877`
- `0x18001c889`
- `0x18001c89b`
- `0x18001c8ad`

## callees

- `0x1800174f0`
- `0x18001c7c2`

## pseudocode

```c
__int64 __fastcall _tailMerge_nduprov_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_nduprov_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c7c2  mov     [rsp+arg_0], rcx
0x18001c7c7  mov     [rsp+arg_8], rdx
0x18001c7cc  mov     [rsp+arg_10], r8
0x18001c7d1  mov     [rsp+arg_18], r9
0x18001c7d6  sub     rsp, 68h
0x18001c7da  movdqa  [rsp+68h+var_48], xmm0
0x18001c7e0  movdqa  [rsp+68h+var_38], xmm1
0x18001c7e6  movdqa  [rsp+68h+var_28], xmm2
0x18001c7ec  movdqa  [rsp+68h+var_18], xmm3
0x18001c7f2  mov     rdx, rax
0x18001c7f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_nduprov_dll
0x18001c7fc  call    __delayLoadHelper2
0x18001c801  movdqa  xmm0, [rsp+68h+var_48]
0x18001c807  movdqa  xmm1, [rsp+68h+var_38]
0x18001c80d  movdqa  xmm2, [rsp+68h+var_28]
0x18001c813  movdqa  xmm3, [rsp+68h+var_18]
0x18001c819  mov     rcx, [rsp+68h+arg_0]
0x18001c81e  mov     rdx, [rsp+68h+arg_8]
0x18001c823  mov     r8, [rsp+68h+arg_10]
0x18001c82b  mov     r9, [rsp+68h+arg_18]
0x18001c833  add     rsp, 68h
0x18001c837  jmp     short $+2
0x18001c839  jmp     rax
```
