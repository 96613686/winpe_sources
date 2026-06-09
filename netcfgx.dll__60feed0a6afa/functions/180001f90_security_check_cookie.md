# __security_check_cookie

- ea: `0x180001f90`
- end: `0x180001fae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001560`
- `0x18000366c`
- `0x18000498c`
- `0x180004d58`
- `0x180004ea8`
- `0x180005038`
- `0x18000521c`
- `0x180005b98`
- `0x180005d2c`
- `0x180006054`
- `0x180006ac4`
- `0x180006d30`
- `0x180006ecc`
- `0x1800070a8`
- `0x180007838`
- `0x180007a4c`
- `0x18000844c`
- `0x180008cc0`
- `0x180008fe8`
- `0x1800090b4`
- `0x1800099f0`
- `0x180009fd0`
- `0x18000a410`
- `0x18000a5dc`
- `0x18000a99c`
- `0x18000aa78`
- `0x18000ab50`
- `0x18000af5c`
- `0x18000b648`
- `0x18000bc54`
- `0x18000bef0`
- `0x18000c018`
- `0x18000c3fc`
- `0x18000c8ec`
- `0x18000cc94`
- `0x18000d1f4`
- `0x18000d614`
- `0x18000da34`
- `0x18000f814`
- `0x18000f9bc`
- `0x18000fb90`
- `0x18000ff0c`
- `0x180010490`
- `0x18001084c`
- `0x180010a00`
- `0x180011078`
- `0x180011270`
- `0x180011c38`

## callees

- `0x180001f90`
- `0x180002000`

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
0x180001f90  cmp     rcx, cs:__security_cookie
0x180001f97  jnz     short ReportFailure
0x180001f99  rol     rcx, 10h
0x180001f9d  test    cx, 0FFFFh
0x180001fa2  jnz     short RestoreRcx
0x180001fa4  retn
0x180001fa5  ror     rcx, 10h; StackCookie
0x180001fa9  jmp     __report_gsfailure
```
