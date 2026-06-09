# __tailMerge_winhttp_dll

- ea: `0x18001c2fe`
- end: `0x18001c377`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c37d`
- `0x18001c38f`
- `0x18001c3a1`
- `0x18001c3b3`
- `0x18001c3c5`
- `0x18001c3d7`
- `0x18001c3e9`
- `0x18001c3fb`
- `0x18001c40d`
- `0x18001c41f`
- `0x18001c431`
- `0x18001c443`
- `0x18001c455`

## callees

- `0x1800187e0`
- `0x18001c2fe`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c2fe  mov     [rsp+arg_0], rcx
0x18001c303  mov     [rsp+arg_8], rdx
0x18001c308  mov     [rsp+arg_10], r8
0x18001c30d  mov     [rsp+arg_18], r9
0x18001c312  sub     rsp, 68h
0x18001c316  movdqa  [rsp+68h+var_48], xmm0
0x18001c31c  movdqa  [rsp+68h+var_38], xmm1
0x18001c322  movdqa  [rsp+68h+var_28], xmm2
0x18001c328  movdqa  [rsp+68h+var_18], xmm3
0x18001c32e  mov     rdx, rax
0x18001c331  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x18001c338  call    __delayLoadHelper2
0x18001c33d  movdqa  xmm0, [rsp+68h+var_48]
0x18001c343  movdqa  xmm1, [rsp+68h+var_38]
0x18001c349  movdqa  xmm2, [rsp+68h+var_28]
0x18001c34f  movdqa  xmm3, [rsp+68h+var_18]
0x18001c355  mov     rcx, [rsp+68h+arg_0]
0x18001c35a  mov     rdx, [rsp+68h+arg_8]
0x18001c35f  mov     r8, [rsp+68h+arg_10]
0x18001c367  mov     r9, [rsp+68h+arg_18]
0x18001c36f  add     rsp, 68h
0x18001c373  jmp     short $+2
0x18001c375  jmp     rax
```
