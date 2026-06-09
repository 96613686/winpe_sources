# __tailMerge_dui70_dll

- ea: `0x1800023b4`
- end: `0x18000242d`
- name: `__tailMerge_dui70_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002433`
- `0x180002450`
- `0x180002462`
- `0x180002474`
- `0x180002486`
- `0x180002498`
- `0x1800024aa`
- `0x1800024bc`
- `0x1800024ce`
- `0x1800024e0`
- `0x1800024f2`
- `0x180002504`
- `0x180002516`
- `0x180002528`
- `0x18000253a`
- `0x18000254c`
- `0x18000255e`
- `0x180002570`
- `0x180002582`
- `0x180002594`
- `0x1800025a6`
- `0x1800025b8`

## callees

- `0x1800023b4`
- `0x18000cb80`

## pseudocode

```c
__int64 __fastcall _tailMerge_dui70_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dui70_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800023b4  mov     [rsp+arg_0], rcx
0x1800023b9  mov     [rsp+arg_8], rdx
0x1800023be  mov     [rsp+arg_10], r8
0x1800023c3  mov     [rsp+arg_18], r9
0x1800023c8  sub     rsp, 68h
0x1800023cc  movdqa  [rsp+68h+var_48], xmm0
0x1800023d2  movdqa  [rsp+68h+var_38], xmm1
0x1800023d8  movdqa  [rsp+68h+var_28], xmm2
0x1800023de  movdqa  [rsp+68h+var_18], xmm3
0x1800023e4  mov     rdx, rax
0x1800023e7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dui70_dll
0x1800023ee  call    __delayLoadHelper2
0x1800023f3  movdqa  xmm0, [rsp+68h+var_48]
0x1800023f9  movdqa  xmm1, [rsp+68h+var_38]
0x1800023ff  movdqa  xmm2, [rsp+68h+var_28]
0x180002405  movdqa  xmm3, [rsp+68h+var_18]
0x18000240b  mov     rcx, [rsp+68h+arg_0]
0x180002410  mov     rdx, [rsp+68h+arg_8]
0x180002415  mov     r8, [rsp+68h+arg_10]
0x18000241d  mov     r9, [rsp+68h+arg_18]
0x180002425  add     rsp, 68h
0x180002429  jmp     short $+2
0x18000242b  jmp     rax
```
