# __tailMerge_oleaut32_dll

- ea: `0x18000ac72`
- end: `0x18000aceb`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000acf1`
- `0x18000aeda`
- `0x18000aeec`
- `0x18000af34`

## callees

- `0x180001530`
- `0x18000ac72`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ac72  mov     [rsp+arg_0], rcx
0x18000ac77  mov     [rsp+arg_8], rdx
0x18000ac7c  mov     [rsp+arg_10], r8
0x18000ac81  mov     [rsp+arg_18], r9
0x18000ac86  sub     rsp, 68h
0x18000ac8a  movdqa  [rsp+68h+var_48], xmm0
0x18000ac90  movdqa  [rsp+68h+var_38], xmm1
0x18000ac96  movdqa  [rsp+68h+var_28], xmm2
0x18000ac9c  movdqa  [rsp+68h+var_18], xmm3
0x18000aca2  mov     rdx, rax
0x18000aca5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000acac  call    __delayLoadHelper2
0x18000acb1  movdqa  xmm0, [rsp+68h+var_48]
0x18000acb7  movdqa  xmm1, [rsp+68h+var_38]
0x18000acbd  movdqa  xmm2, [rsp+68h+var_28]
0x18000acc3  movdqa  xmm3, [rsp+68h+var_18]
0x18000acc9  mov     rcx, [rsp+68h+arg_0]
0x18000acce  mov     rdx, [rsp+68h+arg_8]
0x18000acd3  mov     r8, [rsp+68h+arg_10]
0x18000acdb  mov     r9, [rsp+68h+arg_18]
0x18000ace3  add     rsp, 68h
0x18000ace7  jmp     short $+2
0x18000ace9  jmp     rax
```
