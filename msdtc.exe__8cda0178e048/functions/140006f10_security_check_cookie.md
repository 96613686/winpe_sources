# __security_check_cookie

- ea: `0x140006f10`
- end: `0x140006f2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400021cc`
- `0x1400022f0`
- `0x1400023c4`
- `0x1400029f0`
- `0x140003094`
- `0x1400031c0`
- `0x1400033b4`
- `0x1400037ac`
- `0x140003c50`
- `0x140003e74`
- `0x1400040dc`
- `0x1400042cc`
- `0x140004870`
- `0x140004b80`
- `0x1400056c0`
- `0x140005a4c`
- `0x1400060d8`
- `0x140006844`
- `0x140006a7c`
- `0x140006b68`
- `0x140006d8c`

## callees

- `0x140001ae0`
- `0x140006f10`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140006f10  cmp     rcx, cs:__security_cookie
0x140006f17  jnz     short loc_140006F29
0x140006f19  rol     rcx, 10h
0x140006f1d  test    cx, 0FFFFh
0x140006f22  jnz     short loc_140006F25
0x140006f24  retn
0x140006f25  ror     rcx, 10h
0x140006f29  jmp     __report_gsfailure
```
