# __security_check_cookie

- ea: `0x1800222d0`
- end: `0x1800222ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `104`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004010`
- `0x180004080`
- `0x180004814`
- `0x180004b7c`
- `0x1800056c0`
- `0x180006040`
- `0x18000728c`
- `0x180007724`
- `0x180007a08`
- `0x180007bd8`
- `0x180007f70`
- `0x18000839c`
- `0x1800087bc`
- `0x180008be0`
- `0x1800092cc`
- `0x1800098e0`
- `0x180009a24`
- `0x180009dcc`
- `0x180009ec8`
- `0x18000a014`
- `0x18000a32c`
- `0x18000a61c`
- `0x18000aa10`
- `0x18000aac0`
- `0x18000af00`
- `0x18000b2d0`
- `0x18000b6b8`
- `0x18000c8b8`
- `0x18000cca8`
- `0x18000d078`
- `0x18000d444`
- `0x18000d814`
- `0x18000dfdc`
- `0x18000e208`
- `0x18000e664`
- `0x18000e824`
- `0x18000e908`
- `0x18000eb2c`
- `0x18000f09c`
- `0x18000f8f4`
- `0x180010948`
- `0x180010b0c`
- `0x180010bc8`
- `0x180010c48`
- `0x180010e8c`
- `0x180011020`
- `0x1800113f0`
- `0x180011bc0`
- `0x180011dd0`
- `0x1800121ac`

## callees

- `0x1800031f0`
- `0x1800222d0`

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
0x1800222d0  cmp     rcx, cs:__security_cookie
0x1800222d7  jnz     short ReportFailure
0x1800222d9  rol     rcx, 10h
0x1800222dd  test    cx, 0FFFFh
0x1800222e2  jnz     short RestoreRcx
0x1800222e4  retn
0x1800222e5  ror     rcx, 10h
0x1800222e9  jmp     __report_gsfailure
```
