# __tailMerge_appxalluserstore_dll

- ea: `0x140002c92`
- end: `0x140002d0b`
- name: `__tailMerge_appxalluserstore_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002d11`

## callees

- `0x140002c92`
- `0x14000fd50`

## pseudocode

```c
__int64 __fastcall _tailMerge_appxalluserstore_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_appxalluserstore_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002c92  mov     [rsp+arg_0], rcx
0x140002c97  mov     [rsp+arg_8], rdx
0x140002c9c  mov     [rsp+arg_10], r8
0x140002ca1  mov     [rsp+arg_18], r9
0x140002ca6  sub     rsp, 68h
0x140002caa  movdqa  [rsp+68h+var_48], xmm0
0x140002cb0  movdqa  [rsp+68h+var_38], xmm1
0x140002cb6  movdqa  [rsp+68h+var_28], xmm2
0x140002cbc  movdqa  [rsp+68h+var_18], xmm3
0x140002cc2  mov     rdx, rax
0x140002cc5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_appxalluserstore_dll
0x140002ccc  call    __delayLoadHelper2
0x140002cd1  movdqa  xmm0, [rsp+68h+var_48]
0x140002cd7  movdqa  xmm1, [rsp+68h+var_38]
0x140002cdd  movdqa  xmm2, [rsp+68h+var_28]
0x140002ce3  movdqa  xmm3, [rsp+68h+var_18]
0x140002ce9  mov     rcx, [rsp+68h+arg_0]
0x140002cee  mov     rdx, [rsp+68h+arg_8]
0x140002cf3  mov     r8, [rsp+68h+arg_10]
0x140002cfb  mov     r9, [rsp+68h+arg_18]
0x140002d03  add     rsp, 68h
0x140002d07  jmp     short $+2
0x140002d09  jmp     rax
```
