# __tailMerge_bcrypt_dll

- ea: `0x1800054c4`
- end: `0x18000553d`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005543`
- `0x180005555`
- `0x180005567`
- `0x180005579`
- `0x18000558b`
- `0x18000559d`
- `0x1800055af`
- `0x1800055c1`
- `0x1800055d3`
- `0x1800055e5`
- `0x1800055f7`
- `0x180005609`
- `0x18000561b`
- `0x18000562d`

## callees

- `0x180003c60`
- `0x1800054c4`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800054c4  mov     [rsp+arg_0], rcx
0x1800054c9  mov     [rsp+arg_8], rdx
0x1800054ce  mov     [rsp+arg_10], r8
0x1800054d3  mov     [rsp+arg_18], r9
0x1800054d8  sub     rsp, 68h
0x1800054dc  movdqa  [rsp+68h+var_48], xmm0
0x1800054e2  movdqa  [rsp+68h+var_38], xmm1
0x1800054e8  movdqa  [rsp+68h+var_28], xmm2
0x1800054ee  movdqa  [rsp+68h+var_18], xmm3
0x1800054f4  mov     rdx, rax
0x1800054f7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800054fe  call    __delayLoadHelper2
0x180005503  movdqa  xmm0, [rsp+68h+var_48]
0x180005509  movdqa  xmm1, [rsp+68h+var_38]
0x18000550f  movdqa  xmm2, [rsp+68h+var_28]
0x180005515  movdqa  xmm3, [rsp+68h+var_18]
0x18000551b  mov     rcx, [rsp+68h+arg_0]
0x180005520  mov     rdx, [rsp+68h+arg_8]
0x180005525  mov     r8, [rsp+68h+arg_10]
0x18000552d  mov     r9, [rsp+68h+arg_18]
0x180005535  add     rsp, 68h
0x180005539  jmp     short $+2
0x18000553b  jmp     rax
```
