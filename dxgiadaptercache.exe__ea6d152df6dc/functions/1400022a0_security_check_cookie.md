# __security_check_cookie

- ea: `0x1400022a0`
- end: `0x1400022be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001590`
- `0x140001834`
- `0x1400035b8`
- `0x14000377c`
- `0x1400038d0`
- `0x1400042ec`
- `0x140004598`
- `0x140004cbc`
- `0x1400051f8`
- `0x140007368`
- `0x140007738`
- `0x140007f28`
- `0x14000893c`
- `0x140009350`
- `0x140009770`
- `0x14000adf0`
- `0x14000b1bc`
- `0x14000badc`
- `0x14000bebc`
- `0x14000c0e4`
- `0x14000d358`
- `0x14000d500`
- `0x14000d6e0`
- `0x14000de70`
- `0x14000e174`
- `0x14000eafc`
- `0x140010c10`
- `0x140010d38`
- `0x1400110b8`
- `0x1400112d0`

## callees

- `0x1400022a0`
- `0x140002890`

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
0x1400022a0  cmp     rcx, cs:__security_cookie
0x1400022a7  jnz     short loc_1400022B9
0x1400022a9  rol     rcx, 10h
0x1400022ad  test    cx, 0FFFFh
0x1400022b2  jnz     short loc_1400022B5
0x1400022b4  retn
0x1400022b5  ror     rcx, 10h; StackCookie
0x1400022b9  jmp     __report_gsfailure
```
