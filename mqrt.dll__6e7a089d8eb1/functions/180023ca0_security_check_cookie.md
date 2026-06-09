# __security_check_cookie

- ea: `0x180023ca0`
- end: `0x180023cbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001178`
- `0x180002314`
- `0x180002708`
- `0x180002d98`
- `0x180003034`
- `0x180003ce0`
- `0x180003e48`
- `0x180004010`
- `0x180004684`
- `0x180004a38`
- `0x180005d50`
- `0x180005eec`
- `0x18000653c`
- `0x1800074d4`
- `0x1800080c0`
- `0x1800082b0`
- `0x180008d34`
- `0x1800094b4`
- `0x18000a844`
- `0x18000a8b8`
- `0x18000aa6c`
- `0x18000aad0`
- `0x18000b080`
- `0x18000dc48`
- `0x18000e590`
- `0x18000fcf0`
- `0x180011050`
- `0x180011200`
- `0x1800112b0`
- `0x180011c14`
- `0x1800120b0`
- `0x180013e88`
- `0x180014e08`
- `0x180015e08`
- `0x180016944`
- `0x180017edc`
- `0x180018800`
- `0x180018f4c`
- `0x180019944`
- `0x180019d3c`
- `0x18001a3b0`
- `0x18001c188`
- `0x18001c688`
- `0x18001c914`
- `0x18001d138`
- `0x180020750`
- `0x180020b48`
- `0x1800211e0`
- `0x1800219b8`

## callees

- `0x180002130`
- `0x180023ca0`

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
0x180023ca0  cmp     rcx, cs:__security_cookie
0x180023ca7  jnz     short ReportFailure
0x180023ca9  rol     rcx, 10h
0x180023cad  test    cx, 0FFFFh
0x180023cb2  jnz     short RestoreRcx
0x180023cb4  retn
0x180023cb5  ror     rcx, 10h
0x180023cb9  jmp     __report_gsfailure
```
