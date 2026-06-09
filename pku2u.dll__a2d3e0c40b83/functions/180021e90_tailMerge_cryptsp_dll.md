# __tailMerge_cryptsp_dll

- ea: `0x180021e90`
- end: `0x180021f09`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021f0f`
- `0x180021fbe`
- `0x180021fd0`
- `0x180021fe2`
- `0x180021ff4`
- `0x180022006`
- `0x180022018`
- `0x18002202a`

## callees

- `0x18001a6d0`
- `0x180021e90`

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
0x180021e90  mov     [rsp+arg_0], rcx
0x180021e95  mov     [rsp+arg_8], rdx
0x180021e9a  mov     [rsp+arg_10], r8
0x180021e9f  mov     [rsp+arg_18], r9
0x180021ea4  sub     rsp, 68h
0x180021ea8  movdqa  [rsp+68h+var_48], xmm0
0x180021eae  movdqa  [rsp+68h+var_38], xmm1
0x180021eb4  movdqa  [rsp+68h+var_28], xmm2
0x180021eba  movdqa  [rsp+68h+var_18], xmm3
0x180021ec0  mov     rdx, rax
0x180021ec3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x180021eca  call    __delayLoadHelper2
0x180021ecf  movdqa  xmm0, [rsp+68h+var_48]
0x180021ed5  movdqa  xmm1, [rsp+68h+var_38]
0x180021edb  movdqa  xmm2, [rsp+68h+var_28]
0x180021ee1  movdqa  xmm3, [rsp+68h+var_18]
0x180021ee7  mov     rcx, [rsp+68h+arg_0]
0x180021eec  mov     rdx, [rsp+68h+arg_8]
0x180021ef1  mov     r8, [rsp+68h+arg_10]
0x180021ef9  mov     r9, [rsp+68h+arg_18]
0x180021f01  add     rsp, 68h
0x180021f05  jmp     short $+2
0x180021f07  jmp     rax
```
