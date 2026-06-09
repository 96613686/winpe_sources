# __security_check_cookie

- ea: `0x18000a1a0`
- end: `0x18000a1be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c4c`
- `0x180001da8`
- `0x180003988`
- `0x180003cf8`
- `0x180004658`
- `0x180004ec4`
- `0x180005430`
- `0x1800054d4`
- `0x180005bcc`
- `0x180005e5c`
- `0x180005fc4`
- `0x180006590`
- `0x180007000`
- `0x18000729c`
- `0x180007548`
- `0x1800076d4`
- `0x1800077d0`
- `0x180007b4c`
- `0x180007cd0`
- `0x1800086bc`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`
- `0x180008d80`
- `0x180009410`
- `0x1800095cc`
- `0x18000973c`
- `0x180009ca0`
- `0x18000a074`

## callees

- `0x180001580`
- `0x18000a1a0`

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
0x18000a1a0  cmp     rcx, cs:__security_cookie
0x18000a1a7  jnz     short ReportFailure
0x18000a1a9  rol     rcx, 10h
0x18000a1ad  test    cx, 0FFFFh
0x18000a1b2  jnz     short RestoreRcx
0x18000a1b4  retn
0x18000a1b5  ror     rcx, 10h
0x18000a1b9  jmp     __report_gsfailure
```
