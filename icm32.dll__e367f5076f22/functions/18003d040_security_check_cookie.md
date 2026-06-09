# __security_check_cookie

- ea: `0x18003d040`
- end: `0x18003d05e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a64`
- `0x180001c0c`
- `0x1800023c8`
- `0x1800029a4`
- `0x1800053d0`
- `0x180005838`
- `0x180005974`
- `0x180005c70`
- `0x1800061dc`
- `0x180006af0`
- `0x180007418`
- `0x1800079d4`
- `0x180007ddc`
- `0x180007fe0`
- `0x180008480`
- `0x18000aa10`
- `0x18000e724`
- `0x18000ee40`
- `0x180013090`
- `0x180014d50`
- `0x1800178f8`
- `0x180017cf4`
- `0x180018288`
- `0x180019b00`
- `0x180019f50`
- `0x18001a7d0`
- `0x18001a958`
- `0x18001c308`
- `0x18001d7a0`
- `0x18001de14`
- `0x18001e1ec`
- `0x18001e97c`
- `0x18001edd4`
- `0x18001fc68`
- `0x180020380`
- `0x180020828`
- `0x180020ae4`
- `0x180020c14`
- `0x18002167c`
- `0x180021964`
- `0x18003cb08`
- `0x18003ce38`
- `0x18003cf80`

## callees

- `0x18001d2a0`
- `0x18003d040`

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
0x18003d040  cmp     rcx, cs:__security_cookie
0x18003d047  jnz     short ReportFailure
0x18003d049  rol     rcx, 10h
0x18003d04d  test    cx, 0FFFFh
0x18003d052  jnz     short RestoreRcx
0x18003d054  retn
0x18003d055  ror     rcx, 10h
0x18003d059  jmp     __report_gsfailure
```
