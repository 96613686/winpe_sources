# __tailMerge_bcrypt_dll

- ea: `0x1800024c6`
- end: `0x18000253f`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002545`
- `0x180002557`
- `0x180002569`
- `0x18000257b`
- `0x18000258d`
- `0x18000259f`
- `0x1800025b1`

## callees

- `0x1800024c6`
- `0x180023d10`

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
0x1800024c6  mov     [rsp+arg_0], rcx
0x1800024cb  mov     [rsp+arg_8], rdx
0x1800024d0  mov     [rsp+arg_10], r8
0x1800024d5  mov     [rsp+arg_18], r9
0x1800024da  sub     rsp, 68h
0x1800024de  movdqa  [rsp+68h+var_48], xmm0
0x1800024e4  movdqa  [rsp+68h+var_38], xmm1
0x1800024ea  movdqa  [rsp+68h+var_28], xmm2
0x1800024f0  movdqa  [rsp+68h+var_18], xmm3
0x1800024f6  mov     rdx, rax
0x1800024f9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x180002500  call    __delayLoadHelper2
0x180002505  movdqa  xmm0, [rsp+68h+var_48]
0x18000250b  movdqa  xmm1, [rsp+68h+var_38]
0x180002511  movdqa  xmm2, [rsp+68h+var_28]
0x180002517  movdqa  xmm3, [rsp+68h+var_18]
0x18000251d  mov     rcx, [rsp+68h+arg_0]
0x180002522  mov     rdx, [rsp+68h+arg_8]
0x180002527  mov     r8, [rsp+68h+arg_10]
0x18000252f  mov     r9, [rsp+68h+arg_18]
0x180002537  add     rsp, 68h
0x18000253b  jmp     short $+2
0x18000253d  jmp     rax
```
