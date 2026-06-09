# __tailMerge_shlwapi_dll

- ea: `0x140010bad`
- end: `0x140010c26`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010c2c`
- `0x140010c3e`
- `0x140010c50`
- `0x140010c62`
- `0x140010c74`
- `0x140010c86`

## callees

- `0x1400083b0`
- `0x140010bad`

## pseudocode

```c
__int64 __fastcall _tailMerge_shlwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_shlwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010bad  mov     [rsp+arg_0], rcx
0x140010bb2  mov     [rsp+arg_8], rdx
0x140010bb7  mov     [rsp+arg_10], r8
0x140010bbc  mov     [rsp+arg_18], r9
0x140010bc1  sub     rsp, 68h
0x140010bc5  movdqa  [rsp+68h+var_48], xmm0
0x140010bcb  movdqa  [rsp+68h+var_38], xmm1
0x140010bd1  movdqa  [rsp+68h+var_28], xmm2
0x140010bd7  movdqa  [rsp+68h+var_18], xmm3
0x140010bdd  mov     rdx, rax
0x140010be0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x140010be7  call    __delayLoadHelper2
0x140010bec  movdqa  xmm0, [rsp+68h+var_48]
0x140010bf2  movdqa  xmm1, [rsp+68h+var_38]
0x140010bf8  movdqa  xmm2, [rsp+68h+var_28]
0x140010bfe  movdqa  xmm3, [rsp+68h+var_18]
0x140010c04  mov     rcx, [rsp+68h+arg_0]
0x140010c09  mov     rdx, [rsp+68h+arg_8]
0x140010c0e  mov     r8, [rsp+68h+arg_10]
0x140010c16  mov     r9, [rsp+68h+arg_18]
0x140010c1e  add     rsp, 68h
0x140010c22  jmp     short $+2
0x140010c24  jmp     rax
```
