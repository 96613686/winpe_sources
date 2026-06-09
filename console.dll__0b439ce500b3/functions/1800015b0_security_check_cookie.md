# __security_check_cookie

- ea: `0x1800015b0`
- end: `0x1800015ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800034c4`
- `0x180003784`
- `0x180003d7c`
- `0x180004008`
- `0x1800043c4`
- `0x180004798`
- `0x180006038`
- `0x180006530`
- `0x180006e74`
- `0x180007240`
- `0x180007488`
- `0x18000752c`
- `0x18000788c`
- `0x180007e0c`
- `0x180008d68`
- `0x180008f50`
- `0x180009264`
- `0x180009578`
- `0x180009980`
- `0x18000a5f0`
- `0x18000a87c`
- `0x18000a9d0`
- `0x18000ac68`
- `0x18000b020`
- `0x18000c440`
- `0x18000ca48`
- `0x18000ccb0`
- `0x18000cd98`
- `0x18000e94c`
- `0x18000f4b0`
- `0x18000fa40`
- `0x18000fbdc`
- `0x180010470`
- `0x180010680`
- `0x18001076c`
- `0x1800110b0`
- `0x1800112c4`
- `0x1800114d4`
- `0x180011f44`
- `0x180012894`
- `0x180012ab4`
- `0x180012b4c`
- `0x1800133c0`
- `0x1800137e0`
- `0x180013e00`
- `0x1800143f8`
- `0x180015880`
- `0x180016c14`
- `0x180017368`
- `0x1800180bc`

## callees

- `0x1800015b0`
- `0x180001c10`

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
0x1800015b0  cmp     rcx, cs:__security_cookie
0x1800015b7  jnz     short ReportFailure
0x1800015b9  rol     rcx, 10h
0x1800015bd  test    cx, 0FFFFh
0x1800015c2  jnz     short RestoreRcx
0x1800015c4  retn
0x1800015c5  ror     rcx, 10h; StackCookie
0x1800015c9  jmp     __report_gsfailure
```
