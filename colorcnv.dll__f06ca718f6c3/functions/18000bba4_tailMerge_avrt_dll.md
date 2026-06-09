# __tailMerge_avrt_dll

- ea: `0x18000bba4`
- end: `0x18000bc1d`
- name: `__tailMerge_avrt_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bc23`
- `0x18000bc35`

## callees

- `0x1800089e0`
- `0x18000bba4`

## pseudocode

```c
__int64 __fastcall _tailMerge_avrt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_avrt_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000bba4  mov     [rsp+arg_0], rcx
0x18000bba9  mov     [rsp+arg_8], rdx
0x18000bbae  mov     [rsp+arg_10], r8
0x18000bbb3  mov     [rsp+arg_18], r9
0x18000bbb8  sub     rsp, 68h
0x18000bbbc  movdqa  [rsp+68h+var_48], xmm0
0x18000bbc2  movdqa  [rsp+68h+var_38], xmm1
0x18000bbc8  movdqa  [rsp+68h+var_28], xmm2
0x18000bbce  movdqa  [rsp+68h+var_18], xmm3
0x18000bbd4  mov     rdx, rax
0x18000bbd7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_avrt_dll
0x18000bbde  call    __delayLoadHelper2
0x18000bbe3  movdqa  xmm0, [rsp+68h+var_48]
0x18000bbe9  movdqa  xmm1, [rsp+68h+var_38]
0x18000bbef  movdqa  xmm2, [rsp+68h+var_28]
0x18000bbf5  movdqa  xmm3, [rsp+68h+var_18]
0x18000bbfb  mov     rcx, [rsp+68h+arg_0]
0x18000bc00  mov     rdx, [rsp+68h+arg_8]
0x18000bc05  mov     r8, [rsp+68h+arg_10]
0x18000bc0d  mov     r9, [rsp+68h+arg_18]
0x18000bc15  add     rsp, 68h
0x18000bc19  jmp     short $+2
0x18000bc1b  jmp     rax
```
