# __security_check_cookie

- ea: `0x140075de0`
- end: `0x140075dfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `145`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400042a4`
- `0x140004d00`
- `0x1400069e8`
- `0x140007104`
- `0x140007f98`
- `0x140009c4c`
- `0x14000a150`
- `0x14000c1f0`
- `0x14000c29c`
- `0x1400157d4`
- `0x140015cdc`
- `0x140015d80`
- `0x140021400`
- `0x14002859c`
- `0x140029ba4`
- `0x14002df68`
- `0x14002ff50`
- `0x140030be0`
- `0x140033950`
- `0x1400342b4`
- `0x140034360`
- `0x140034ef8`
- `0x140037640`
- `0x140037bb8`
- `0x140038730`
- `0x140039994`
- `0x14003a958`
- `0x14003bff8`
- `0x14003efa4`
- `0x14003f458`
- `0x14003fc1c`
- `0x14004005c`
- `0x140040440`
- `0x1400404dc`
- `0x140040830`
- `0x140047aa8`
- `0x140048348`
- `0x140048a18`
- `0x140049f44`
- `0x14004af34`
- `0x14004c0f0`
- `0x14004e708`
- `0x14004eeac`
- `0x14004f034`
- `0x14004f30c`
- `0x14004f960`
- `0x14004fab4`
- `0x14004fbd8`
- `0x140050144`

## callees

- `0x140075de0`
- `0x140076360`

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
0x140075de0  cmp     rcx, cs:__security_cookie
0x140075de7  jnz     short loc_140075DF9
0x140075de9  rol     rcx, 10h
0x140075ded  test    cx, 0FFFFh
0x140075df2  jnz     short loc_140075DF5
0x140075df4  retn
0x140075df5  ror     rcx, 10h; StackCookie
0x140075df9  jmp     __report_gsfailure
```
