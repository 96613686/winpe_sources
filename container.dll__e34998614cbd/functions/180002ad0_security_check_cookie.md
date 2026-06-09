# __security_check_cookie

- ea: `0x180002ad0`
- end: `0x180002aee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `153`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x18000134c`
- `0x180001660`
- `0x1800016f0`
- `0x1800017ec`
- `0x180001a90`
- `0x180001eb4`
- `0x180001f4c`
- `0x18000202c`
- `0x180002148`
- `0x18000223c`
- `0x180002fa4`
- `0x180004618`
- `0x1800048d8`
- `0x180004af4`
- `0x180005344`
- `0x180005c6c`
- `0x180006018`
- `0x1800065d8`
- `0x180006e98`
- `0x1800070f4`
- `0x18000753c`
- `0x180007674`
- `0x180007c98`
- `0x180008ce4`
- `0x1800095dc`
- `0x180009a58`
- `0x18000b4dc`
- `0x18000c180`
- `0x18000c2bc`
- `0x18000c69c`
- `0x18000c7e4`
- `0x18000cf0c`
- `0x18000d134`
- `0x18000d710`
- `0x18000d8f0`
- `0x18000da40`
- `0x18000db40`
- `0x18000dda0`
- `0x18000de10`
- `0x18000df80`
- `0x18000e010`
- `0x18000e0b0`
- `0x18000e140`
- `0x18000e5a0`
- `0x18000f21c`
- `0x18000f560`
- `0x18000f620`
- `0x18000f6e0`

## callees

- `0x180002ad0`
- `0x180002f60`

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
0x180002ad0  cmp     rcx, cs:__security_cookie
0x180002ad7  jnz     short ReportFailure
0x180002ad9  rol     rcx, 10h
0x180002add  test    cx, 0FFFFh
0x180002ae2  jnz     short RestoreRcx
0x180002ae4  retn
0x180002ae5  ror     rcx, 10h; StackCookie
0x180002ae9  jmp     __report_gsfailure
```
