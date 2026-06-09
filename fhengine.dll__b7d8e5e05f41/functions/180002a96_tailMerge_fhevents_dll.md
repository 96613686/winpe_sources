# __tailMerge_fhevents_dll

- ea: `0x180002a96`
- end: `0x180002b0f`
- name: `__tailMerge_fhevents_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b15`
- `0x180002b27`
- `0x180002b39`

## callees

- `0x180002a96`
- `0x180031550`

## pseudocode

```c
__int64 __fastcall _tailMerge_fhevents_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_fhevents_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002a96  mov     [rsp+arg_0], rcx
0x180002a9b  mov     [rsp+arg_8], rdx
0x180002aa0  mov     [rsp+arg_10], r8
0x180002aa5  mov     [rsp+arg_18], r9
0x180002aaa  sub     rsp, 68h
0x180002aae  movdqa  [rsp+68h+var_48], xmm0
0x180002ab4  movdqa  [rsp+68h+var_38], xmm1
0x180002aba  movdqa  [rsp+68h+var_28], xmm2
0x180002ac0  movdqa  [rsp+68h+var_18], xmm3
0x180002ac6  mov     rdx, rax
0x180002ac9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_fhevents_dll
0x180002ad0  call    __delayLoadHelper2
0x180002ad5  movdqa  xmm0, [rsp+68h+var_48]
0x180002adb  movdqa  xmm1, [rsp+68h+var_38]
0x180002ae1  movdqa  xmm2, [rsp+68h+var_28]
0x180002ae7  movdqa  xmm3, [rsp+68h+var_18]
0x180002aed  mov     rcx, [rsp+68h+arg_0]
0x180002af2  mov     rdx, [rsp+68h+arg_8]
0x180002af7  mov     r8, [rsp+68h+arg_10]
0x180002aff  mov     r9, [rsp+68h+arg_18]
0x180002b07  add     rsp, 68h
0x180002b0b  jmp     short $+2
0x180002b0d  jmp     rax
```
