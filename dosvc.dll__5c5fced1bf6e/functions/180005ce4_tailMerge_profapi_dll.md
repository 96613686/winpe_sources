# __tailMerge_profapi_dll

- ea: `0x180005ce4`
- end: `0x180005d5d`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005d63`

## callees

- `0x1800023e0`
- `0x180005ce4`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180005ce4  mov     [rsp+arg_0], rcx
0x180005ce9  mov     [rsp+arg_8], rdx
0x180005cee  mov     [rsp+arg_10], r8
0x180005cf3  mov     [rsp+arg_18], r9
0x180005cf8  sub     rsp, 68h
0x180005cfc  movdqa  [rsp+68h+var_48], xmm0
0x180005d02  movdqa  [rsp+68h+var_38], xmm1
0x180005d08  movdqa  [rsp+68h+var_28], xmm2
0x180005d0e  movdqa  [rsp+68h+var_18], xmm3
0x180005d14  mov     rdx, rax
0x180005d17  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x180005d1e  call    __delayLoadHelper2
0x180005d23  movdqa  xmm0, [rsp+68h+var_48]
0x180005d29  movdqa  xmm1, [rsp+68h+var_38]
0x180005d2f  movdqa  xmm2, [rsp+68h+var_28]
0x180005d35  movdqa  xmm3, [rsp+68h+var_18]
0x180005d3b  mov     rcx, [rsp+68h+arg_0]
0x180005d40  mov     rdx, [rsp+68h+arg_8]
0x180005d45  mov     r8, [rsp+68h+arg_10]
0x180005d4d  mov     r9, [rsp+68h+arg_18]
0x180005d55  add     rsp, 68h
0x180005d59  jmp     short $+2
0x180005d5b  jmp     rax
```
