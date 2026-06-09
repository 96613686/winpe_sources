# __security_check_cookie

- ea: `0x180024220`
- end: `0x18002423e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `118`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800145c8`
- `0x18001472c`
- `0x180014940`
- `0x180014990`
- `0x180014a38`
- `0x180014a9c`
- `0x180014b14`
- `0x180014bac`
- `0x180014c80`
- `0x180014d2c`
- `0x180014eec`
- `0x180014f4c`
- `0x180014fc4`
- `0x180015058`
- `0x1800150fc`
- `0x1800151b0`
- `0x180015520`
- `0x1800161d0`
- `0x180017440`
- `0x180017c80`
- `0x1800184a0`
- `0x18001af88`
- `0x18001bc38`
- `0x18001e460`
- `0x18001e7f0`
- `0x18001ef40`
- `0x18001fcb0`
- `0x1800206fc`
- `0x180020e4c`
- `0x180020fe0`
- `0x180023b84`
- `0x180026c60`
- `0x180026f90`
- `0x1800277a0`
- `0x180028400`
- `0x18002cf60`
- `0x18002d2a0`
- `0x18002daf0`
- `0x18002ef60`
- `0x18002f7b0`
- `0x180030040`
- `0x1800309b0`
- `0x1800323e0`
- `0x180032f90`
- `0x1800338c0`
- `0x180034e60`
- `0x180036980`
- `0x1800372a0`
- `0x180038470`
- `0x1800389a0`

## callees

- `0x180024220`
- `0x1800247b0`

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
0x180024220  cmp     rcx, cs:__security_cookie
0x180024227  jnz     short ReportFailure
0x180024229  rol     rcx, 10h
0x18002422d  test    cx, 0FFFFh
0x180024232  jnz     short RestoreRcx
0x180024234  retn
0x180024235  ror     rcx, 10h; StackCookie
0x180024239  jmp     __report_gsfailure
```
