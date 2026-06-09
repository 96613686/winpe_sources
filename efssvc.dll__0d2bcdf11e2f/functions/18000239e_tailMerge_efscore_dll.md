# __tailMerge_efscore_dll

- ea: `0x18000239e`
- end: `0x180002417`
- name: `__tailMerge_efscore_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `65`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000241d`
- `0x18000242f`
- `0x180002441`
- `0x180002453`
- `0x180002465`
- `0x180002477`
- `0x180002489`
- `0x18000249b`
- `0x1800024ad`
- `0x1800024bf`
- `0x1800024d1`
- `0x1800024e3`
- `0x1800024f5`
- `0x180002507`
- `0x180002519`
- `0x18000252b`
- `0x18000253d`
- `0x18000254f`
- `0x180002561`
- `0x180002573`
- `0x180002585`
- `0x180002597`
- `0x1800025a9`
- `0x1800025bb`
- `0x1800025cd`
- `0x1800025df`
- `0x1800025f1`
- `0x180002603`
- `0x180002615`
- `0x180002627`
- `0x180002639`
- `0x18000264b`
- `0x18000265d`
- `0x18000266f`
- `0x180002681`
- `0x180002693`
- `0x1800026a5`
- `0x1800026b7`
- `0x1800026c9`
- `0x1800026db`
- `0x1800026ed`
- `0x1800026ff`
- `0x180002711`
- `0x180002723`
- `0x180002735`
- `0x180002747`
- `0x180002759`
- `0x18000276b`
- `0x18000277d`
- `0x18000278f`

## callees

- `0x18000239e`
- `0x180008790`

## pseudocode

```c
__int64 __fastcall _tailMerge_efscore_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_efscore_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000239e  mov     [rsp+arg_0], rcx
0x1800023a3  mov     [rsp+arg_8], rdx
0x1800023a8  mov     [rsp+arg_10], r8
0x1800023ad  mov     [rsp+arg_18], r9
0x1800023b2  sub     rsp, 68h
0x1800023b6  movdqa  [rsp+68h+var_48], xmm0
0x1800023bc  movdqa  [rsp+68h+var_38], xmm1
0x1800023c2  movdqa  [rsp+68h+var_28], xmm2
0x1800023c8  movdqa  [rsp+68h+var_18], xmm3
0x1800023ce  mov     rdx, rax
0x1800023d1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_efscore_dll
0x1800023d8  call    __delayLoadHelper2
0x1800023dd  movdqa  xmm0, [rsp+68h+var_48]
0x1800023e3  movdqa  xmm1, [rsp+68h+var_38]
0x1800023e9  movdqa  xmm2, [rsp+68h+var_28]
0x1800023ef  movdqa  xmm3, [rsp+68h+var_18]
0x1800023f5  mov     rcx, [rsp+68h+arg_0]
0x1800023fa  mov     rdx, [rsp+68h+arg_8]
0x1800023ff  mov     r8, [rsp+68h+arg_10]
0x180002407  mov     r9, [rsp+68h+arg_18]
0x18000240f  add     rsp, 68h
0x180002413  jmp     short $+2
0x180002415  jmp     rax
```
