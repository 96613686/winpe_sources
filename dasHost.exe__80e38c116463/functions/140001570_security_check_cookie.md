# __security_check_cookie

- ea: `0x140001570`
- end: `0x14000158e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000290c`
- `0x140002bb8`
- `0x1400039d8`
- `0x140003da8`
- `0x1400041a0`
- `0x140004c14`
- `0x140004f90`
- `0x140005bc8`
- `0x1400064cc`
- `0x140007bac`
- `0x1400085e0`
- `0x140008708`
- `0x140008b5c`
- `0x140010dfc`
- `0x140010f4c`
- `0x140011080`
- `0x140011148`
- `0x140011cc8`
- `0x140011ea4`
- `0x14001211c`
- `0x1400124d0`
- `0x140012b58`
- `0x140012c08`
- `0x140014fd8`
- `0x140015a90`
- `0x1400167e4`
- `0x1400195e0`
- `0x14001a6e8`

## callees

- `0x140001570`
- `0x140001c10`

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
0x140001570  cmp     rcx, cs:__security_cookie
0x140001577  jnz     short loc_140001589
0x140001579  rol     rcx, 10h
0x14000157d  test    cx, 0FFFFh
0x140001582  jnz     short loc_140001585
0x140001584  retn
0x140001585  ror     rcx, 10h; StackCookie
0x140001589  jmp     __report_gsfailure
```
