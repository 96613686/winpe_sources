# __security_check_cookie

- ea: `0x140002cb0`
- end: `0x140002cce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001adc`
- `0x140001c68`
- `0x140001e74`
- `0x140001f30`
- `0x1400023ac`
- `0x140002c10`

## callees

- `0x1400016c0`
- `0x140002cb0`

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
0x140002cb0  cmp     rcx, cs:__security_cookie
0x140002cb7  jnz     short loc_140002CC9
0x140002cb9  rol     rcx, 10h
0x140002cbd  test    cx, 0FFFFh
0x140002cc2  jnz     short loc_140002CC5
0x140002cc4  retn
0x140002cc5  ror     rcx, 10h
0x140002cc9  jmp     __report_gsfailure
```
