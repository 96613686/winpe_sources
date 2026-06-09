# __tailMerge_mpr_dll

- ea: `0x140010caa`
- end: `0x140010d23`
- name: `__tailMerge_mpr_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010d29`

## callees

- `0x1400083b0`
- `0x140010caa`

## pseudocode

```c
__int64 __fastcall _tailMerge_mpr_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_mpr_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140010caa  mov     [rsp+arg_0], rcx
0x140010caf  mov     [rsp+arg_8], rdx
0x140010cb4  mov     [rsp+arg_10], r8
0x140010cb9  mov     [rsp+arg_18], r9
0x140010cbe  sub     rsp, 68h
0x140010cc2  movdqa  [rsp+68h+var_48], xmm0
0x140010cc8  movdqa  [rsp+68h+var_38], xmm1
0x140010cce  movdqa  [rsp+68h+var_28], xmm2
0x140010cd4  movdqa  [rsp+68h+var_18], xmm3
0x140010cda  mov     rdx, rax
0x140010cdd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mpr_dll
0x140010ce4  call    __delayLoadHelper2
0x140010ce9  movdqa  xmm0, [rsp+68h+var_48]
0x140010cef  movdqa  xmm1, [rsp+68h+var_38]
0x140010cf5  movdqa  xmm2, [rsp+68h+var_28]
0x140010cfb  movdqa  xmm3, [rsp+68h+var_18]
0x140010d01  mov     rcx, [rsp+68h+arg_0]
0x140010d06  mov     rdx, [rsp+68h+arg_8]
0x140010d0b  mov     r8, [rsp+68h+arg_10]
0x140010d13  mov     r9, [rsp+68h+arg_18]
0x140010d1b  add     rsp, 68h
0x140010d1f  jmp     short $+2
0x140010d21  jmp     rax
```
