# __security_check_cookie

- ea: `0x180012830`
- end: `0x18001284e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002150`
- `0x180002400`
- `0x1800025e0`
- `0x18000341c`
- `0x180003a5c`
- `0x180006328`
- `0x180007b40`
- `0x180007d7c`
- `0x180008bc0`
- `0x18000a288`
- `0x18000bc44`
- `0x18000c350`
- `0x18000d874`
- `0x18000d998`
- `0x18000da60`
- `0x18000db58`
- `0x18000e090`
- `0x18000e6fc`
- `0x18000e828`
- `0x18000ea1c`
- `0x18000ee14`
- `0x18000f2b8`
- `0x18000f4dc`
- `0x18000f744`
- `0x18000f934`
- `0x18000fed8`
- `0x1800101e8`
- `0x1800108bc`
- `0x180010a3c`
- `0x180010fd0`
- `0x18001135c`
- `0x1800119e8`
- `0x180012154`
- `0x18001238c`
- `0x180012478`
- `0x18001269c`

## callees

- `0x180001940`
- `0x180012830`

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
0x180012830  cmp     rcx, cs:__security_cookie
0x180012837  jnz     short ReportFailure
0x180012839  rol     rcx, 10h
0x18001283d  test    cx, 0FFFFh
0x180012842  jnz     short RestoreRcx
0x180012844  retn
0x180012845  ror     rcx, 10h
0x180012849  jmp     __report_gsfailure
```
