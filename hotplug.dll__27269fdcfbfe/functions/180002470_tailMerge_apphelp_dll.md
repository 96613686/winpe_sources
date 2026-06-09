# __tailMerge_apphelp_dll

- ea: `0x180002470`
- end: `0x1800024e9`
- name: `__tailMerge_apphelp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024ef`
- `0x180002501`
- `0x180002513`
- `0x180002525`
- `0x180002537`
- `0x180002549`
- `0x18000255b`
- `0x18000256d`

## callees

- `0x180002470`
- `0x180008600`

## pseudocode

```c
__int64 __fastcall _tailMerge_apphelp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_apphelp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002470  mov     [rsp+arg_0], rcx
0x180002475  mov     [rsp+arg_8], rdx
0x18000247a  mov     [rsp+arg_10], r8
0x18000247f  mov     [rsp+arg_18], r9
0x180002484  sub     rsp, 68h
0x180002488  movdqa  [rsp+68h+var_48], xmm0
0x18000248e  movdqa  [rsp+68h+var_38], xmm1
0x180002494  movdqa  [rsp+68h+var_28], xmm2
0x18000249a  movdqa  [rsp+68h+var_18], xmm3
0x1800024a0  mov     rdx, rax
0x1800024a3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_apphelp_dll
0x1800024aa  call    __delayLoadHelper2
0x1800024af  movdqa  xmm0, [rsp+68h+var_48]
0x1800024b5  movdqa  xmm1, [rsp+68h+var_38]
0x1800024bb  movdqa  xmm2, [rsp+68h+var_28]
0x1800024c1  movdqa  xmm3, [rsp+68h+var_18]
0x1800024c7  mov     rcx, [rsp+68h+arg_0]
0x1800024cc  mov     rdx, [rsp+68h+arg_8]
0x1800024d1  mov     r8, [rsp+68h+arg_10]
0x1800024d9  mov     r9, [rsp+68h+arg_18]
0x1800024e1  add     rsp, 68h
0x1800024e5  jmp     short $+2
0x1800024e7  jmp     rax
```
