# __security_check_cookie

- ea: `0x180001f60`
- end: `0x180001f7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x18000328c`
- `0x180003528`
- `0x180003aa8`
- `0x180004428`
- `0x1800047cc`
- `0x180004b9c`
- `0x1800057b4`
- `0x180005b30`
- `0x180006c6c`
- `0x180006d78`
- `0x18000778c`
- `0x18000919c`
- `0x180009c80`
- `0x180009da8`
- `0x18000a078`
- `0x18000a380`
- `0x18000ac8c`
- `0x18000bc60`
- `0x18000c1a8`
- `0x18000c2a0`
- `0x18000cf50`
- `0x18000d0f8`
- `0x18000dfb0`
- `0x18000ee60`
- `0x18000f184`
- `0x18000f2c8`
- `0x18000f57c`
- `0x18000f77c`
- `0x180010520`
- `0x18001064c`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x180013aac`
- `0x180013ba0`
- `0x1800142dc`
- `0x1800147b4`
- `0x1800148c4`
- `0x180014d40`

## callees

- `0x180001f60`
- `0x180002520`

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
0x180001f60  cmp     rcx, cs:__security_cookie
0x180001f67  jnz     short ReportFailure
0x180001f69  rol     rcx, 10h
0x180001f6d  test    cx, 0FFFFh
0x180001f72  jnz     short RestoreRcx
0x180001f74  retn
0x180001f75  ror     rcx, 10h; StackCookie
0x180001f79  jmp     __report_gsfailure
```
