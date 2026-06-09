# __tailMerge_api_ms_win_shcore_unicodeansi_l1_1_0_dll

- ea: `0x18000406b`
- end: `0x1800040e4`
- name: `__tailMerge_api_ms_win_shcore_unicodeansi_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800040ea`
- `0x1800040fc`

## callees

- `0x1800036d0`
- `0x18000406b`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_shcore_unicodeansi_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_unicodeansi_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000406b  mov     [rsp+arg_0], rcx
0x180004070  mov     [rsp+arg_8], rdx
0x180004075  mov     [rsp+arg_10], r8
0x18000407a  mov     [rsp+arg_18], r9
0x18000407f  sub     rsp, 68h
0x180004083  movdqa  [rsp+68h+var_48], xmm0
0x180004089  movdqa  [rsp+68h+var_38], xmm1
0x18000408f  movdqa  [rsp+68h+var_28], xmm2
0x180004095  movdqa  [rsp+68h+var_18], xmm3
0x18000409b  mov     rdx, rax
0x18000409e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_shcore_unicodeansi_l1_1_0_dll
0x1800040a5  call    __delayLoadHelper2
0x1800040aa  movdqa  xmm0, [rsp+68h+var_48]
0x1800040b0  movdqa  xmm1, [rsp+68h+var_38]
0x1800040b6  movdqa  xmm2, [rsp+68h+var_28]
0x1800040bc  movdqa  xmm3, [rsp+68h+var_18]
0x1800040c2  mov     rcx, [rsp+68h+arg_0]
0x1800040c7  mov     rdx, [rsp+68h+arg_8]
0x1800040cc  mov     r8, [rsp+68h+arg_10]
0x1800040d4  mov     r9, [rsp+68h+arg_18]
0x1800040dc  add     rsp, 68h
0x1800040e0  jmp     short $+2
0x1800040e2  jmp     rax
```
