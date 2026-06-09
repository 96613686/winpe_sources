# __security_check_cookie

- ea: `0x18001b550`
- end: `0x18001b56e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d60`
- `0x180005890`
- `0x180005fd8`
- `0x180006730`
- `0x180006d04`
- `0x180008670`
- `0x18000b290`
- `0x18000bdb8`
- `0x18000be1c`
- `0x18000be80`
- `0x18000bf18`
- `0x18000bfcc`
- `0x18000c6e0`
- `0x18000c914`
- `0x18000caf0`
- `0x18000d370`
- `0x18000fc44`
- `0x18000fdcc`
- `0x180012bf4`
- `0x1800146d0`
- `0x180014cb0`
- `0x180014d60`
- `0x1800154e4`
- `0x180015ca0`
- `0x18001650c`
- `0x180016738`
- `0x180016c58`
- `0x180016cd0`
- `0x1800174b0`
- `0x180017684`
- `0x180017ac4`
- `0x180017b5c`
- `0x180018500`
- `0x1800185e4`
- `0x180018a28`
- `0x180018c44`
- `0x180018fd0`
- `0x18001a44c`
- `0x18001b3d0`

## callees

- `0x18000a300`
- `0x18001b550`

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
0x18001b550  cmp     rcx, cs:__security_cookie
0x18001b557  jnz     short ReportFailure
0x18001b559  rol     rcx, 10h
0x18001b55d  test    cx, 0FFFFh
0x18001b562  jnz     short RestoreRcx
0x18001b564  retn
0x18001b565  ror     rcx, 10h
0x18001b569  jmp     __report_gsfailure
```
