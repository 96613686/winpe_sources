# __security_check_cookie

- ea: `0x18001f1b0`
- end: `0x18001f1ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001068`
- `0x180001550`
- `0x180004454`
- `0x180004c00`
- `0x1800058b0`
- `0x180005a18`
- `0x180006090`
- `0x180006730`
- `0x180009ecc`
- `0x18000f148`
- `0x18000f7b0`
- `0x18000f8b8`
- `0x18000fb20`
- `0x1800102c0`
- `0x180010c90`
- `0x180013ffc`
- `0x180015490`
- `0x180015c74`
- `0x18001620c`
- `0x180016c78`
- `0x180016dbc`
- `0x180016e90`
- `0x1800173c0`
- `0x1800175f0`
- `0x180017990`
- `0x180018a08`
- `0x180019060`
- `0x180019574`
- `0x18001b808`
- `0x18001b8b8`
- `0x18001c810`
- `0x18001ca50`
- `0x18001d7b8`
- `0x18001e0e0`
- `0x18001e3ac`
- `0x18001e50c`
- `0x18001e8e8`
- `0x18001eb38`
- `0x18001f0dc`

## callees

- `0x18001a280`
- `0x18001f1b0`

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
0x18001f1b0  cmp     rcx, cs:__security_cookie
0x18001f1b7  jnz     short loc_18001F1C9
0x18001f1b9  rol     rcx, 10h
0x18001f1bd  test    cx, 0FFFFh
0x18001f1c2  jnz     short loc_18001F1C5
0x18001f1c4  retn
0x18001f1c5  ror     rcx, 10h
0x18001f1c9  jmp     __report_gsfailure
```
