# __security_check_cookie

- ea: `0x14000bfa0`
- end: `0x14000bfbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001828`
- `0x1400023b0`
- `0x140002f34`
- `0x1400049a0`
- `0x140005280`
- `0x140005d74`
- `0x140006f1c`
- `0x14000975c`
- `0x140009834`
- `0x1400098f4`
- `0x1400099dc`
- `0x140009a94`
- `0x140009b84`
- `0x140009c38`
- `0x140009cf8`
- `0x140009df0`
- `0x140009ec0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000a154`
- `0x14000a234`
- `0x14000a2c8`
- `0x14000a5d8`
- `0x14000b8a0`
- `0x14000be6c`
- `0x140018130`
- `0x140018350`
- `0x140018e20`
- `0x140019110`
- `0x140019838`
- `0x14001ac90`
- `0x14001ae50`
- `0x14001b200`
- `0x14001b3c0`
- `0x14001b98c`
- `0x14001bd20`
- `0x14001cf60`
- `0x14001d60c`
- `0x14001e1c0`
- `0x14001e5ac`
- `0x140020b80`
- `0x140021550`
- `0x140023b40`
- `0x140024640`
- `0x140024a60`
- `0x140024c3c`
- `0x140025280`
- `0x1400256b0`
- `0x140025b20`
- `0x140026080`

## callees

- `0x1400010c0`
- `0x14000bfa0`

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
0x14000bfa0  cmp     rcx, cs:__security_cookie
0x14000bfa7  jnz     short ReportFailure
0x14000bfa9  rol     rcx, 10h
0x14000bfad  test    cx, 0FFFFh
0x14000bfb2  jnz     short RestoreRcx
0x14000bfb4  retn
0x14000bfb5  ror     rcx, 10h; StackCookie
0x14000bfb9  jmp     __report_gsfailure
```
