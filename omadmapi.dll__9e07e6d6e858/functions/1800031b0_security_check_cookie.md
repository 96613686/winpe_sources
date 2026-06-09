# __security_check_cookie

- ea: `0x1800031b0`
- end: `0x1800031ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `80`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001150`
- `0x1800011f8`
- `0x1800012ec`
- `0x1800013dc`
- `0x1800014a0`
- `0x180001af0`
- `0x180001ce0`
- `0x180001fb0`
- `0x180002470`
- `0x180002670`
- `0x1800027e0`
- `0x180002a60`
- `0x180002c80`
- `0x180003724`
- `0x180005304`
- `0x1800055d0`
- `0x180006360`
- `0x180008770`
- `0x180008d70`
- `0x1800093b4`
- `0x180009674`
- `0x18000a8a4`
- `0x18000ac80`
- `0x18000b528`
- `0x18000b67c`
- `0x18000c718`
- `0x18000d3ec`
- `0x18000e5d4`
- `0x18000f47c`
- `0x18000fc34`
- `0x180010614`
- `0x180010720`
- `0x180011190`
- `0x180011bc0`
- `0x180013468`
- `0x180014338`
- `0x180014570`
- `0x1800145f4`
- `0x180014698`
- `0x18001473c`
- `0x1800148f0`
- `0x180014b20`
- `0x180015120`
- `0x180015bb0`
- `0x180015d40`
- `0x180015df0`
- `0x180016160`
- `0x180016c50`
- `0x1800174d0`

## callees

- `0x1800031b0`
- `0x1800036f0`

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
0x1800031b0  cmp     rcx, cs:__security_cookie
0x1800031b7  jnz     short ReportFailure
0x1800031b9  rol     rcx, 10h
0x1800031bd  test    cx, 0FFFFh
0x1800031c2  jnz     short RestoreRcx
0x1800031c4  retn
0x1800031c5  ror     rcx, 10h; StackCookie
0x1800031c9  jmp     __report_gsfailure
```
