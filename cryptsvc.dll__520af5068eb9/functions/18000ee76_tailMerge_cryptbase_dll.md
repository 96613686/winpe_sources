# __tailMerge_cryptbase_dll

- ea: `0x18000ee76`
- end: `0x18000eeef`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eef5`

## callees

- `0x18000bd20`
- `0x18000ee76`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ee76  mov     [rsp+arg_0], rcx
0x18000ee7b  mov     [rsp+arg_8], rdx
0x18000ee80  mov     [rsp+arg_10], r8
0x18000ee85  mov     [rsp+arg_18], r9
0x18000ee8a  sub     rsp, 68h
0x18000ee8e  movdqa  [rsp+68h+var_48], xmm0
0x18000ee94  movdqa  [rsp+68h+var_38], xmm1
0x18000ee9a  movdqa  [rsp+68h+var_28], xmm2
0x18000eea0  movdqa  [rsp+68h+var_18], xmm3
0x18000eea6  mov     rdx, rax
0x18000eea9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x18000eeb0  call    __delayLoadHelper2
0x18000eeb5  movdqa  xmm0, [rsp+68h+var_48]
0x18000eebb  movdqa  xmm1, [rsp+68h+var_38]
0x18000eec1  movdqa  xmm2, [rsp+68h+var_28]
0x18000eec7  movdqa  xmm3, [rsp+68h+var_18]
0x18000eecd  mov     rcx, [rsp+68h+arg_0]
0x18000eed2  mov     rdx, [rsp+68h+arg_8]
0x18000eed7  mov     r8, [rsp+68h+arg_10]
0x18000eedf  mov     r9, [rsp+68h+arg_18]
0x18000eee7  add     rsp, 68h
0x18000eeeb  jmp     short $+2
0x18000eeed  jmp     rax
```
