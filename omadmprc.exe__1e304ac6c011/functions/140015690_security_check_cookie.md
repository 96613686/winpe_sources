# __security_check_cookie

- ea: `0x140015690`
- end: `0x1400156ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `60`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001134`
- `0x140001314`
- `0x1400014a4`
- `0x1400015dc`
- `0x1400016e8`
- `0x1400017e8`
- `0x14000330c`
- `0x1400035b4`
- `0x1400042a4`
- `0x140004680`
- `0x140004a88`
- `0x140005604`
- `0x1400059a0`
- `0x140006b24`
- `0x140006f7c`
- `0x140007088`
- `0x140007a24`
- `0x14000942c`
- `0x14000a760`
- `0x14000a87c`
- `0x14000abe0`
- `0x14000b0ac`
- `0x14000b860`
- `0x14000beb8`
- `0x14000c4ac`
- `0x14000c718`
- `0x14000c9a4`
- `0x14000cbf8`
- `0x14000cddc`
- `0x14000ce84`
- `0x14000cf44`
- `0x14000d024`
- `0x14000d108`
- `0x14000d238`
- `0x14000d380`
- `0x14000d4e8`
- `0x14000d868`
- `0x14000d908`
- `0x14000da8c`
- `0x14000dc4c`
- `0x14000debc`
- `0x14000e3e4`
- `0x14000f13c`
- `0x14000f2b8`
- `0x14000f76c`
- `0x14000fc54`
- `0x14000fff0`
- `0x1400107ec`
- `0x140010f44`
- `0x140011ac8`

## callees

- `0x140002770`
- `0x140015690`

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
0x140015690  cmp     rcx, cs:__security_cookie
0x140015697  jnz     short loc_1400156A9
0x140015699  rol     rcx, 10h
0x14001569d  test    cx, 0FFFFh
0x1400156a2  jnz     short loc_1400156A5
0x1400156a4  retn
0x1400156a5  ror     rcx, 10h
0x1400156a9  jmp     __report_gsfailure
```
