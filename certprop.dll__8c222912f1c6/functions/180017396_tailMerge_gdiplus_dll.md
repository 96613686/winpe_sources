# __tailMerge_gdiplus_dll

- ea: `0x180017396`
- end: `0x18001740f`
- name: `__tailMerge_gdiplus_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017415`
- `0x180017427`
- `0x180017439`
- `0x18001744b`
- `0x18001745d`
- `0x18001746f`
- `0x180017481`
- `0x180017493`
- `0x1800174a5`
- `0x1800174b7`
- `0x1800174c9`
- `0x1800174db`

## callees

- `0x18000e1a0`
- `0x180017396`

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
0x180017396  mov     [rsp+arg_0], rcx
0x18001739b  mov     [rsp+arg_8], rdx
0x1800173a0  mov     [rsp+arg_10], r8
0x1800173a5  mov     [rsp+arg_18], r9
0x1800173aa  sub     rsp, 68h
0x1800173ae  movdqa  [rsp+68h+var_48], xmm0
0x1800173b4  movdqa  [rsp+68h+var_38], xmm1
0x1800173ba  movdqa  [rsp+68h+var_28], xmm2
0x1800173c0  movdqa  [rsp+68h+var_18], xmm3
0x1800173c6  mov     rdx, rax
0x1800173c9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdiplus_dll
0x1800173d0  call    __delayLoadHelper2
0x1800173d5  movdqa  xmm0, [rsp+68h+var_48]
0x1800173db  movdqa  xmm1, [rsp+68h+var_38]
0x1800173e1  movdqa  xmm2, [rsp+68h+var_28]
0x1800173e7  movdqa  xmm3, [rsp+68h+var_18]
0x1800173ed  mov     rcx, [rsp+68h+arg_0]
0x1800173f2  mov     rdx, [rsp+68h+arg_8]
0x1800173f7  mov     r8, [rsp+68h+arg_10]
0x1800173ff  mov     r9, [rsp+68h+arg_18]
0x180017407  add     rsp, 68h
0x18001740b  jmp     short $+2
0x18001740d  jmp     rax
```
