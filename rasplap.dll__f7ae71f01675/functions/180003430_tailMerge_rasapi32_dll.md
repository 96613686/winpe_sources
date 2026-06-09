# __tailMerge_rasapi32_dll

- ea: `0x180003430`
- end: `0x1800034a9`
- name: `__tailMerge_rasapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800034af`
- `0x1800034c1`
- `0x1800034d3`
- `0x1800034e5`
- `0x1800034f7`
- `0x180003509`
- `0x18000351b`
- `0x18000352d`

## callees

- `0x1800015c0`
- `0x180003430`

## pseudocode

```c
__int64 __fastcall _tailMerge_rasapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rasapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003430  mov     [rsp+arg_0], rcx
0x180003435  mov     [rsp+arg_8], rdx
0x18000343a  mov     [rsp+arg_10], r8
0x18000343f  mov     [rsp+arg_18], r9
0x180003444  sub     rsp, 68h
0x180003448  movdqa  [rsp+68h+var_48], xmm0
0x18000344e  movdqa  [rsp+68h+var_38], xmm1
0x180003454  movdqa  [rsp+68h+var_28], xmm2
0x18000345a  movdqa  [rsp+68h+var_18], xmm3
0x180003460  mov     rdx, rax
0x180003463  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rasapi32_dll
0x18000346a  call    __delayLoadHelper2
0x18000346f  movdqa  xmm0, [rsp+68h+var_48]
0x180003475  movdqa  xmm1, [rsp+68h+var_38]
0x18000347b  movdqa  xmm2, [rsp+68h+var_28]
0x180003481  movdqa  xmm3, [rsp+68h+var_18]
0x180003487  mov     rcx, [rsp+68h+arg_0]
0x18000348c  mov     rdx, [rsp+68h+arg_8]
0x180003491  mov     r8, [rsp+68h+arg_10]
0x180003499  mov     r9, [rsp+68h+arg_18]
0x1800034a1  add     rsp, 68h
0x1800034a5  jmp     short $+2
0x1800034a7  jmp     rax
```
