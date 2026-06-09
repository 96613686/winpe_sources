# __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll

- ea: `0x1800107c2`
- end: `0x18001083b`
- name: `__tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010841`

## callees

- `0x18000aac0`
- `0x1800107c2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_2_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_2_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800107c2  mov     [rsp+arg_0], rcx
0x1800107c7  mov     [rsp+arg_8], rdx
0x1800107cc  mov     [rsp+arg_10], r8
0x1800107d1  mov     [rsp+arg_18], r9
0x1800107d6  sub     rsp, 68h
0x1800107da  movdqa  [rsp+68h+var_48], xmm0
0x1800107e0  movdqa  [rsp+68h+var_38], xmm1
0x1800107e6  movdqa  [rsp+68h+var_28], xmm2
0x1800107ec  movdqa  [rsp+68h+var_18], xmm3
0x1800107f2  mov     rdx, rax
0x1800107f5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_appmodel_runtime_internal_l1_1_2_dll
0x1800107fc  call    __delayLoadHelper2
0x180010801  movdqa  xmm0, [rsp+68h+var_48]
0x180010807  movdqa  xmm1, [rsp+68h+var_38]
0x18001080d  movdqa  xmm2, [rsp+68h+var_28]
0x180010813  movdqa  xmm3, [rsp+68h+var_18]
0x180010819  mov     rcx, [rsp+68h+arg_0]
0x18001081e  mov     rdx, [rsp+68h+arg_8]
0x180010823  mov     r8, [rsp+68h+arg_10]
0x18001082b  mov     r9, [rsp+68h+arg_18]
0x180010833  add     rsp, 68h
0x180010837  jmp     short $+2
0x180010839  jmp     rax
```
