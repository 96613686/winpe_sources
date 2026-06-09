# __tailMerge_bcrypt_dll

- ea: `0x180002330`
- end: `0x1800023a9`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800023af`
- `0x1800023c1`
- `0x1800023d3`
- `0x1800023e5`
- `0x1800023f7`
- `0x180002409`
- `0x18000241b`

## callees

- `0x180002330`
- `0x18001cd30`

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
0x180002330  mov     [rsp+arg_0], rcx
0x180002335  mov     [rsp+arg_8], rdx
0x18000233a  mov     [rsp+arg_10], r8
0x18000233f  mov     [rsp+arg_18], r9
0x180002344  sub     rsp, 68h
0x180002348  movdqa  [rsp+68h+var_48], xmm0
0x18000234e  movdqa  [rsp+68h+var_38], xmm1
0x180002354  movdqa  [rsp+68h+var_28], xmm2
0x18000235a  movdqa  [rsp+68h+var_18], xmm3
0x180002360  mov     rdx, rax
0x180002363  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18000236a  call    __delayLoadHelper2
0x18000236f  movdqa  xmm0, [rsp+68h+var_48]
0x180002375  movdqa  xmm1, [rsp+68h+var_38]
0x18000237b  movdqa  xmm2, [rsp+68h+var_28]
0x180002381  movdqa  xmm3, [rsp+68h+var_18]
0x180002387  mov     rcx, [rsp+68h+arg_0]
0x18000238c  mov     rdx, [rsp+68h+arg_8]
0x180002391  mov     r8, [rsp+68h+arg_10]
0x180002399  mov     r9, [rsp+68h+arg_18]
0x1800023a1  add     rsp, 68h
0x1800023a5  jmp     short $+2
0x1800023a7  jmp     rax
```
