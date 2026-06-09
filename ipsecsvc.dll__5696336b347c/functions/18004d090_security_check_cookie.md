# __security_check_cookie

- ea: `0x18004d090`
- end: `0x18004d0ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `60`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e20`
- `0x180003de0`
- `0x1800080e0`
- `0x180009438`
- `0x180009d44`
- `0x180009eb8`
- `0x18000abf0`
- `0x18000e078`
- `0x18000e1f8`
- `0x18000e2c0`
- `0x18000e3b8`
- `0x18000f0d8`
- `0x18000f1a4`
- `0x18000ff90`
- `0x180010660`
- `0x180012b20`
- `0x180013880`
- `0x180013ea0`
- `0x180014510`
- `0x1800148a0`
- `0x1800151f0`
- `0x1800155d0`
- `0x180015c10`
- `0x180016918`
- `0x180016ae0`
- `0x180018a94`
- `0x18001a860`
- `0x18001bcb4`
- `0x18001d020`
- `0x18001d89c`
- `0x18001fcb0`
- `0x180021f80`
- `0x180022cac`
- `0x180024528`
- `0x1800259f0`
- `0x1800277f8`
- `0x1800281dc`
- `0x180028884`
- `0x180028cd8`
- `0x18002912c`
- `0x1800298f8`
- `0x180029e00`
- `0x18002ebb8`
- `0x18002f7a4`
- `0x18002f984`
- `0x18002fab4`
- `0x1800300b4`
- `0x180031ad0`
- `0x180035240`
- `0x1800353e4`

## callees

- `0x18000d530`
- `0x18004d090`

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
0x18004d090  cmp     rcx, cs:__security_cookie
0x18004d097  jnz     short ReportFailure
0x18004d099  rol     rcx, 10h
0x18004d09d  test    cx, 0FFFFh
0x18004d0a2  jnz     short RestoreRcx
0x18004d0a4  retn
0x18004d0a5  ror     rcx, 10h
0x18004d0a9  jmp     __report_gsfailure
```
