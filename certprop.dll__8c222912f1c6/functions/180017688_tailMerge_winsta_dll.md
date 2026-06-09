# __tailMerge_winsta_dll

- ea: `0x180017688`
- end: `0x180017701`
- name: `__tailMerge_winsta_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017707`

## callees

- `0x18000e1a0`
- `0x180017688`

## pseudocode

```c
__int64 __fastcall _tailMerge_winsta_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_winsta_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017688  mov     [rsp+arg_0], rcx
0x18001768d  mov     [rsp+arg_8], rdx
0x180017692  mov     [rsp+arg_10], r8
0x180017697  mov     [rsp+arg_18], r9
0x18001769c  sub     rsp, 68h
0x1800176a0  movdqa  [rsp+68h+var_48], xmm0
0x1800176a6  movdqa  [rsp+68h+var_38], xmm1
0x1800176ac  movdqa  [rsp+68h+var_28], xmm2
0x1800176b2  movdqa  [rsp+68h+var_18], xmm3
0x1800176b8  mov     rdx, rax
0x1800176bb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winsta_dll
0x1800176c2  call    __delayLoadHelper2
0x1800176c7  movdqa  xmm0, [rsp+68h+var_48]
0x1800176cd  movdqa  xmm1, [rsp+68h+var_38]
0x1800176d3  movdqa  xmm2, [rsp+68h+var_28]
0x1800176d9  movdqa  xmm3, [rsp+68h+var_18]
0x1800176df  mov     rcx, [rsp+68h+arg_0]
0x1800176e4  mov     rdx, [rsp+68h+arg_8]
0x1800176e9  mov     r8, [rsp+68h+arg_10]
0x1800176f1  mov     r9, [rsp+68h+arg_18]
0x1800176f9  add     rsp, 68h
0x1800176fd  jmp     short $+2
0x1800176ff  jmp     rax
```
