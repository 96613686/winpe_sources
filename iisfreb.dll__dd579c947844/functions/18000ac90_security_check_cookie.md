# __security_check_cookie

- ea: `0x18000ac90`
- end: `0x18000acae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023cc`
- `0x180003654`
- `0x180004440`
- `0x1800047a4`
- `0x180004ae4`
- `0x180005210`
- `0x180006944`
- `0x180006f98`
- `0x180007518`
- `0x180007f70`
- `0x180008178`
- `0x180008ad8`
- `0x180008d98`
- `0x180009360`
- `0x180009520`
- `0x1800095dc`
- `0x180009948`
- `0x18000a2e8`
- `0x18000a6d8`
- `0x18000a7e0`
- `0x18000abd0`

## callees

- `0x180001580`
- `0x18000ac90`

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
0x18000ac90  cmp     rcx, cs:__security_cookie
0x18000ac97  jnz     short ReportFailure
0x18000ac99  rol     rcx, 10h
0x18000ac9d  test    cx, 0FFFFh
0x18000aca2  jnz     short RestoreRcx
0x18000aca4  retn
0x18000aca5  ror     rcx, 10h
0x18000aca9  jmp     __report_gsfailure
```
