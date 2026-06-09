# __security_check_cookie

- ea: `0x140002190`
- end: `0x1400021ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001580`
- `0x140001824`
- `0x14000319c`
- `0x140003260`
- `0x1400036d8`
- `0x14000381c`
- `0x140003e58`
- `0x140004104`
- `0x1400048ac`
- `0x140004924`
- `0x1400051d8`
- `0x140005ce8`
- `0x1400060b8`
- `0x1400066c4`
- `0x140006748`
- `0x140006810`
- `0x140007104`
- `0x1400073e4`
- `0x140007804`
- `0x140007f60`
- `0x14000809c`
- `0x1400081a8`
- `0x140008558`
- `0x1400093c8`
- `0x140009494`
- `0x140009dac`
- `0x14000a440`
- `0x14000b358`
- `0x14000b504`
- `0x14000b8d0`
- `0x14000c02c`
- `0x14000c2ac`
- `0x14000c36c`
- `0x14000d240`
- `0x14000d368`
- `0x14000d8b8`
- `0x14000dd80`
- `0x14000e114`
- `0x14000e25c`
- `0x14000eac8`
- `0x14000eeb8`
- `0x14000f358`
- `0x14000f490`
- `0x14000f530`

## callees

- `0x140002190`
- `0x140002780`

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
0x140002190  cmp     rcx, cs:__security_cookie
0x140002197  jnz     short loc_1400021A9
0x140002199  rol     rcx, 10h
0x14000219d  test    cx, 0FFFFh
0x1400021a2  jnz     short loc_1400021A5
0x1400021a4  retn
0x1400021a5  ror     rcx, 10h; StackCookie
0x1400021a9  jmp     __report_gsfailure
```
