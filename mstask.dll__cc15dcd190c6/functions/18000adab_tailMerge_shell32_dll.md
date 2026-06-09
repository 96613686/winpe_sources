# __tailMerge_shell32_dll

- ea: `0x18000adab`
- end: `0x18000ae24`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ae2a`
- `0x18000b557`

## callees

- `0x180009170`
- `0x18000adab`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000adab  mov     [rsp+arg_0], rcx
0x18000adb0  mov     [rsp+arg_8], rdx
0x18000adb5  mov     [rsp+arg_10], r8
0x18000adba  mov     [rsp+arg_18], r9
0x18000adbf  sub     rsp, 68h
0x18000adc3  movdqa  [rsp+68h+var_48], xmm0
0x18000adc9  movdqa  [rsp+68h+var_38], xmm1
0x18000adcf  movdqa  [rsp+68h+var_28], xmm2
0x18000add5  movdqa  [rsp+68h+var_18], xmm3
0x18000addb  mov     rdx, rax
0x18000adde  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x18000ade5  call    __delayLoadHelper2
0x18000adea  movdqa  xmm0, [rsp+68h+var_48]
0x18000adf0  movdqa  xmm1, [rsp+68h+var_38]
0x18000adf6  movdqa  xmm2, [rsp+68h+var_28]
0x18000adfc  movdqa  xmm3, [rsp+68h+var_18]
0x18000ae02  mov     rcx, [rsp+68h+arg_0]
0x18000ae07  mov     rdx, [rsp+68h+arg_8]
0x18000ae0c  mov     r8, [rsp+68h+arg_10]
0x18000ae14  mov     r9, [rsp+68h+arg_18]
0x18000ae1c  add     rsp, 68h
0x18000ae20  jmp     short $+2
0x18000ae22  jmp     rax
```
