# __security_check_cookie

- ea: `0x140001b60`
- end: `0x140001b7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400036d0`
- `0x140003850`
- `0x140003f78`
- `0x140004c40`
- `0x1400052a4`
- `0x140005324`
- `0x14000baf8`
- `0x14000d384`
- `0x14000ea0c`
- `0x14000f4f4`
- `0x1400100e4`
- `0x14001088c`
- `0x140011b98`
- `0x140012cb4`
- `0x140012f2c`
- `0x14001cf60`
- `0x14001d06c`
- `0x14001daa0`
- `0x140023e64`
- `0x14002410c`
- `0x140024cc0`
- `0x1400251d4`
- `0x14002774c`
- `0x140029188`
- `0x140029854`
- `0x14002a154`
- `0x14002c288`

## callees

- `0x140001b60`
- `0x140002380`

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
0x140001b60  cmp     rcx, cs:__security_cookie
0x140001b67  jnz     short loc_140001B79
0x140001b69  rol     rcx, 10h
0x140001b6d  test    cx, 0FFFFh
0x140001b72  jnz     short loc_140001B75
0x140001b74  retn
0x140001b75  ror     rcx, 10h; StackCookie
0x140001b79  jmp     __report_gsfailure
```
