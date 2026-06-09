# __tailMerge_dui70_dll

- ea: `0x1800030ff`
- end: `0x180003178`
- name: `__tailMerge_dui70_dll`
- size: `121`
- prototype: ``
- caller_count: `133`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000317e`
- `0x180003190`
- `0x1800031a2`
- `0x1800031b4`
- `0x1800031c6`
- `0x1800031d8`
- `0x1800031ea`
- `0x1800031fc`
- `0x18000320e`
- `0x180003220`
- `0x180003232`
- `0x180003244`
- `0x180003256`
- `0x180003268`
- `0x18000327a`
- `0x18000328c`
- `0x18000329e`
- `0x1800032b0`
- `0x1800032c2`
- `0x1800032d4`
- `0x1800032e6`
- `0x1800032f8`
- `0x18000330a`
- `0x18000332c`
- `0x18000334c`
- `0x18000336c`
- `0x18000338c`
- `0x1800033ac`
- `0x1800033cc`
- `0x1800033ec`
- `0x18000340c`
- `0x18000342c`
- `0x18000344c`
- `0x18000346c`
- `0x18000348c`
- `0x1800034ac`
- `0x1800034cc`
- `0x1800034ec`
- `0x18000350c`
- `0x18000352c`
- `0x18000354c`
- `0x18000356c`
- `0x18000358c`
- `0x1800035ac`
- `0x1800035cc`
- `0x1800035ec`
- `0x18000360c`
- `0x18000362c`
- `0x18000364c`
- `0x18000366c`

## callees

- `0x1800030ff`
- `0x180018990`

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
0x1800030ff  mov     [rsp+arg_0], rcx
0x180003104  mov     [rsp+arg_8], rdx
0x180003109  mov     [rsp+arg_10], r8
0x18000310e  mov     [rsp+arg_18], r9
0x180003113  sub     rsp, 68h
0x180003117  movdqa  [rsp+68h+var_48], xmm0
0x18000311d  movdqa  [rsp+68h+var_38], xmm1
0x180003123  movdqa  [rsp+68h+var_28], xmm2
0x180003129  movdqa  [rsp+68h+var_18], xmm3
0x18000312f  mov     rdx, rax
0x180003132  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dui70_dll
0x180003139  call    __delayLoadHelper2
0x18000313e  movdqa  xmm0, [rsp+68h+var_48]
0x180003144  movdqa  xmm1, [rsp+68h+var_38]
0x18000314a  movdqa  xmm2, [rsp+68h+var_28]
0x180003150  movdqa  xmm3, [rsp+68h+var_18]
0x180003156  mov     rcx, [rsp+68h+arg_0]
0x18000315b  mov     rdx, [rsp+68h+arg_8]
0x180003160  mov     r8, [rsp+68h+arg_10]
0x180003168  mov     r9, [rsp+68h+arg_18]
0x180003170  add     rsp, 68h
0x180003174  jmp     short $+2
0x180003176  jmp     rax
```
