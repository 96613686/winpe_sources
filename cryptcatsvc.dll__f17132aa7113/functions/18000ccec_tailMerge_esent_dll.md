# __tailMerge_esent_dll

- ea: `0x18000ccec`
- end: `0x18000cd65`
- name: `__tailMerge_esent_dll`
- size: `121`
- prototype: ``
- caller_count: `34`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cd6b`
- `0x18000cd7d`
- `0x18000cd8f`
- `0x18000cda1`
- `0x18000cdb3`
- `0x18000cdc5`
- `0x18000cdd7`
- `0x18000cde9`
- `0x18000cdfb`
- `0x18000ce0d`
- `0x18000ce1f`
- `0x18000ce31`
- `0x18000ce43`
- `0x18000ce55`
- `0x18000ce67`
- `0x18000ce79`
- `0x18000ce8b`
- `0x18000ce9d`
- `0x18000ceaf`
- `0x18000cec1`
- `0x18000ced3`
- `0x18000cee5`
- `0x18000cef7`
- `0x18000cf09`
- `0x18000cf1b`
- `0x18000cf2d`
- `0x18000cf3f`
- `0x18000cf51`
- `0x18000cf63`
- `0x18000cf75`
- `0x18000cf87`
- `0x18000cf99`
- `0x18000cfab`
- `0x18000cfbd`

## callees

- `0x18000ccec`
- `0x1800213a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_esent_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_esent_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ccec  mov     [rsp+arg_0], rcx
0x18000ccf1  mov     [rsp+arg_8], rdx
0x18000ccf6  mov     [rsp+arg_10], r8
0x18000ccfb  mov     [rsp+arg_18], r9
0x18000cd00  sub     rsp, 68h
0x18000cd04  movdqa  [rsp+68h+var_48], xmm0
0x18000cd0a  movdqa  [rsp+68h+var_38], xmm1
0x18000cd10  movdqa  [rsp+68h+var_28], xmm2
0x18000cd16  movdqa  [rsp+68h+var_18], xmm3
0x18000cd1c  mov     rdx, rax
0x18000cd1f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_esent_dll
0x18000cd26  call    __delayLoadHelper2
0x18000cd2b  movdqa  xmm0, [rsp+68h+var_48]
0x18000cd31  movdqa  xmm1, [rsp+68h+var_38]
0x18000cd37  movdqa  xmm2, [rsp+68h+var_28]
0x18000cd3d  movdqa  xmm3, [rsp+68h+var_18]
0x18000cd43  mov     rcx, [rsp+68h+arg_0]
0x18000cd48  mov     rdx, [rsp+68h+arg_8]
0x18000cd4d  mov     r8, [rsp+68h+arg_10]
0x18000cd55  mov     r9, [rsp+68h+arg_18]
0x18000cd5d  add     rsp, 68h
0x18000cd61  jmp     short $+2
0x18000cd63  jmp     rax
```
