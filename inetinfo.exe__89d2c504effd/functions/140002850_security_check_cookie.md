# __security_check_cookie

- ea: `0x140002850`
- end: `0x14000286e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001808`
- `0x14000193c`
- `0x140001b40`
- `0x140001f54`
- `0x140002210`
- `0x1400024d0`
- `0x1400027bc`

## callees

- `0x140001660`
- `0x140002850`

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
0x140002850  cmp     rcx, cs:__security_cookie
0x140002857  jnz     short loc_140002869
0x140002859  rol     rcx, 10h
0x14000285d  test    cx, 0FFFFh
0x140002862  jnz     short loc_140002865
0x140002864  retn
0x140002865  ror     rcx, 10h
0x140002869  jmp     __report_gsfailure
```
