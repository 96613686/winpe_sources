# SslpValidateHybridGroup

- ea: `0x18002392c`
- end: `0x180023966`
- name: `SslpValidateHybridGroup`
- size: `58`
- prototype: `__int64 __fastcall(__int16)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023314`
- `0x1800237a0`
- `0x18002396c`

## callees

- `0x18000b654`
- `0x1800233a8`
- `0x18002392c`

## string_xrefs

- `0x180023940`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpValidateHybridGroup(__int16 a1)
{
  if ( SslpGetHybridKeyGroup(a1) )
    return 0;
  DebugTraceError(
    2148073511LL,
    "NTE_INVALID_PARAMETER",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
    131);
  return 2148073511LL;
}

```

## disassembly

```asm
0x18002392c  sub     rsp, 28h
0x180023930  call    SslpGetHybridKeyGroup
0x180023935  test    rax, rax
0x180023938  jnz     short loc_18002395F
0x18002393a  mov     r9d, 83h
0x180023940  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023947  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18002394e  mov     ecx, 80090027h
0x180023953  call    DebugTraceError
0x180023958  mov     eax, 80090027h
0x18002395d  jmp     short loc_180023961
0x18002395f  xor     eax, eax
0x180023961  add     rsp, 28h
0x180023965  retn
```
