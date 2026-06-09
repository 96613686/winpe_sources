# __security_check_cookie

- ea: `0x1800136b0`
- end: `0x1800136ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`
- `0x18000233c`
- `0x180002844`
- `0x180002b10`
- `0x180003ce0`
- `0x18000597c`
- `0x180005aac`
- `0x18000615c`
- `0x1800075c0`
- `0x180007d5c`
- `0x1800086fc`
- `0x180008b8c`
- `0x180008d5c`
- `0x180008f00`
- `0x180009108`
- `0x180009ba0`
- `0x180009c78`
- `0x18000b0cc`
- `0x18000b17c`
- `0x18000b200`
- `0x18000bdf4`
- `0x18000d670`
- `0x18000e2a0`
- `0x18000e600`
- `0x18000e7c0`
- `0x18000ea98`
- `0x18000ebf8`
- `0x18000f5d8`
- `0x18000f970`
- `0x18000fd18`
- `0x18000fe80`
- `0x180011920`
- `0x180011a10`
- `0x180011f1c`
- `0x180011fcc`
- `0x180012560`

## callees

- `0x180001c60`
- `0x1800136b0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x1800136b0  cmp     rcx, cs:__security_cookie
0x1800136b7  jnz     short ReportFailure
0x1800136b9  rol     rcx, 10h
0x1800136bd  test    cx, 0FFFFh
0x1800136c2  jnz     short RestoreRcx
0x1800136c4  retn
0x1800136c5  ror     rcx, 10h
0x1800136c9  jmp     __report_gsfailure
```
