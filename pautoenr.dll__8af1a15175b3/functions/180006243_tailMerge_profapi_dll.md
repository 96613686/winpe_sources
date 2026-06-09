# __tailMerge_profapi_dll

- ea: `0x180006243`
- end: `0x1800062bc`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800062c2`

## callees

- `0x1800046b0`
- `0x180006243`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006243  mov     [rsp+arg_0], rcx
0x180006248  mov     [rsp+arg_8], rdx
0x18000624d  mov     [rsp+arg_10], r8
0x180006252  mov     [rsp+arg_18], r9
0x180006257  sub     rsp, 68h
0x18000625b  movdqa  [rsp+68h+var_48], xmm0
0x180006261  movdqa  [rsp+68h+var_38], xmm1
0x180006267  movdqa  [rsp+68h+var_28], xmm2
0x18000626d  movdqa  [rsp+68h+var_18], xmm3
0x180006273  mov     rdx, rax
0x180006276  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x18000627d  call    __delayLoadHelper2
0x180006282  movdqa  xmm0, [rsp+68h+var_48]
0x180006288  movdqa  xmm1, [rsp+68h+var_38]
0x18000628e  movdqa  xmm2, [rsp+68h+var_28]
0x180006294  movdqa  xmm3, [rsp+68h+var_18]
0x18000629a  mov     rcx, [rsp+68h+arg_0]
0x18000629f  mov     rdx, [rsp+68h+arg_8]
0x1800062a4  mov     r8, [rsp+68h+arg_10]
0x1800062ac  mov     r9, [rsp+68h+arg_18]
0x1800062b4  add     rsp, 68h
0x1800062b8  jmp     short $+2
0x1800062ba  jmp     rax
```
