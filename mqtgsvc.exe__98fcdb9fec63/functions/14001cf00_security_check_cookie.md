# __security_check_cookie

- ea: `0x14001cf00`
- end: `0x14001cf1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001918`
- `0x140001d04`
- `0x140003530`
- `0x140003630`
- `0x140003f54`
- `0x140004c24`
- `0x1400053dc`
- `0x140006b54`
- `0x140006d34`
- `0x140007034`
- `0x1400076a8`
- `0x140008520`
- `0x14000cac4`
- `0x14000d4a8`
- `0x14000f0a4`
- `0x14000f308`
- `0x14000f6e0`
- `0x14000f858`
- `0x14000f9d8`
- `0x14000fabc`
- `0x14000fbcc`
- `0x1400115c8`
- `0x140011f54`
- `0x1400125cc`
- `0x1400127c0`
- `0x140012d70`
- `0x140012e34`
- `0x140012edc`
- `0x140013200`
- `0x1400133e0`
- `0x140013bf8`
- `0x140013e20`
- `0x140013ee0`
- `0x140013fa0`
- `0x140014130`
- `0x1400142c0`
- `0x140014370`
- `0x140014430`
- `0x1400144f0`
- `0x1400149f4`
- `0x140015dc8`
- `0x1400167e0`
- `0x1400168d4`
- `0x1400176a8`
- `0x140017810`
- `0x1400179d8`
- `0x140017cf4`
- `0x140018204`
- `0x14001855c`
- `0x140019638`

## callees

- `0x140001b20`
- `0x14001cf00`

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
0x14001cf00  cmp     rcx, cs:__security_cookie
0x14001cf07  jnz     short loc_14001CF19
0x14001cf09  rol     rcx, 10h
0x14001cf0d  test    cx, 0FFFFh
0x14001cf12  jnz     short loc_14001CF15
0x14001cf14  retn
0x14001cf15  ror     rcx, 10h
0x14001cf19  jmp     __report_gsfailure
```
