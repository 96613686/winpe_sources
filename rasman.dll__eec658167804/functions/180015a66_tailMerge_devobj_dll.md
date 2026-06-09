# __tailMerge_devobj_dll

- ea: `0x180015a66`
- end: `0x180015adf`
- name: `__tailMerge_devobj_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015ae5`
- `0x180015af7`
- `0x180015b09`
- `0x180015b1b`

## callees

- `0x180014230`
- `0x180015a66`

## pseudocode

```c
__int64 __fastcall _tailMerge_devobj_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_devobj_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180015a66  mov     [rsp+arg_0], rcx
0x180015a6b  mov     [rsp+arg_8], rdx
0x180015a70  mov     [rsp+arg_10], r8
0x180015a75  mov     [rsp+arg_18], r9
0x180015a7a  sub     rsp, 68h
0x180015a7e  movdqa  [rsp+68h+var_48], xmm0
0x180015a84  movdqa  [rsp+68h+var_38], xmm1
0x180015a8a  movdqa  [rsp+68h+var_28], xmm2
0x180015a90  movdqa  [rsp+68h+var_18], xmm3
0x180015a96  mov     rdx, rax
0x180015a99  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_devobj_dll
0x180015aa0  call    __delayLoadHelper2
0x180015aa5  movdqa  xmm0, [rsp+68h+var_48]
0x180015aab  movdqa  xmm1, [rsp+68h+var_38]
0x180015ab1  movdqa  xmm2, [rsp+68h+var_28]
0x180015ab7  movdqa  xmm3, [rsp+68h+var_18]
0x180015abd  mov     rcx, [rsp+68h+arg_0]
0x180015ac2  mov     rdx, [rsp+68h+arg_8]
0x180015ac7  mov     r8, [rsp+68h+arg_10]
0x180015acf  mov     r9, [rsp+68h+arg_18]
0x180015ad7  add     rsp, 68h
0x180015adb  jmp     short $+2
0x180015add  jmp     rax
```
