# __tailMerge_advapi32_dll

- ea: `0x180017196`
- end: `0x18001720f`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017215`
- `0x180017227`
- `0x180017239`
- `0x18001724b`
- `0x18001725d`
- `0x18001726f`
- `0x180017281`
- `0x180017293`
- `0x1800172a5`
- `0x1800172b7`
- `0x1800172c9`
- `0x1800172db`
- `0x1800172ed`

## callees

- `0x18000e1a0`
- `0x180017196`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017196  mov     [rsp+arg_0], rcx
0x18001719b  mov     [rsp+arg_8], rdx
0x1800171a0  mov     [rsp+arg_10], r8
0x1800171a5  mov     [rsp+arg_18], r9
0x1800171aa  sub     rsp, 68h
0x1800171ae  movdqa  [rsp+68h+var_48], xmm0
0x1800171b4  movdqa  [rsp+68h+var_38], xmm1
0x1800171ba  movdqa  [rsp+68h+var_28], xmm2
0x1800171c0  movdqa  [rsp+68h+var_18], xmm3
0x1800171c6  mov     rdx, rax
0x1800171c9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x1800171d0  call    __delayLoadHelper2
0x1800171d5  movdqa  xmm0, [rsp+68h+var_48]
0x1800171db  movdqa  xmm1, [rsp+68h+var_38]
0x1800171e1  movdqa  xmm2, [rsp+68h+var_28]
0x1800171e7  movdqa  xmm3, [rsp+68h+var_18]
0x1800171ed  mov     rcx, [rsp+68h+arg_0]
0x1800171f2  mov     rdx, [rsp+68h+arg_8]
0x1800171f7  mov     r8, [rsp+68h+arg_10]
0x1800171ff  mov     r9, [rsp+68h+arg_18]
0x180017207  add     rsp, 68h
0x18001720b  jmp     short $+2
0x18001720d  jmp     rax
```
