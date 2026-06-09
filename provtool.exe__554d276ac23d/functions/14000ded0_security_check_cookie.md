# __security_check_cookie

- ea: `0x14000ded0`
- end: `0x14000deee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001098`
- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x1400023bc`
- `0x140002ce8`
- `0x140002f94`
- `0x140003210`
- `0x140003ce4`
- `0x140003de0`
- `0x1400045f0`
- `0x140004d58`
- `0x140005204`
- `0x140005580`
- `0x1400059ac`
- `0x140006b70`
- `0x140007844`
- `0x14000820c`
- `0x140009230`
- `0x140009398`
- `0x140009590`
- `0x140009918`
- `0x140009c8c`
- `0x14000a3d4`
- `0x14000aae8`
- `0x14000ac60`
- `0x14000ad18`
- `0x14000b250`
- `0x14000b454`
- `0x14000be30`
- `0x14000c0e0`
- `0x14000c610`
- `0x14000c7f0`
- `0x14000c920`
- `0x14000ca40`
- `0x14000cd30`
- `0x14000cf10`
- `0x14000d760`
- `0x14000ddac`

## callees

- `0x140001f10`
- `0x14000ded0`

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
0x14000ded0  cmp     rcx, cs:__security_cookie
0x14000ded7  jnz     short loc_14000DEE9
0x14000ded9  rol     rcx, 10h
0x14000dedd  test    cx, 0FFFFh
0x14000dee2  jnz     short loc_14000DEE5
0x14000dee4  retn
0x14000dee5  ror     rcx, 10h
0x14000dee9  jmp     __report_gsfailure
```
