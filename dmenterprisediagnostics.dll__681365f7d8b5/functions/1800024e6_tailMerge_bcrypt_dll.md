# __tailMerge_bcrypt_dll

- ea: `0x1800024e6`
- end: `0x18000255f`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002565`
- `0x180002577`
- `0x180002589`
- `0x18000259b`
- `0x1800025ad`
- `0x1800025bf`
- `0x1800025d1`

## callees

- `0x1800024e6`
- `0x180024b90`

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
0x1800024e6  mov     [rsp+arg_0], rcx
0x1800024eb  mov     [rsp+arg_8], rdx
0x1800024f0  mov     [rsp+arg_10], r8
0x1800024f5  mov     [rsp+arg_18], r9
0x1800024fa  sub     rsp, 68h
0x1800024fe  movdqa  [rsp+68h+var_48], xmm0
0x180002504  movdqa  [rsp+68h+var_38], xmm1
0x18000250a  movdqa  [rsp+68h+var_28], xmm2
0x180002510  movdqa  [rsp+68h+var_18], xmm3
0x180002516  mov     rdx, rax
0x180002519  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180002520  call    __delayLoadHelper2
0x180002525  movdqa  xmm0, [rsp+68h+var_48]
0x18000252b  movdqa  xmm1, [rsp+68h+var_38]
0x180002531  movdqa  xmm2, [rsp+68h+var_28]
0x180002537  movdqa  xmm3, [rsp+68h+var_18]
0x18000253d  mov     rcx, [rsp+68h+arg_0]
0x180002542  mov     rdx, [rsp+68h+arg_8]
0x180002547  mov     r8, [rsp+68h+arg_10]
0x18000254f  mov     r9, [rsp+68h+arg_18]
0x180002557  add     rsp, 68h
0x18000255b  jmp     short $+2
0x18000255d  jmp     rax
```
