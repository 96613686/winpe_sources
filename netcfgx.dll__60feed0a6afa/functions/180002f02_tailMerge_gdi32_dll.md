# __tailMerge_gdi32_dll

- ea: `0x180002f02`
- end: `0x180002f7b`
- name: `__tailMerge_gdi32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f81`
- `0x180002f93`
- `0x180002fa5`
- `0x180002fb7`
- `0x180002fc9`

## callees

- `0x180002f02`
- `0x180011dd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_gdi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_gdi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002f02  mov     [rsp+arg_0], rcx
0x180002f07  mov     [rsp+arg_8], rdx
0x180002f0c  mov     [rsp+arg_10], r8
0x180002f11  mov     [rsp+arg_18], r9
0x180002f16  sub     rsp, 68h
0x180002f1a  movdqa  [rsp+68h+var_48], xmm0
0x180002f20  movdqa  [rsp+68h+var_38], xmm1
0x180002f26  movdqa  [rsp+68h+var_28], xmm2
0x180002f2c  movdqa  [rsp+68h+var_18], xmm3
0x180002f32  mov     rdx, rax
0x180002f35  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_gdi32_dll
0x180002f3c  call    __delayLoadHelper2
0x180002f41  movdqa  xmm0, [rsp+68h+var_48]
0x180002f47  movdqa  xmm1, [rsp+68h+var_38]
0x180002f4d  movdqa  xmm2, [rsp+68h+var_28]
0x180002f53  movdqa  xmm3, [rsp+68h+var_18]
0x180002f59  mov     rcx, [rsp+68h+arg_0]
0x180002f5e  mov     rdx, [rsp+68h+arg_8]
0x180002f63  mov     r8, [rsp+68h+arg_10]
0x180002f6b  mov     r9, [rsp+68h+arg_18]
0x180002f73  add     rsp, 68h
0x180002f77  jmp     short $+2
0x180002f79  jmp     rax
```
