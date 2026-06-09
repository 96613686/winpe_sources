# __tailMerge_efscore_dll

- ea: `0x18000236e`
- end: `0x1800023e7`
- name: `__tailMerge_efscore_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `65`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800023ed`
- `0x1800023ff`
- `0x180002411`
- `0x180002423`
- `0x180002435`
- `0x180002447`
- `0x180002459`
- `0x18000246b`
- `0x18000247d`
- `0x18000248f`
- `0x1800024a1`
- `0x1800024b3`
- `0x1800024c5`
- `0x1800024d7`
- `0x1800024e9`
- `0x1800024fb`
- `0x18000250d`
- `0x18000251f`
- `0x180002531`
- `0x180002543`
- `0x180002555`
- `0x180002567`
- `0x180002579`
- `0x18000258b`
- `0x18000259d`
- `0x1800025af`
- `0x1800025c1`
- `0x1800025d3`
- `0x1800025e5`
- `0x1800025f7`
- `0x180002609`
- `0x18000261b`
- `0x18000262d`
- `0x18000263f`
- `0x180002651`
- `0x180002663`
- `0x180002675`
- `0x180002687`
- `0x180002699`
- `0x1800026ab`
- `0x1800026bd`
- `0x1800026cf`
- `0x1800026e1`
- `0x1800026f3`
- `0x180002705`
- `0x180002717`
- `0x180002729`
- `0x18000273b`
- `0x18000274d`
- `0x18000275f`

## callees

- `0x18000236e`
- `0x180007e40`

## pseudocode

```c
__int64 __fastcall _tailMerge_efscore_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_efscore_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000236e  mov     [rsp+arg_0], rcx
0x180002373  mov     [rsp+arg_8], rdx
0x180002378  mov     [rsp+arg_10], r8
0x18000237d  mov     [rsp+arg_18], r9
0x180002382  sub     rsp, 68h
0x180002386  movdqa  [rsp+68h+var_48], xmm0
0x18000238c  movdqa  [rsp+68h+var_38], xmm1
0x180002392  movdqa  [rsp+68h+var_28], xmm2
0x180002398  movdqa  [rsp+68h+var_18], xmm3
0x18000239e  mov     rdx, rax
0x1800023a1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_efscore_dll
0x1800023a8  call    __delayLoadHelper2
0x1800023ad  movdqa  xmm0, [rsp+68h+var_48]
0x1800023b3  movdqa  xmm1, [rsp+68h+var_38]
0x1800023b9  movdqa  xmm2, [rsp+68h+var_28]
0x1800023bf  movdqa  xmm3, [rsp+68h+var_18]
0x1800023c5  mov     rcx, [rsp+68h+arg_0]
0x1800023ca  mov     rdx, [rsp+68h+arg_8]
0x1800023cf  mov     r8, [rsp+68h+arg_10]
0x1800023d7  mov     r9, [rsp+68h+arg_18]
0x1800023df  add     rsp, 68h
0x1800023e3  jmp     short $+2
0x1800023e5  jmp     rax
```
