# __security_check_cookie

- ea: `0x1800265b0`
- end: `0x1800265ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `66`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800015bc`
- `0x18000195c`
- `0x180001c80`
- `0x180002460`
- `0x180002810`
- `0x180002df0`
- `0x180003020`
- `0x18000335c`
- `0x1800036dc`
- `0x180003e7c`
- `0x180003ef0`
- `0x180004b40`
- `0x1800052d0`
- `0x180006710`
- `0x180006d40`
- `0x180007a40`
- `0x180007cc0`
- `0x180008f80`
- `0x18000a9d0`
- `0x18000b090`
- `0x18000ba90`
- `0x18000bb78`
- `0x18000bc60`
- `0x18000c620`
- `0x18000ca20`
- `0x18000cfa0`
- `0x18000ddb0`
- `0x18000e264`
- `0x18000e4ac`
- `0x18000e610`
- `0x18000f004`
- `0x180011280`
- `0x180011eb4`
- `0x180014750`
- `0x180014df0`
- `0x180017500`
- `0x180018f78`
- `0x18001c594`
- `0x18001c790`
- `0x18001d970`
- `0x18001db64`
- `0x18001dc80`
- `0x18001e1b8`
- `0x18001e720`
- `0x18001ec64`
- `0x18001f61c`
- `0x18001fcac`
- `0x18001fe2c`
- `0x18001ff84`
- `0x180020794`

## callees

- `0x18001b970`
- `0x1800265b0`

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
0x1800265b0  cmp     rcx, cs:__security_cookie
0x1800265b7  jnz     short ReportFailure
0x1800265b9  rol     rcx, 10h
0x1800265bd  test    cx, 0FFFFh
0x1800265c2  jnz     short RestoreRcx
0x1800265c4  retn
0x1800265c5  ror     rcx, 10h
0x1800265c9  jmp     __report_gsfailure
```
