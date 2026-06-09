# __tailMerge_crypt32_dll

- ea: `0x18000aeec`
- end: `0x18000af65`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000af6b`
- `0x18000af7d`
- `0x18000af8f`
- `0x18000afa1`
- `0x18000afb3`
- `0x18000afc5`
- `0x18000afd7`
- `0x18000afe9`
- `0x18000affb`
- `0x18000b00d`
- `0x18000b01f`
- `0x18000b031`

## callees

- `0x1800079c0`
- `0x18000aeec`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000aeec  mov     [rsp+arg_0], rcx
0x18000aef1  mov     [rsp+arg_8], rdx
0x18000aef6  mov     [rsp+arg_10], r8
0x18000aefb  mov     [rsp+arg_18], r9
0x18000af00  sub     rsp, 68h
0x18000af04  movdqa  [rsp+68h+var_48], xmm0
0x18000af0a  movdqa  [rsp+68h+var_38], xmm1
0x18000af10  movdqa  [rsp+68h+var_28], xmm2
0x18000af16  movdqa  [rsp+68h+var_18], xmm3
0x18000af1c  mov     rdx, rax
0x18000af1f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x18000af26  call    __delayLoadHelper2
0x18000af2b  movdqa  xmm0, [rsp+68h+var_48]
0x18000af31  movdqa  xmm1, [rsp+68h+var_38]
0x18000af37  movdqa  xmm2, [rsp+68h+var_28]
0x18000af3d  movdqa  xmm3, [rsp+68h+var_18]
0x18000af43  mov     rcx, [rsp+68h+arg_0]
0x18000af48  mov     rdx, [rsp+68h+arg_8]
0x18000af4d  mov     r8, [rsp+68h+arg_10]
0x18000af55  mov     r9, [rsp+68h+arg_18]
0x18000af5d  add     rsp, 68h
0x18000af61  jmp     short $+2
0x18000af63  jmp     rax
```
