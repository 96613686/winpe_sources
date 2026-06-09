# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x18000529d`
- end: `0x180005316`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000531c`
- `0x18000532e`
- `0x180005340`
- `0x180005352`

## callees

- `0x1800030d0`
- `0x18000529d`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000529d  mov     [rsp+arg_0], rcx
0x1800052a2  mov     [rsp+arg_8], rdx
0x1800052a7  mov     [rsp+arg_10], r8
0x1800052ac  mov     [rsp+arg_18], r9
0x1800052b1  sub     rsp, 68h
0x1800052b5  movdqa  [rsp+68h+var_48], xmm0
0x1800052bb  movdqa  [rsp+68h+var_38], xmm1
0x1800052c1  movdqa  [rsp+68h+var_28], xmm2
0x1800052c7  movdqa  [rsp+68h+var_18], xmm3
0x1800052cd  mov     rdx, rax
0x1800052d0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x1800052d7  call    __delayLoadHelper2
0x1800052dc  movdqa  xmm0, [rsp+68h+var_48]
0x1800052e2  movdqa  xmm1, [rsp+68h+var_38]
0x1800052e8  movdqa  xmm2, [rsp+68h+var_28]
0x1800052ee  movdqa  xmm3, [rsp+68h+var_18]
0x1800052f4  mov     rcx, [rsp+68h+arg_0]
0x1800052f9  mov     rdx, [rsp+68h+arg_8]
0x1800052fe  mov     r8, [rsp+68h+arg_10]
0x180005306  mov     r9, [rsp+68h+arg_18]
0x18000530e  add     rsp, 68h
0x180005312  jmp     short $+2
0x180005314  jmp     rax
```
