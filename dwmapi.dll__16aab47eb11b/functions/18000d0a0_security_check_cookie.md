# __security_check_cookie

- ea: `0x18000d0a0`
- end: `0x18000d0be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a10`
- `0x180001c10`
- `0x180002200`
- `0x180002920`
- `0x180002e90`
- `0x180003030`
- `0x180003380`
- `0x1800035f0`
- `0x18000387c`
- `0x180003a90`
- `0x180003bc0`
- `0x180004300`
- `0x180004610`
- `0x180005060`
- `0x1800052c0`
- `0x180005534`
- `0x180005788`
- `0x180005980`
- `0x180005b5c`
- `0x180005c64`
- `0x180005d14`
- `0x1800061c0`
- `0x180006c28`
- `0x180007310`
- `0x1800076c0`
- `0x1800077d0`
- `0x180007c50`
- `0x180008004`
- `0x1800080e0`
- `0x1800084b0`
- `0x180008ab4`
- `0x180008cc0`
- `0x180009098`
- `0x180009690`
- `0x180009890`
- `0x180009be0`
- `0x18000a060`
- `0x18000a320`
- `0x18000a3c0`
- `0x18000a650`
- `0x18000a8e0`
- `0x18000ab44`
- `0x18000b2e0`
- `0x18000b560`
- `0x18000bacc`
- `0x18000bd8c`
- `0x18000be7c`
- `0x18000bff4`
- `0x18000c2ec`
- `0x18000d7fc`

## callees

- `0x18000d0a0`
- `0x18000db00`

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
0x18000d0a0  cmp     rcx, cs:__security_cookie
0x18000d0a7  jnz     short loc_18000D0B9
0x18000d0a9  rol     rcx, 10h
0x18000d0ad  test    cx, 0FFFFh
0x18000d0b2  jnz     short loc_18000D0B5
0x18000d0b4  retn
0x18000d0b5  ror     rcx, 10h; StackCookie
0x18000d0b9  jmp     __report_gsfailure
```
