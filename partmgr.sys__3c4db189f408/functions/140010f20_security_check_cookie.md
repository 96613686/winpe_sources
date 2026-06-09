# __security_check_cookie

- ea: `0x140010f20`
- end: `0x140010f3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010ac`
- `0x140001160`
- `0x14000191c`
- `0x140003674`
- `0x140003734`
- `0x1400037bc`
- `0x140004190`
- `0x140004260`
- `0x140004d20`
- `0x1400051c0`
- `0x140005d78`
- `0x140006300`
- `0x1400066a0`
- `0x140009880`
- `0x14000a3d0`
- `0x14000ada0`
- `0x14000b490`
- `0x14000c14c`
- `0x14000c1b8`
- `0x14000c238`
- `0x14000c2a0`
- `0x14000cb34`
- `0x14000cc88`
- `0x14000d180`
- `0x14000d634`
- `0x14000df90`
- `0x14000e5b0`
- `0x14000e6f0`
- `0x14000ea44`
- `0x14000f6e0`
- `0x14000fbd4`
- `0x14000fc84`
- `0x140010ddc`
- `0x14001c3d8`
- `0x14001ca0c`
- `0x14001ced4`
- `0x14001cf74`
- `0x14001cff4`
- `0x14001d090`
- `0x14001e468`
- `0x14001e6f0`
- `0x14001f014`
- `0x14001fb44`
- `0x140020050`
- `0x1400200e0`
- `0x14002046c`
- `0x1400210a8`
- `0x140021738`
- `0x140021b3c`

## callees

- `0x14000a930`
- `0x140010f20`

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
0x140010f20  cmp     rcx, cs:__security_cookie
0x140010f27  jnz     short ReportFailure
0x140010f29  rol     rcx, 10h
0x140010f2d  test    cx, 0FFFFh
0x140010f32  jnz     short RestoreRcx
0x140010f34  retn
0x140010f35  ror     rcx, 10h; StackCookie
0x140010f39  jmp     __report_gsfailure
```
