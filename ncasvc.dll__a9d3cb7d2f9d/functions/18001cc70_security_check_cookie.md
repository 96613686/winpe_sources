# __security_check_cookie

- ea: `0x18001cc70`
- end: `0x18001cc8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001180`
- `0x180001ee0`
- `0x180004c8c`
- `0x180005df8`
- `0x180006544`
- `0x1800065c8`
- `0x180008ee8`
- `0x180009158`
- `0x18000a398`
- `0x18000a954`
- `0x18000c1d0`
- `0x18000d480`
- `0x18000ddc0`
- `0x18000e250`
- `0x18000e7a4`
- `0x1800112ac`
- `0x180012614`
- `0x1800126a0`
- `0x180012740`
- `0x180012950`
- `0x1800136e0`
- `0x180014248`
- `0x180015f20`
- `0x1800161c8`
- `0x1800163cc`
- `0x180016678`
- `0x180016798`
- `0x180016d38`
- `0x180016ee4`
- `0x180017f14`
- `0x180018ab0`
- `0x180018c40`
- `0x1800193f8`
- `0x180019638`
- `0x18001aec4`
- `0x18001bd68`
- `0x18001cbb0`

## callees

- `0x180003df0`
- `0x18001cc70`

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
0x18001cc70  cmp     rcx, cs:__security_cookie
0x18001cc77  jnz     short ReportFailure
0x18001cc79  rol     rcx, 10h
0x18001cc7d  test    cx, 0FFFFh
0x18001cc82  jnz     short RestoreRcx
0x18001cc84  retn
0x18001cc85  ror     rcx, 10h
0x18001cc89  jmp     __report_gsfailure
```
