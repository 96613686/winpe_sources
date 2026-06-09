# __tailMerge_sspisrv_dll

- ea: `0x140002a26`
- end: `0x140002a9f`
- name: `__tailMerge_sspisrv_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002aa5`
- `0x140002ab7`
- `0x140002ac9`
- `0x140002adb`
- `0x140002aed`

## callees

- `0x140002a26`
- `0x1400051c0`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspisrv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_sspisrv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002a26  mov     [rsp+arg_0], rcx
0x140002a2b  mov     [rsp+arg_8], rdx
0x140002a30  mov     [rsp+arg_10], r8
0x140002a35  mov     [rsp+arg_18], r9
0x140002a3a  sub     rsp, 68h
0x140002a3e  movdqa  [rsp+68h+var_48], xmm0
0x140002a44  movdqa  [rsp+68h+var_38], xmm1
0x140002a4a  movdqa  [rsp+68h+var_28], xmm2
0x140002a50  movdqa  [rsp+68h+var_18], xmm3
0x140002a56  mov     rdx, rax
0x140002a59  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspisrv_dll
0x140002a60  call    __delayLoadHelper2
0x140002a65  movdqa  xmm0, [rsp+68h+var_48]
0x140002a6b  movdqa  xmm1, [rsp+68h+var_38]
0x140002a71  movdqa  xmm2, [rsp+68h+var_28]
0x140002a77  movdqa  xmm3, [rsp+68h+var_18]
0x140002a7d  mov     rcx, [rsp+68h+arg_0]
0x140002a82  mov     rdx, [rsp+68h+arg_8]
0x140002a87  mov     r8, [rsp+68h+arg_10]
0x140002a8f  mov     r9, [rsp+68h+arg_18]
0x140002a97  add     rsp, 68h
0x140002a9b  jmp     short $+2
0x140002a9d  jmp     rax
```
