# __tailMerge_user32_dll

- ea: `0x18000ae36`
- end: `0x18000aeaf`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aeb5`
- `0x18000aec7`
- `0x18000afef`
- `0x18000b001`
- `0x18000b013`
- `0x18000b025`
- `0x18000b037`
- `0x18000b049`
- `0x18000b06d`
- `0x18000b07f`
- `0x18000b0a3`
- `0x18000b0b5`
- `0x18000b0c7`
- `0x18000b0d9`
- `0x18000b0eb`
- `0x18000b0fd`
- `0x18000b10f`
- `0x18000b121`
- `0x18000b133`
- `0x18000b157`
- `0x18000b169`
- `0x18000b17b`
- `0x18000b18d`
- `0x18000b19f`
- `0x18000b1b1`
- `0x18000b1c3`
- `0x18000b260`
- `0x18000b272`
- `0x18000b284`
- `0x18000b296`
- `0x18000b2a8`
- `0x18000b2ba`
- `0x18000b2cc`
- `0x18000b2de`
- `0x18000b4d9`
- `0x18000b4eb`

## callees

- `0x180009170`
- `0x18000ae36`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ae36  mov     [rsp+arg_0], rcx
0x18000ae3b  mov     [rsp+arg_8], rdx
0x18000ae40  mov     [rsp+arg_10], r8
0x18000ae45  mov     [rsp+arg_18], r9
0x18000ae4a  sub     rsp, 68h
0x18000ae4e  movdqa  [rsp+68h+var_48], xmm0
0x18000ae54  movdqa  [rsp+68h+var_38], xmm1
0x18000ae5a  movdqa  [rsp+68h+var_28], xmm2
0x18000ae60  movdqa  [rsp+68h+var_18], xmm3
0x18000ae66  mov     rdx, rax
0x18000ae69  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x18000ae70  call    __delayLoadHelper2
0x18000ae75  movdqa  xmm0, [rsp+68h+var_48]
0x18000ae7b  movdqa  xmm1, [rsp+68h+var_38]
0x18000ae81  movdqa  xmm2, [rsp+68h+var_28]
0x18000ae87  movdqa  xmm3, [rsp+68h+var_18]
0x18000ae8d  mov     rcx, [rsp+68h+arg_0]
0x18000ae92  mov     rdx, [rsp+68h+arg_8]
0x18000ae97  mov     r8, [rsp+68h+arg_10]
0x18000ae9f  mov     r9, [rsp+68h+arg_18]
0x18000aea7  add     rsp, 68h
0x18000aeab  jmp     short $+2
0x18000aead  jmp     rax
```
