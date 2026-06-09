# __security_check_cookie

- ea: `0x18000cbf0`
- end: `0x18000cc0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fc0`
- `0x18000225c`
- `0x1800024d4`
- `0x180002878`
- `0x180002dc4`
- `0x18000313c`
- `0x1800042d4`
- `0x1800050b0`
- `0x180005470`
- `0x180005f5c`
- `0x18000642c`
- `0x180006900`
- `0x180006f48`
- `0x1800074e0`
- `0x1800075c4`
- `0x18000774c`
- `0x1800079ac`
- `0x180007cf8`
- `0x1800080a8`
- `0x18000874c`
- `0x180008b94`
- `0x180008c8c`
- `0x180008dcc`
- `0x180008ec0`
- `0x180009370`
- `0x1800098ac`
- `0x18000a474`
- `0x18000a624`
- `0x18000afb4`
- `0x18000b328`
- `0x18000b7a0`
- `0x18000b94c`
- `0x18000baa0`
- `0x18000bbc0`
- `0x18000c080`
- `0x18000c5e8`
- `0x18000c89c`
- `0x18000cb3c`

## callees

- `0x1800016e0`
- `0x18000cbf0`

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
0x18000cbf0  cmp     rcx, cs:__security_cookie
0x18000cbf7  jnz     short ReportFailure
0x18000cbf9  rol     rcx, 10h
0x18000cbfd  test    cx, 0FFFFh
0x18000cc02  jnz     short RestoreRcx
0x18000cc04  retn
0x18000cc05  ror     rcx, 10h
0x18000cc09  jmp     __report_gsfailure
```
