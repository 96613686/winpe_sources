# __tailMerge_bcrypt_dll

- ea: `0x18001a4e6`
- end: `0x18001a55f`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a565`
- `0x18001a577`
- `0x18001a589`
- `0x18001a59b`
- `0x18001a5ad`
- `0x18001a5bf`
- `0x18001a5d1`
- `0x18001a5e3`
- `0x18001a5f5`
- `0x18001a607`
- `0x18001a820`
- `0x18001a832`
- `0x18001a844`
- `0x18001a856`
- `0x18001a868`
- `0x18001a87a`
- `0x18001a88c`
- `0x18001a89e`

## callees

- `0x180015c10`
- `0x18001a4e6`

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
0x18001a4e6  mov     [rsp+arg_0], rcx
0x18001a4eb  mov     [rsp+arg_8], rdx
0x18001a4f0  mov     [rsp+arg_10], r8
0x18001a4f5  mov     [rsp+arg_18], r9
0x18001a4fa  sub     rsp, 68h
0x18001a4fe  movdqa  [rsp+68h+var_48], xmm0
0x18001a504  movdqa  [rsp+68h+var_38], xmm1
0x18001a50a  movdqa  [rsp+68h+var_28], xmm2
0x18001a510  movdqa  [rsp+68h+var_18], xmm3
0x18001a516  mov     rdx, rax
0x18001a519  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18001a520  call    __delayLoadHelper2
0x18001a525  movdqa  xmm0, [rsp+68h+var_48]
0x18001a52b  movdqa  xmm1, [rsp+68h+var_38]
0x18001a531  movdqa  xmm2, [rsp+68h+var_28]
0x18001a537  movdqa  xmm3, [rsp+68h+var_18]
0x18001a53d  mov     rcx, [rsp+68h+arg_0]
0x18001a542  mov     rdx, [rsp+68h+arg_8]
0x18001a547  mov     r8, [rsp+68h+arg_10]
0x18001a54f  mov     r9, [rsp+68h+arg_18]
0x18001a557  add     rsp, 68h
0x18001a55b  jmp     short $+2
0x18001a55d  jmp     rax
```
