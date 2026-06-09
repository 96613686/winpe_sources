# __tailMerge_wwapi_dll

- ea: `0x140003db0`
- end: `0x140003e29`
- name: `__tailMerge_wwapi_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003e2f`
- `0x140003e41`
- `0x140003e53`
- `0x140003e65`
- `0x140003e77`
- `0x140003e89`
- `0x140003e9b`
- `0x140003ead`

## callees

- `0x140003db0`
- `0x14003bc70`

## pseudocode

```c
__int64 __fastcall _tailMerge_wwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140003db0  mov     [rsp+arg_0], rcx
0x140003db5  mov     [rsp+arg_8], rdx
0x140003dba  mov     [rsp+arg_10], r8
0x140003dbf  mov     [rsp+arg_18], r9
0x140003dc4  sub     rsp, 68h
0x140003dc8  movdqa  [rsp+68h+var_48], xmm0
0x140003dce  movdqa  [rsp+68h+var_38], xmm1
0x140003dd4  movdqa  [rsp+68h+var_28], xmm2
0x140003dda  movdqa  [rsp+68h+var_18], xmm3
0x140003de0  mov     rdx, rax
0x140003de3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wwapi_dll
0x140003dea  call    __delayLoadHelper2
0x140003def  movdqa  xmm0, [rsp+68h+var_48]
0x140003df5  movdqa  xmm1, [rsp+68h+var_38]
0x140003dfb  movdqa  xmm2, [rsp+68h+var_28]
0x140003e01  movdqa  xmm3, [rsp+68h+var_18]
0x140003e07  mov     rcx, [rsp+68h+arg_0]
0x140003e0c  mov     rdx, [rsp+68h+arg_8]
0x140003e11  mov     r8, [rsp+68h+arg_10]
0x140003e19  mov     r9, [rsp+68h+arg_18]
0x140003e21  add     rsp, 68h
0x140003e25  jmp     short $+2
0x140003e27  jmp     rax
```
