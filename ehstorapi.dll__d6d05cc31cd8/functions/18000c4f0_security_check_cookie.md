# __security_check_cookie

- ea: `0x18000c4f0`
- end: `0x18000c50e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x180001f9c`
- `0x180002d68`
- `0x180003f64`
- `0x1800042f4`
- `0x180004380`
- `0x1800046b4`
- `0x180004a60`
- `0x18000521c`
- `0x180005960`
- `0x180005d50`
- `0x180006400`
- `0x18000664c`
- `0x180006a64`
- `0x180006af0`
- `0x180007090`
- `0x1800071c0`
- `0x180007290`
- `0x180007430`
- `0x180007840`
- `0x1800079d0`
- `0x180007f00`
- `0x1800082b0`
- `0x18000919c`
- `0x18000a728`
- `0x18000a9f8`
- `0x18000ab0c`
- `0x18000ac80`
- `0x18000ae30`
- `0x18000b524`
- `0x18000b7bc`
- `0x18000ba34`

## callees

- `0x1800018b0`
- `0x18000c4f0`

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
0x18000c4f0  cmp     rcx, cs:__security_cookie
0x18000c4f7  jnz     short ReportFailure
0x18000c4f9  rol     rcx, 10h
0x18000c4fd  test    cx, 0FFFFh
0x18000c502  jnz     short RestoreRcx
0x18000c504  retn
0x18000c505  ror     rcx, 10h
0x18000c509  jmp     __report_gsfailure
```
