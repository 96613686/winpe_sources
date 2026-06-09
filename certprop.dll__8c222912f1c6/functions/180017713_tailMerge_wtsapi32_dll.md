# __tailMerge_wtsapi32_dll

- ea: `0x180017713`
- end: `0x18001778c`
- name: `__tailMerge_wtsapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017792`
- `0x1800177a4`
- `0x1800177b6`
- `0x1800177c8`
- `0x1800177da`
- `0x1800177ec`

## callees

- `0x18000e1a0`
- `0x180017713`

## pseudocode

```c
__int64 __fastcall _tailMerge_wtsapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017713  mov     [rsp+arg_0], rcx
0x180017718  mov     [rsp+arg_8], rdx
0x18001771d  mov     [rsp+arg_10], r8
0x180017722  mov     [rsp+arg_18], r9
0x180017727  sub     rsp, 68h
0x18001772b  movdqa  [rsp+68h+var_48], xmm0
0x180017731  movdqa  [rsp+68h+var_38], xmm1
0x180017737  movdqa  [rsp+68h+var_28], xmm2
0x18001773d  movdqa  [rsp+68h+var_18], xmm3
0x180017743  mov     rdx, rax
0x180017746  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll
0x18001774d  call    __delayLoadHelper2
0x180017752  movdqa  xmm0, [rsp+68h+var_48]
0x180017758  movdqa  xmm1, [rsp+68h+var_38]
0x18001775e  movdqa  xmm2, [rsp+68h+var_28]
0x180017764  movdqa  xmm3, [rsp+68h+var_18]
0x18001776a  mov     rcx, [rsp+68h+arg_0]
0x18001776f  mov     rdx, [rsp+68h+arg_8]
0x180017774  mov     r8, [rsp+68h+arg_10]
0x18001777c  mov     r9, [rsp+68h+arg_18]
0x180017784  add     rsp, 68h
0x180017788  jmp     short $+2
0x18001778a  jmp     rax
```
