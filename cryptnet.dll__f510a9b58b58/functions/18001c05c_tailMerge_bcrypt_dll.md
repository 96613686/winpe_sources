# __tailMerge_bcrypt_dll

- ea: `0x18001c05c`
- end: `0x18001c0d5`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c0db`
- `0x18001c0ed`
- `0x18001c0ff`
- `0x18001c111`

## callees

- `0x1800187e0`
- `0x18001c05c`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c05c  mov     [rsp+arg_0], rcx
0x18001c061  mov     [rsp+arg_8], rdx
0x18001c066  mov     [rsp+arg_10], r8
0x18001c06b  mov     [rsp+arg_18], r9
0x18001c070  sub     rsp, 68h
0x18001c074  movdqa  [rsp+68h+var_48], xmm0
0x18001c07a  movdqa  [rsp+68h+var_38], xmm1
0x18001c080  movdqa  [rsp+68h+var_28], xmm2
0x18001c086  movdqa  [rsp+68h+var_18], xmm3
0x18001c08c  mov     rdx, rax
0x18001c08f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18001c096  call    __delayLoadHelper2
0x18001c09b  movdqa  xmm0, [rsp+68h+var_48]
0x18001c0a1  movdqa  xmm1, [rsp+68h+var_38]
0x18001c0a7  movdqa  xmm2, [rsp+68h+var_28]
0x18001c0ad  movdqa  xmm3, [rsp+68h+var_18]
0x18001c0b3  mov     rcx, [rsp+68h+arg_0]
0x18001c0b8  mov     rdx, [rsp+68h+arg_8]
0x18001c0bd  mov     r8, [rsp+68h+arg_10]
0x18001c0c5  mov     r9, [rsp+68h+arg_18]
0x18001c0cd  add     rsp, 68h
0x18001c0d1  jmp     short $+2
0x18001c0d3  jmp     rax
```
