# __security_check_cookie

- ea: `0x180001190`
- end: `0x1800011ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001590`
- `0x180002ef8`
- `0x180003194`
- `0x1800034ac`
- `0x18000385c`
- `0x180003d14`
- `0x18000408c`
- `0x180005300`
- `0x1800060e0`
- `0x1800061fc`
- `0x180006538`
- `0x1800067a8`
- `0x180006bb8`
- `0x1800077ac`
- `0x180007b74`
- `0x180007e64`
- `0x1800099d4`
- `0x18000a0b4`
- `0x18000a374`
- `0x18000a4b8`
- `0x18000a524`
- `0x18000a9c4`
- `0x18000ae54`
- `0x18000b1fc`

## callees

- `0x180001190`
- `0x180001890`

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
0x180001190  cmp     rcx, cs:__security_cookie
0x180001197  jnz     short loc_1800011A9
0x180001199  rol     rcx, 10h
0x18000119d  test    cx, 0FFFFh
0x1800011a2  jnz     short loc_1800011A5
0x1800011a4  retn
0x1800011a5  ror     rcx, 10h; StackCookie
0x1800011a9  jmp     __report_gsfailure
```
