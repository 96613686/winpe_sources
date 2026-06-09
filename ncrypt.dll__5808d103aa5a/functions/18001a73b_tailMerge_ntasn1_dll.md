# __tailMerge_ntasn1_dll

- ea: `0x18001a73b`
- end: `0x18001a7b4`
- name: `__tailMerge_ntasn1_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a7ba`
- `0x18001a7cc`
- `0x18001a7de`
- `0x18001a7f0`
- `0x18001a802`
- `0x18001a8b0`

## callees

- `0x180015c10`
- `0x18001a73b`

## pseudocode

```c
__int64 __fastcall _tailMerge_ntasn1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ntasn1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a73b  mov     [rsp+arg_0], rcx
0x18001a740  mov     [rsp+arg_8], rdx
0x18001a745  mov     [rsp+arg_10], r8
0x18001a74a  mov     [rsp+arg_18], r9
0x18001a74f  sub     rsp, 68h
0x18001a753  movdqa  [rsp+68h+var_48], xmm0
0x18001a759  movdqa  [rsp+68h+var_38], xmm1
0x18001a75f  movdqa  [rsp+68h+var_28], xmm2
0x18001a765  movdqa  [rsp+68h+var_18], xmm3
0x18001a76b  mov     rdx, rax
0x18001a76e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ntasn1_dll
0x18001a775  call    __delayLoadHelper2
0x18001a77a  movdqa  xmm0, [rsp+68h+var_48]
0x18001a780  movdqa  xmm1, [rsp+68h+var_38]
0x18001a786  movdqa  xmm2, [rsp+68h+var_28]
0x18001a78c  movdqa  xmm3, [rsp+68h+var_18]
0x18001a792  mov     rcx, [rsp+68h+arg_0]
0x18001a797  mov     rdx, [rsp+68h+arg_8]
0x18001a79c  mov     r8, [rsp+68h+arg_10]
0x18001a7a4  mov     r9, [rsp+68h+arg_18]
0x18001a7ac  add     rsp, 68h
0x18001a7b0  jmp     short $+2
0x18001a7b2  jmp     rax
```
