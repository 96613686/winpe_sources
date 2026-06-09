# __tailMerge_oleaut32_dll

- ea: `0x18000c259`
- end: `0x18000c2d2`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `32`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c2d8`
- `0x18000c2ea`
- `0x18000c387`
- `0x18000c399`
- `0x18000c3ab`
- `0x18000c3bd`
- `0x18000c3cf`
- `0x18000c3e1`
- `0x18000c3f3`
- `0x18000c405`
- `0x18000c417`
- `0x18000c429`
- `0x18000c43b`
- `0x18000c44d`
- `0x18000c45f`
- `0x18000c471`
- `0x18000c483`
- `0x18000c495`
- `0x18000c4a7`
- `0x18000c4b9`
- `0x18000c65c`
- `0x18000c67c`
- `0x18000c69c`
- `0x18000c6bc`
- `0x18000c6ec`
- `0x18000c72c`
- `0x18000c74c`
- `0x18000c76c`
- `0x18000caea`
- `0x18000cafc`
- `0x18000cb0e`
- `0x18000cb20`

## callees

- `0x1800086b0`
- `0x18000c259`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c259  mov     [rsp+arg_0], rcx
0x18000c25e  mov     [rsp+arg_8], rdx
0x18000c263  mov     [rsp+arg_10], r8
0x18000c268  mov     [rsp+arg_18], r9
0x18000c26d  sub     rsp, 68h
0x18000c271  movdqa  [rsp+68h+var_48], xmm0
0x18000c277  movdqa  [rsp+68h+var_38], xmm1
0x18000c27d  movdqa  [rsp+68h+var_28], xmm2
0x18000c283  movdqa  [rsp+68h+var_18], xmm3
0x18000c289  mov     rdx, rax
0x18000c28c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x18000c293  call    __delayLoadHelper2
0x18000c298  movdqa  xmm0, [rsp+68h+var_48]
0x18000c29e  movdqa  xmm1, [rsp+68h+var_38]
0x18000c2a4  movdqa  xmm2, [rsp+68h+var_28]
0x18000c2aa  movdqa  xmm3, [rsp+68h+var_18]
0x18000c2b0  mov     rcx, [rsp+68h+arg_0]
0x18000c2b5  mov     rdx, [rsp+68h+arg_8]
0x18000c2ba  mov     r8, [rsp+68h+arg_10]
0x18000c2c2  mov     r9, [rsp+68h+arg_18]
0x18000c2ca  add     rsp, 68h
0x18000c2ce  jmp     short $+2
0x18000c2d0  jmp     rax
```
