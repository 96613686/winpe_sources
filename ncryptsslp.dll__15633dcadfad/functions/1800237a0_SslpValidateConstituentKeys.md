# SslpValidateConstituentKeys

- ea: `0x1800237a0`
- end: `0x1800238ac`
- name: `SslpValidateConstituentKeys`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014024`
- `0x1800229a4`
- `0x180023234`

## callees

- `0x1800066f0`
- `0x18000b654`
- `0x1800237a0`
- `0x1800238b4`
- `0x18002392c`
- `0x180023a78`

## string_xrefs

- `0x1800237e4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023847`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023884`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpValidateConstituentKeys(__int64 a1, __int64 *a2, __int64 *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // r9

  if ( !a1 || !a2 || !a3 )
  {
    v12 = 259;
    goto LABEL_16;
  }
  v6 = SslpValidateHybridGroup(*(unsigned __int16 *)(a1 + 8));
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 266);
    return v7;
  }
  if ( !*(_QWORD *)(a1 + 16) || !*(_QWORD *)(a1 + 32) )
  {
    v12 = 274;
    goto LABEL_16;
  }
  v9 = SslpValidateEphemeralHandle();
  v10 = SslpValidateKemKeyHandle(*(_QWORD *)(a1 + 32));
  v11 = v10;
  if ( !v9 || !v10 )
  {
    v12 = 283;
LABEL_16:
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v12);
    return 2148073511LL;
  }
  result = SslpValidateHybridAndConstituentGroupsMatch(*(unsigned __int16 *)(a1 + 8), v9, v10);
  if ( (int)result >= 0 )
  {
    *a2 = v9;
    *a3 = v11;
  }
  else
  {
    DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 291);
    return 2148073513LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800237a0  push    rbx
0x1800237a2  push    rbp
0x1800237a3  push    rsi
0x1800237a4  push    rdi
0x1800237a5  push    r14
0x1800237a7  sub     rsp, 20h
0x1800237ab  mov     rsi, r8
0x1800237ae  mov     r14, rdx
0x1800237b1  mov     rbx, rcx
0x1800237b4  test    rcx, rcx
0x1800237b7  jz      loc_18002387E
0x1800237bd  test    rdx, rdx
0x1800237c0  jz      loc_18002387E
0x1800237c6  test    r8, r8
0x1800237c9  jz      loc_18002387E
0x1800237cf  movzx   ecx, word ptr [rcx+8]
0x1800237d3  call    SslpValidateHybridGroup
0x1800237d8  mov     edi, eax
0x1800237da  test    eax, eax
0x1800237dc  jns     short loc_180023800
0x1800237de  mov     r9d, 10Ah
0x1800237e4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800237eb  lea     rdx, aStatus_0; "status"
0x1800237f2  mov     ecx, eax
0x1800237f4  call    DebugTraceError
0x1800237f9  mov     eax, edi
0x1800237fb  jmp     loc_1800238A1
0x180023800  mov     rcx, [rbx+10h]
0x180023804  test    rcx, rcx
0x180023807  jz      short loc_180023876
0x180023809  cmp     qword ptr [rbx+20h], 0
0x18002380e  jz      short loc_180023876
0x180023810  call    SslpValidateEphemeralHandle
0x180023815  mov     rcx, [rbx+20h]
0x180023819  mov     rbp, rax
0x18002381c  call    SslpValidateKemKeyHandle
0x180023821  mov     rdi, rax
0x180023824  test    rbp, rbp
0x180023827  jz      short loc_18002386E
0x180023829  test    rax, rax
0x18002382c  jz      short loc_18002386E
0x18002382e  movzx   ecx, word ptr [rbx+8]
0x180023832  mov     r8, rax
0x180023835  mov     rdx, rbp
0x180023838  call    SslpValidateHybridAndConstituentGroupsMatch
0x18002383d  test    eax, eax
0x18002383f  jns     short loc_180023866
0x180023841  mov     r9d, 123h
0x180023847  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002384e  lea     rdx, aStatus_0; "status"
0x180023855  mov     ecx, 80090029h
0x18002385a  call    DebugTraceError
0x18002385f  mov     eax, 80090029h
0x180023864  jmp     short loc_1800238A1
0x180023866  mov     [r14], rbp
0x180023869  mov     [rsi], rdi
0x18002386c  jmp     short loc_1800238A1
0x18002386e  mov     r9d, 11Bh
0x180023874  jmp     short loc_180023884
0x180023876  mov     r9d, 112h
0x18002387c  jmp     short loc_180023884
0x18002387e  mov     r9d, 103h
0x180023884  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002388b  mov     ecx, 80090027h
0x180023890  lea     rdx, aStatus_0; "status"
0x180023897  call    DebugTraceError
0x18002389c  mov     eax, 80090027h
0x1800238a1  add     rsp, 20h
0x1800238a5  pop     r14
0x1800238a7  pop     rdi
0x1800238a8  pop     rsi
0x1800238a9  pop     rbp
0x1800238aa  pop     rbx
0x1800238ab  retn
```
