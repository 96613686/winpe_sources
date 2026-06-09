# __security_check_cookie

- ea: `0x180002490`
- end: `0x1800024ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `102`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015d0`
- `0x180001660`
- `0x180001904`
- `0x180001bfc`
- `0x1800042e4`
- `0x180004590`
- `0x180004b38`
- `0x180004f08`
- `0x180005534`
- `0x180005954`
- `0x18000730c`
- `0x180007890`
- `0x180007d88`
- `0x180008350`
- `0x1800083a8`
- `0x180008da4`
- `0x1800095cc`
- `0x18000b140`
- `0x18000b24c`
- `0x18000bbf8`
- `0x18000d09c`
- `0x18000fd6c`
- `0x18000ffb0`
- `0x1800101c0`
- `0x1800102f0`
- `0x180010470`
- `0x180010600`
- `0x1800107e0`
- `0x180010a00`
- `0x180010bd0`
- `0x180010db0`
- `0x180011030`
- `0x180011230`
- `0x1800113b0`
- `0x180011540`
- `0x180011770`
- `0x180011940`
- `0x180011b10`
- `0x180011dd0`
- `0x180011f20`
- `0x180012210`
- `0x180012388`
- `0x180012910`
- `0x180012b38`
- `0x180012cec`
- `0x1800134bc`
- `0x180013578`
- `0x1800169ac`

## callees

- `0x180002490`
- `0x180002ac0`

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
0x180002490  cmp     rcx, cs:__security_cookie
0x180002497  jnz     short ReportFailure
0x180002499  rol     rcx, 10h
0x18000249d  test    cx, 0FFFFh
0x1800024a2  jnz     short RestoreRcx
0x1800024a4  retn
0x1800024a5  ror     rcx, 10h; StackCookie
0x1800024a9  jmp     __report_gsfailure
```
