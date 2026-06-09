# __tailMerge_user32_dll

- ea: `0x180002b76`
- end: `0x180002bef`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002bf5`
- `0x180002c07`
- `0x180002c19`
- `0x180002db2`
- `0x180002dc4`
- `0x180002dd6`
- `0x180002de8`
- `0x180002dfa`
- `0x180002e0c`
- `0x180002e1e`
- `0x180002e30`
- `0x180002e42`
- `0x180002e54`
- `0x180002e66`
- `0x180002e78`
- `0x180002e8a`
- `0x180002e9c`
- `0x180002eae`
- `0x180002ec0`
- `0x180002ed2`
- `0x180002fdb`
- `0x180002fed`
- `0x180002fff`

## callees

- `0x180002b76`
- `0x180011dd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b76  mov     [rsp+arg_0], rcx
0x180002b7b  mov     [rsp+arg_8], rdx
0x180002b80  mov     [rsp+arg_10], r8
0x180002b85  mov     [rsp+arg_18], r9
0x180002b8a  sub     rsp, 68h
0x180002b8e  movdqa  [rsp+68h+var_48], xmm0
0x180002b94  movdqa  [rsp+68h+var_38], xmm1
0x180002b9a  movdqa  [rsp+68h+var_28], xmm2
0x180002ba0  movdqa  [rsp+68h+var_18], xmm3
0x180002ba6  mov     rdx, rax
0x180002ba9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x180002bb0  call    __delayLoadHelper2
0x180002bb5  movdqa  xmm0, [rsp+68h+var_48]
0x180002bbb  movdqa  xmm1, [rsp+68h+var_38]
0x180002bc1  movdqa  xmm2, [rsp+68h+var_28]
0x180002bc7  movdqa  xmm3, [rsp+68h+var_18]
0x180002bcd  mov     rcx, [rsp+68h+arg_0]
0x180002bd2  mov     rdx, [rsp+68h+arg_8]
0x180002bd7  mov     r8, [rsp+68h+arg_10]
0x180002bdf  mov     r9, [rsp+68h+arg_18]
0x180002be7  add     rsp, 68h
0x180002beb  jmp     short $+2
0x180002bed  jmp     rax
```
