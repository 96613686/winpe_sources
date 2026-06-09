# __security_check_cookie

- ea: `0x180014130`
- end: `0x18001414e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `60`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001100`
- `0x1800013b4`
- `0x1800016ac`
- `0x180005110`
- `0x1800063a0`
- `0x1800064c4`
- `0x180006ad0`
- `0x180006b90`
- `0x1800074e0`
- `0x180008690`
- `0x180009700`
- `0x18000a3c0`
- `0x18000b68c`
- `0x18000bea0`
- `0x18000c540`
- `0x18000c5f0`
- `0x18000d07c`
- `0x18000d328`
- `0x18000e664`
- `0x18000e6f0`
- `0x18000eac8`
- `0x18000fab0`
- `0x18000fb70`
- `0x180010288`
- `0x180012e98`
- `0x180015604`
- `0x1800158b0`
- `0x180016668`
- `0x1800167d4`
- `0x1800169a0`
- `0x180017124`
- `0x18001743c`
- `0x180018794`
- `0x180018ef8`
- `0x180019eec`
- `0x18001aac0`
- `0x18001acc8`
- `0x18001af34`
- `0x18001b220`
- `0x18001cb54`
- `0x18001cc20`
- `0x18001f17c`
- `0x18001f5ac`
- `0x18001f73c`
- `0x18001f904`
- `0x18001fafc`
- `0x18001fd54`
- `0x1800200a4`
- `0x180020304`

## callees

- `0x180014130`
- `0x180014590`

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
0x180014130  cmp     rcx, cs:__security_cookie
0x180014137  jnz     short ReportFailure
0x180014139  rol     rcx, 10h
0x18001413d  test    cx, 0FFFFh
0x180014142  jnz     short RestoreRcx
0x180014144  retn
0x180014145  ror     rcx, 10h; StackCookie
0x180014149  jmp     __report_gsfailure
```
