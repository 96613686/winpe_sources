# __security_check_cookie

- ea: `0x140001340`
- end: `0x14000135e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400038f8`
- `0x1400040b8`
- `0x140004678`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x1400073d4`
- `0x140008cbc`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`
- `0x14000aa4c`
- `0x14000afd4`
- `0x14000b54c`
- `0x14000b91c`
- `0x14000bdc4`
- `0x14000c1d8`
- `0x14000c5c0`
- `0x14000f15c`
- `0x14000f998`

## callees

- `0x140001340`
- `0x140001370`

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
0x140001340  cmp     rcx, cs:__security_cookie
0x140001347  jnz     short loc_140001359
0x140001349  rol     rcx, 10h
0x14000134d  test    cx, 0FFFFh
0x140001352  jnz     short loc_140001355
0x140001354  retn
0x140001355  ror     rcx, 10h; StackCookie
0x140001359  jmp     __report_gsfailure
```
