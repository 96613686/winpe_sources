# __security_check_cookie

- ea: `0x140002600`
- end: `0x14000261e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010b0`
- `0x140001364`
- `0x14000177c`
- `0x140001d50`
- `0x140001fd0`
- `0x140002954`
- `0x140003af8`
- `0x140004158`
- `0x140004404`
- `0x140005738`
- `0x140005b08`
- `0x140006434`
- `0x1400070c4`
- `0x1400074e4`
- `0x140007acc`
- `0x140008348`
- `0x140008740`
- `0x14000905c`
- `0x14000a6cc`
- `0x14000afac`
- `0x14000bc10`
- `0x14000bd38`
- `0x14000cd88`
- `0x14000d064`
- `0x14000d2a4`
- `0x14000ebec`
- `0x14000f0f0`
- `0x140010e84`
- `0x1400111bc`
- `0x140011344`
- `0x140011688`
- `0x140011758`
- `0x140011bb0`
- `0x1400122f0`
- `0x140012754`
- `0x1400128fc`
- `0x140012ae0`

## callees

- `0x140002600`
- `0x140002920`

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
0x140002600  cmp     rcx, cs:__security_cookie
0x140002607  jnz     short loc_140002619
0x140002609  rol     rcx, 10h
0x14000260d  test    cx, 0FFFFh
0x140002612  jnz     short loc_140002615
0x140002614  retn
0x140002615  ror     rcx, 10h; StackCookie
0x140002619  jmp     __report_gsfailure
```
