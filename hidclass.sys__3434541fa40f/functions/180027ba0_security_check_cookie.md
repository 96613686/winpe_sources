# __security_check_cookie

- ea: `0x180027ba0`
- end: `0x180027bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `71`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180003090`
- `0x180008650`
- `0x180009664`
- `0x18000a430`
- `0x18000c948`
- `0x1800115f8`
- `0x180014980`
- `0x180014a44`
- `0x180017264`
- `0x180019d28`
- `0x18001acb8`
- `0x18001b4f0`
- `0x18001b81c`
- `0x18001c4c0`
- `0x18001d2f8`
- `0x18001d374`
- `0x18001d43c`
- `0x18001d4d4`
- `0x18001d550`
- `0x18001d630`
- `0x18001de68`
- `0x18001e2a4`
- `0x18001e538`
- `0x18001eb28`
- `0x18001ec30`
- `0x18001ed14`
- `0x18001ee14`
- `0x18001fabc`
- `0x18001fba0`
- `0x18001ffbc`
- `0x1800206e0`
- `0x180020c54`
- `0x1800211b0`
- `0x18002136c`
- `0x180021940`
- `0x1800219bc`
- `0x180021ac0`
- `0x180021bb0`
- `0x180021ca0`
- `0x180021d38`
- `0x180021e1c`
- `0x180021f1c`
- `0x18002204c`
- `0x180023e50`
- `0x180023f18`
- `0x180023fe0`
- `0x180024124`
- `0x18002423c`
- `0x18002432c`

## callees

- `0x18001cbb0`
- `0x180027ba0`

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
0x180027ba0  cmp     rcx, cs:__security_cookie
0x180027ba7  jnz     short ReportFailure
0x180027ba9  rol     rcx, 10h
0x180027bad  test    cx, 0FFFFh
0x180027bb2  jnz     short RestoreRcx
0x180027bb4  retn
0x180027bb5  ror     rcx, 10h; StackCookie
0x180027bb9  jmp     __report_gsfailure
```
