# __security_check_cookie

- ea: `0x180024ef0`
- end: `0x180024f0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cb0`
- `0x180006070`
- `0x180006b60`
- `0x180007de4`
- `0x18000860c`
- `0x180008810`
- `0x180008b80`
- `0x180009190`
- `0x1800091e0`
- `0x18000c1c0`
- `0x18000cc40`
- `0x18000d6cc`
- `0x18000da9c`
- `0x18000f2d0`
- `0x18000fc08`
- `0x1800105e0`
- `0x180011630`
- `0x180011a40`
- `0x180012a7c`
- `0x180012fa4`
- `0x180014c18`
- `0x18001681c`
- `0x180016df0`
- `0x1800173e4`
- `0x180017bf8`
- `0x180018a48`
- `0x1800191f8`
- `0x180019b08`
- `0x18001c26c`
- `0x18001c764`
- `0x18001c878`
- `0x18001c9a0`
- `0x18001d8e8`
- `0x18001e5c0`
- `0x18001edb0`
- `0x18001f5cc`
- `0x18001fb58`
- `0x18001fd90`
- `0x180020248`
- `0x18002032c`
- `0x180020d10`
- `0x180021170`
- `0x180021464`
- `0x180021778`
- `0x180022420`
- `0x180023e34`
- `0x180024190`
- `0x1800244f0`
- `0x180024650`
- `0x180024a3c`

## callees

- `0x1800142e0`
- `0x180024ef0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180024ef0  cmp     rcx, cs:__security_cookie
0x180024ef7  jnz     short loc_180024F09
0x180024ef9  rol     rcx, 10h
0x180024efd  test    cx, 0FFFFh
0x180024f02  jnz     short loc_180024F05
0x180024f04  retn
0x180024f05  ror     rcx, 10h
0x180024f09  jmp     __report_gsfailure
```
