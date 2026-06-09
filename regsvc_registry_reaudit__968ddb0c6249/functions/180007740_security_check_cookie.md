# __security_check_cookie

- ea: `0x180007740`
- end: `0x18000775e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `83`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000113c`
- `0x1800012dc`
- `0x1800013ac`
- `0x180001450`
- `0x1800059a0`
- `0x180005c60`
- `0x180005df0`
- `0x180005f20`
- `0x180008560`
- `0x180008c30`
- `0x1800093a8`
- `0x18000a0d4`
- `0x18000bc48`
- `0x18000c6f4`
- `0x18000cc70`
- `0x18000d158`
- `0x18000dd34`
- `0x18000e1a8`
- `0x18000fb6c`
- `0x180010020`
- `0x1800100e0`
- `0x180010430`
- `0x180011180`
- `0x1800113b0`
- `0x180012d14`
- `0x180012df0`
- `0x180012ec4`
- `0x180012fac`
- `0x1800136b0`
- `0x1800142ac`
- `0x1800143b0`
- `0x180016260`
- `0x180016c10`
- `0x180016d3c`
- `0x180017210`
- `0x1800173cc`
- `0x18001782c`
- `0x180017b54`
- `0x180017f6c`
- `0x1800180b4`
- `0x180018538`
- `0x180018960`
- `0x180018a60`
- `0x180018b90`
- `0x180018c80`
- `0x180018dd0`
- `0x180018f20`
- `0x180019060`
- `0x180019290`

## callees

- `0x180007740`
- `0x180007c70`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180007740  cmp     rcx, cs:__security_cookie
0x180007747  jnz     short ReportFailure
0x180007749  rol     rcx, 10h
0x18000774d  test    cx, 0FFFFh
0x180007752  jnz     short RestoreRcx
0x180007754  retn
0x180007755  ror     rcx, 10h; StackCookie
0x180007759  jmp     __report_gsfailure
```
