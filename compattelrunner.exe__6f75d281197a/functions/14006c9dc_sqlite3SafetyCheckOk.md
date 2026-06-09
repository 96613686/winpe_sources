# sqlite3SafetyCheckOk

- ea: `0x14006c9dc`
- end: `0x14006ca23`
- name: `sqlite3SafetyCheckOk`
- size: `71`
- prototype: ``
- caller_count: `55`
- callee_count: `3`
- tags: ``

## callers

- `0x1400267b8`
- `0x140062858`
- `0x14006a0dc`
- `0x140086610`
- `0x1400867f0`
- `0x140087590`
- `0x140087ca0`
- `0x140087d40`
- `0x140087e60`
- `0x140087f70`
- `0x140088000`
- `0x1400883c0`
- `0x140088cc0`
- `0x140088da0`
- `0x140089010`
- `0x140089190`
- `0x1400891f0`
- `0x140089310`
- `0x140089540`
- `0x1400895f0`
- `0x140089620`
- `0x140089670`
- `0x1400896f0`
- `0x1400897b0`
- `0x140089cf0`
- `0x140089fb0`
- `0x14008a170`
- `0x14008a490`
- `0x14008a8b0`
- `0x14008a930`
- `0x14008adc0`
- `0x14008ae30`
- `0x14008b4b0`
- `0x14008b500`
- `0x14008b5f0`
- `0x14008b640`
- `0x14008ba10`
- `0x14008bbb0`
- `0x14008bde0`
- `0x14008be70`
- `0x14008c730`
- `0x14008c7b0`
- `0x14008c9e0`
- `0x14008cb40`
- `0x14008ebb0`
- `0x14008f390`
- `0x14008f3d0`
- `0x14008f460`
- `0x14008f540`
- `0x14008f610`

## callees

- `0x14006c9dc`
- `0x14006ca2c`
- `0x14008b740`

## string_xrefs

- `0x14006ca10`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3SafetyCheckOk(__int64 a1)
{
  const char *v1; // r8

  if ( !a1 )
  {
    v1 = "NULL";
    goto LABEL_3;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
      return 0;
    v1 = "unopened";
LABEL_3:
    sqlite3_log(21, "API call with %s database connection pointer", v1);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14006c9dc  sub     rsp, 28h
0x14006c9e0  test    rcx, rcx
0x14006c9e3  jnz     short loc_14006CA01
0x14006c9e5  lea     r8, aNull_1; "NULL"
0x14006c9ec  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x14006c9f3  mov     ecx, 15h
0x14006c9f8  call    sqlite3_log
0x14006c9fd  xor     eax, eax
0x14006c9ff  jmp     short loc_14006CA1E
0x14006ca01  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x14006ca05  jz      short loc_14006CA19
0x14006ca07  call    sqlite3SafetyCheckSickOrOk
0x14006ca0c  test    eax, eax
0x14006ca0e  jz      short loc_14006C9FD
0x14006ca10  lea     r8, aUnopened; "unopened"
0x14006ca17  jmp     short loc_14006C9EC
0x14006ca19  mov     eax, 1
0x14006ca1e  add     rsp, 28h
0x14006ca22  retn
```
