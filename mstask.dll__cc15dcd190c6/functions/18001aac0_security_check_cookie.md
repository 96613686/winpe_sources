# __security_check_cookie

- ea: `0x18001aac0`
- end: `0x18001aade`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `81`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001610`
- `0x1800018c0`
- `0x180002ab0`
- `0x180003830`
- `0x180003ce0`
- `0x180004220`
- `0x180004590`
- `0x180005270`
- `0x180005cd0`
- `0x180006550`
- `0x1800069e8`
- `0x180006ba0`
- `0x180007640`
- `0x180007860`
- `0x180007e60`
- `0x18000807c`
- `0x1800082f4`
- `0x180008688`
- `0x180009490`
- `0x180009b1c`
- `0x180009cd0`
- `0x18000b740`
- `0x18000b920`
- `0x18000bb50`
- `0x18000beb8`
- `0x18000c02c`
- `0x18000c4dc`
- `0x18000c78c`
- `0x18000c93c`
- `0x18000cae0`
- `0x18000cc18`
- `0x18000cdcc`
- `0x18000cff4`
- `0x18000d650`
- `0x18000d870`
- `0x18000e578`
- `0x18000e750`
- `0x18000e7f8`
- `0x18000f510`
- `0x18000f850`
- `0x18000ff30`
- `0x1800104c4`
- `0x180010710`
- `0x180010b5c`
- `0x180010c90`
- `0x1800110c4`
- `0x18001140c`
- `0x1800114b4`
- `0x1800116c0`

## callees

- `0x18000a460`
- `0x18001aac0`

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
0x18001aac0  cmp     rcx, cs:__security_cookie
0x18001aac7  jnz     short ReportFailure
0x18001aac9  rol     rcx, 10h
0x18001aacd  test    cx, 0FFFFh
0x18001aad2  jnz     short RestoreRcx
0x18001aad4  retn
0x18001aad5  ror     rcx, 10h
0x18001aad9  jmp     __report_gsfailure
```
