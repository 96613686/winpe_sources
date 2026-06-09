# __tailMerge_sspicli_dll

- ea: `0x18000ac95`
- end: `0x18000ad0e`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ad14`

## callees

- `0x180009170`
- `0x18000ac95`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ac95  mov     [rsp+arg_0], rcx
0x18000ac9a  mov     [rsp+arg_8], rdx
0x18000ac9f  mov     [rsp+arg_10], r8
0x18000aca4  mov     [rsp+arg_18], r9
0x18000aca9  sub     rsp, 68h
0x18000acad  movdqa  [rsp+68h+var_48], xmm0
0x18000acb3  movdqa  [rsp+68h+var_38], xmm1
0x18000acb9  movdqa  [rsp+68h+var_28], xmm2
0x18000acbf  movdqa  [rsp+68h+var_18], xmm3
0x18000acc5  mov     rdx, rax
0x18000acc8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000accf  call    __delayLoadHelper2
0x18000acd4  movdqa  xmm0, [rsp+68h+var_48]
0x18000acda  movdqa  xmm1, [rsp+68h+var_38]
0x18000ace0  movdqa  xmm2, [rsp+68h+var_28]
0x18000ace6  movdqa  xmm3, [rsp+68h+var_18]
0x18000acec  mov     rcx, [rsp+68h+arg_0]
0x18000acf1  mov     rdx, [rsp+68h+arg_8]
0x18000acf6  mov     r8, [rsp+68h+arg_10]
0x18000acfe  mov     r9, [rsp+68h+arg_18]
0x18000ad06  add     rsp, 68h
0x18000ad0a  jmp     short $+2
0x18000ad0c  jmp     rax
```
