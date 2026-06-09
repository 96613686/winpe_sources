# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180020b8d`
- end: `0x180020c06`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020c0c`

## callees

- `0x180018b30`
- `0x180020b8d`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180020b8d  mov     [rsp+arg_0], rcx
0x180020b92  mov     [rsp+arg_8], rdx
0x180020b97  mov     [rsp+arg_10], r8
0x180020b9c  mov     [rsp+arg_18], r9
0x180020ba1  sub     rsp, 68h
0x180020ba5  movdqa  [rsp+68h+var_48], xmm0
0x180020bab  movdqa  [rsp+68h+var_38], xmm1
0x180020bb1  movdqa  [rsp+68h+var_28], xmm2
0x180020bb7  movdqa  [rsp+68h+var_18], xmm3
0x180020bbd  mov     rdx, rax
0x180020bc0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x180020bc7  call    __delayLoadHelper2
0x180020bcc  movdqa  xmm0, [rsp+68h+var_48]
0x180020bd2  movdqa  xmm1, [rsp+68h+var_38]
0x180020bd8  movdqa  xmm2, [rsp+68h+var_28]
0x180020bde  movdqa  xmm3, [rsp+68h+var_18]
0x180020be4  mov     rcx, [rsp+68h+arg_0]
0x180020be9  mov     rdx, [rsp+68h+arg_8]
0x180020bee  mov     r8, [rsp+68h+arg_10]
0x180020bf6  mov     r9, [rsp+68h+arg_18]
0x180020bfe  add     rsp, 68h
0x180020c02  jmp     short $+2
0x180020c04  jmp     rax
```
