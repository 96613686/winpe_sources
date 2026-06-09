# __security_check_cookie

- ea: `0x180009fb0`
- end: `0x180009fce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001830`
- `0x180001e88`
- `0x180006694`
- `0x180007360`
- `0x180007500`
- `0x180007694`
- `0x180007888`
- `0x180007d30`
- `0x1800080c8`
- `0x1800082a8`
- `0x180008474`
- `0x180008ab8`
- `0x180008dd8`
- `0x180009090`
- `0x18000cce4`
- `0x18000dc30`
- `0x18000e9d4`
- `0x18000ed8c`
- `0x18000fbb4`
- `0x180010374`
- `0x180010a00`
- `0x180011020`
- `0x180011274`
- `0x1800122d4`
- `0x180012a70`
- `0x180012b74`
- `0x180013214`
- `0x1800149dc`
- `0x1800152c4`
- `0x180015428`
- `0x18001585c`
- `0x180015b84`
- `0x180016200`
- `0x180016914`
- `0x180017040`
- `0x180018ad4`

## callees

- `0x180009fb0`
- `0x180009fe0`

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
0x180009fb0  cmp     rcx, cs:__security_cookie
0x180009fb7  jnz     short ReportFailure
0x180009fb9  rol     rcx, 10h
0x180009fbd  test    cx, 0FFFFh
0x180009fc2  jnz     short RestoreRcx
0x180009fc4  retn
0x180009fc5  ror     rcx, 10h; StackCookie
0x180009fc9  jmp     __report_gsfailure
```
