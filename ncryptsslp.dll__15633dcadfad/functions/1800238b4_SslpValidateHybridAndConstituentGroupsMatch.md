# SslpValidateHybridAndConstituentGroupsMatch

- ea: `0x1800238b4`
- end: `0x180023923`
- name: `SslpValidateHybridAndConstituentGroupsMatch`
- size: `111`
- prototype: `__int64 __fastcall(__int16, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022ca4`
- `0x1800237a0`
- `0x18002396c`

## callees

- `0x18000b654`
- `0x1800233a8`
- `0x1800238b4`

## string_xrefs

- `0x180023901`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpValidateHybridAndConstituentGroupsMatch(__int16 a1, __int64 a2, __int64 a3)
{
  __int64 *HybridKeyGroup; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r9

  if ( a2 && a3 )
  {
    HybridKeyGroup = SslpGetHybridKeyGroup(a1);
    if ( HybridKeyGroup )
    {
      if ( *(_DWORD *)(v5 + 32) == *((unsigned __int16 *)HybridKeyGroup + 2)
        && *(_WORD *)(v4 + 44) == *((_WORD *)HybridKeyGroup + 12) )
      {
        return 0;
      }
      v6 = 239;
    }
    else
    {
      v6 = 232;
    }
  }
  else
  {
    v6 = 225;
  }
  DebugTraceError(
    2148073511LL,
    "NTE_INVALID_PARAMETER",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
    v6);
  return 2148073511LL;
}

```

## disassembly

```asm
0x1800238b4  sub     rsp, 28h
0x1800238b8  mov     r9, rdx
0x1800238bb  test    rdx, rdx
0x1800238be  jz      short loc_1800238FB
0x1800238c0  test    r8, r8
0x1800238c3  jz      short loc_1800238FB
0x1800238c5  call    SslpGetHybridKeyGroup
0x1800238ca  mov     rcx, rax
0x1800238cd  test    rax, rax
0x1800238d0  jnz     short loc_1800238DA
0x1800238d2  mov     r9d, 0E8h
0x1800238d8  jmp     short loc_180023901
0x1800238da  movzx   eax, word ptr [rax+4]
0x1800238de  cmp     [r9+20h], eax
0x1800238e2  jnz     short loc_1800238F3
0x1800238e4  movzx   eax, word ptr [rcx+18h]
0x1800238e8  cmp     [r8+2Ch], ax
0x1800238ed  jnz     short loc_1800238F3
0x1800238ef  xor     eax, eax
0x1800238f1  jmp     short loc_18002391E
0x1800238f3  mov     r9d, 0EFh
0x1800238f9  jmp     short loc_180023901
0x1800238fb  mov     r9d, 0E1h
0x180023901  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023908  mov     ecx, 80090027h
0x18002390d  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180023914  call    DebugTraceError
0x180023919  mov     eax, 80090027h
0x18002391e  add     rsp, 28h
0x180023922  retn
```
