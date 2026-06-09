# __tailMerge_iphlpapi_dll

- ea: `0x18001a4f9`
- end: `0x18001a572`
- name: `__tailMerge_iphlpapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a578`
- `0x18001a58a`
- `0x18001a59c`
- `0x18001aab1`
- `0x18001aac3`

## callees

- `0x18000f880`
- `0x18001a4f9`

## pseudocode

```c
__int64 __fastcall _tailMerge_iphlpapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a4f9  mov     [rsp+arg_0], rcx
0x18001a4fe  mov     [rsp+arg_8], rdx
0x18001a503  mov     [rsp+arg_10], r8
0x18001a508  mov     [rsp+arg_18], r9
0x18001a50d  sub     rsp, 68h
0x18001a511  movdqa  [rsp+68h+var_48], xmm0
0x18001a517  movdqa  [rsp+68h+var_38], xmm1
0x18001a51d  movdqa  [rsp+68h+var_28], xmm2
0x18001a523  movdqa  [rsp+68h+var_18], xmm3
0x18001a529  mov     rdx, rax
0x18001a52c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iphlpapi_dll
0x18001a533  call    __delayLoadHelper2
0x18001a538  movdqa  xmm0, [rsp+68h+var_48]
0x18001a53e  movdqa  xmm1, [rsp+68h+var_38]
0x18001a544  movdqa  xmm2, [rsp+68h+var_28]
0x18001a54a  movdqa  xmm3, [rsp+68h+var_18]
0x18001a550  mov     rcx, [rsp+68h+arg_0]
0x18001a555  mov     rdx, [rsp+68h+arg_8]
0x18001a55a  mov     r8, [rsp+68h+arg_10]
0x18001a562  mov     r9, [rsp+68h+arg_18]
0x18001a56a  add     rsp, 68h
0x18001a56e  jmp     short $+2
0x18001a570  jmp     rax
```
