# __tailMerge_gdiplus_dll

- ea: `0x140010e6f`
- end: `0x140010ee8`
- name: `__tailMerge_gdiplus_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010eee`
- `0x140010f00`
- `0x140010f12`
- `0x140010f24`
- `0x140010f36`
- `0x140010f48`
- `0x140010f5a`

## callees

- `0x1400083b0`
- `0x140010e6f`

## pseudocode

```c
__int64 __fastcall _tailMerge_gdiplus_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_gdiplus_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010e6f  mov     [rsp+arg_0], rcx
0x140010e74  mov     [rsp+arg_8], rdx
0x140010e79  mov     [rsp+arg_10], r8
0x140010e7e  mov     [rsp+arg_18], r9
0x140010e83  sub     rsp, 68h
0x140010e87  movdqa  [rsp+68h+var_48], xmm0
0x140010e8d  movdqa  [rsp+68h+var_38], xmm1
0x140010e93  movdqa  [rsp+68h+var_28], xmm2
0x140010e99  movdqa  [rsp+68h+var_18], xmm3
0x140010e9f  mov     rdx, rax
0x140010ea2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdiplus_dll
0x140010ea9  call    __delayLoadHelper2
0x140010eae  movdqa  xmm0, [rsp+68h+var_48]
0x140010eb4  movdqa  xmm1, [rsp+68h+var_38]
0x140010eba  movdqa  xmm2, [rsp+68h+var_28]
0x140010ec0  movdqa  xmm3, [rsp+68h+var_18]
0x140010ec6  mov     rcx, [rsp+68h+arg_0]
0x140010ecb  mov     rdx, [rsp+68h+arg_8]
0x140010ed0  mov     r8, [rsp+68h+arg_10]
0x140010ed8  mov     r9, [rsp+68h+arg_18]
0x140010ee0  add     rsp, 68h
0x140010ee4  jmp     short $+2
0x140010ee6  jmp     rax
```
