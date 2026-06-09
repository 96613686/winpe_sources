# __security_check_cookie

- ea: `0x1800015d0`
- end: `0x1800015ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `44`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800025f8`
- `0x180002894`
- `0x180003114`
- `0x1800034b8`
- `0x1800038a4`
- `0x1800044c4`
- `0x18000483c`
- `0x1800057a0`
- `0x1800060b4`
- `0x180007048`
- `0x180007994`
- `0x1800080f0`
- `0x18000828c`
- `0x180008450`
- `0x1800085b0`
- `0x180008710`
- `0x180008bc0`
- `0x180008e90`
- `0x1800092c0`
- `0x180009844`
- `0x1800099e0`
- `0x180009b20`
- `0x180009d30`
- `0x18000a310`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000ba54`
- `0x18000bbc4`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c494`
- `0x18000c5d8`
- `0x18000c810`
- `0x18000c8c4`
- `0x18000cae4`
- `0x18000cca0`
- `0x18000e4e8`
- `0x18000e9e4`
- `0x18000edc0`
- `0x18000eee0`
- `0x18000f330`
- `0x18000f8b8`

## callees

- `0x1800015d0`
- `0x180001b70`

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
0x1800015d0  cmp     rcx, cs:__security_cookie
0x1800015d7  jnz     short ReportFailure
0x1800015d9  rol     rcx, 10h
0x1800015dd  test    cx, 0FFFFh
0x1800015e2  jnz     short RestoreRcx
0x1800015e4  retn
0x1800015e5  ror     rcx, 10h; StackCookie
0x1800015e9  jmp     __report_gsfailure
```
