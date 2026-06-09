# __security_check_cookie

- ea: `0x1800273b0`
- end: `0x1800273ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022c4`
- `0x1800023f8`
- `0x180002c14`
- `0x180002eb0`
- `0x180003d10`
- `0x180003e78`
- `0x180004098`
- `0x180004774`
- `0x180004a30`
- `0x180004c48`
- `0x180005980`
- `0x1800061b8`
- `0x1800063a0`
- `0x180006a38`
- `0x180007b40`
- `0x180008720`
- `0x180008bf0`
- `0x180008de0`
- `0x1800094f0`
- `0x18000be24`
- `0x18000c848`
- `0x18000e560`
- `0x18000e7e0`
- `0x1800100cc`
- `0x180011038`
- `0x1800112e8`
- `0x180011504`
- `0x180012854`
- `0x180012ae8`
- `0x180012b60`
- `0x180014890`
- `0x1800155cc`
- `0x180015db8`
- `0x1800160e4`
- `0x18001d208`
- `0x18001d410`
- `0x18001d774`
- `0x18001f180`
- `0x180021710`
- `0x180021a70`
- `0x180021bd0`
- `0x180021ed4`
- `0x180021fc4`
- `0x1800220b4`
- `0x1800230fc`
- `0x1800237c0`
- `0x180024c80`
- `0x180025fd0`
- `0x180026450`
- `0x18002678c`

## callees

- `0x180002090`
- `0x1800273b0`

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
0x1800273b0  cmp     rcx, cs:__security_cookie
0x1800273b7  jnz     short ReportFailure
0x1800273b9  rol     rcx, 10h
0x1800273bd  test    cx, 0FFFFh
0x1800273c2  jnz     short RestoreRcx
0x1800273c4  retn
0x1800273c5  ror     rcx, 10h
0x1800273c9  jmp     __report_gsfailure
```
