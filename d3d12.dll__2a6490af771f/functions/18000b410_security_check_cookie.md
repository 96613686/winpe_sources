# __security_check_cookie

- ea: `0x18000b410`
- end: `0x18000b42e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800014c0`
- `0x180001a60`
- `0x180003390`
- `0x1800035c4`
- `0x180004c8c`
- `0x1800051f4`
- `0x1800052ac`
- `0x180005644`
- `0x180005894`
- `0x180006228`
- `0x18000670c`
- `0x1800071bc`
- `0x18000750c`
- `0x180007cfc`
- `0x180007f78`
- `0x1800098fc`
- `0x180009c34`
- `0x180009ddc`
- `0x18000a498`
- `0x18000ae80`
- `0x18000c090`
- `0x18000c2c0`
- `0x18000c9c8`
- `0x18000cd34`
- `0x18000d1f4`
- `0x18000e1a0`
- `0x18000e350`
- `0x18000f9e4`
- `0x18000fedc`
- `0x180010ae0`
- `0x180010ce8`
- `0x1800111b8`
- `0x18001153c`
- `0x180011648`
- `0x180011ba0`
- `0x180011c48`
- `0x180012c80`
- `0x1800136c4`
- `0x180013750`
- `0x180013908`

## callees

- `0x18000b410`
- `0x18000ba20`

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
0x18000b410  cmp     rcx, cs:__security_cookie
0x18000b417  jnz     short ReportFailure
0x18000b419  rol     rcx, 10h
0x18000b41d  test    cx, 0FFFFh
0x18000b422  jnz     short RestoreRcx
0x18000b424  retn
0x18000b425  ror     rcx, 10h; StackCookie
0x18000b429  jmp     __report_gsfailure
```
