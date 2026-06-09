# __security_check_cookie

- ea: `0x140002f60`
- end: `0x140002f7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `158`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010e0`
- `0x140001278`
- `0x140001308`
- `0x1400013ac`
- `0x140001454`
- `0x140001518`
- `0x1400015c4`
- `0x14000168c`
- `0x140001728`
- `0x140001824`
- `0x140001ad8`
- `0x140001bd4`
- `0x140001d38`
- `0x140001e94`
- `0x14000218c`
- `0x1400022b4`
- `0x140002368`
- `0x140002434`
- `0x1400032e8`
- `0x140004670`
- `0x1400057b0`
- `0x140005960`
- `0x140006810`
- `0x140007630`
- `0x140008af0`
- `0x140009f80`
- `0x14000a940`
- `0x14000bc80`
- `0x14000bde0`
- `0x14000bf50`
- `0x14000c280`
- `0x14000d91c`
- `0x14000dbb8`
- `0x14000eb58`
- `0x14000eefc`
- `0x14000f2cc`
- `0x14000fdf4`
- `0x140010170`
- `0x140011224`
- `0x140011330`
- `0x140011d3c`
- `0x1400134cc`
- `0x140014060`
- `0x140014188`
- `0x140014458`
- `0x140014f64`
- `0x14001628c`
- `0x1400163cc`
- `0x140016da0`

## callees

- `0x140002f60`
- `0x1400038b0`

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
0x140002f60  cmp     rcx, cs:__security_cookie
0x140002f67  jnz     short loc_140002F79
0x140002f69  rol     rcx, 10h
0x140002f6d  test    cx, 0FFFFh
0x140002f72  jnz     short loc_140002F75
0x140002f74  retn
0x140002f75  ror     rcx, 10h; StackCookie
0x140002f79  jmp     __report_gsfailure
```
