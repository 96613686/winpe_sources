# MSCryptEccFinalizeKeyPair

- ea: `0x1800766a0`
- end: `0x1800767e7`
- name: `MSCryptEccFinalizeKeyPair`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180075a40`
- `0x180075e50`

## callees

- `0x18000743c`
- `0x18003caf8`
- `0x180046b98`
- `0x180047ce0`
- `0x1800766a0`
- `0x1800880a4`
- `0x180088490`

## string_xrefs

- `0x180076740`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800767b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccFinalizeKeyPair(__int64 a1, int a2, int a3)
{
  __int64 v3; // rbx
  int v4; // ebp
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v16 = 0;
  if ( !a1 || a2 && a2 != 24 )
  {
    LODWORD(v7) = -1073741811;
    v8 = 3221225485LL;
    v9 = 2788;
    goto LABEL_17;
  }
  v6 = ValidateEccKey(a1, a3, 0, 1, &v16);
  v3 = v16;
  LODWORD(v7) = v6;
  if ( v6 >= 0 )
  {
    if ( (*(_DWORD *)(v16 + 32) & 2) == 0 )
    {
      v10 = *(_QWORD *)(v16 + 16);
      if ( v10 )
      {
        if ( !*(_QWORD *)(v16 + 24) )
        {
          v11 = SymCryptEckeyAllocate(*(_QWORD *)(v10 + 8));
          *(_QWORD *)(v3 + 24) = v11;
          if ( !v11 )
          {
            LODWORD(v7) = -1073741801;
            v12 = 2812;
            v13 = 3221225495LL;
LABEL_11:
            DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
            return (unsigned int)v7;
          }
          v14 = SymCryptEckeySetRandom(a3 != 0 ? 4096 : 0x2000, v11);
          if ( v14 )
          {
            v4 = 1;
            v7 = (unsigned int)SymcryptErrorCodeToNtStatus(v14);
            v8 = v7;
            v9 = 2824;
            goto LABEL_17;
          }
        }
        *(_DWORD *)(v3 + 32) |= 2u;
        LODWORD(v7) = 0;
        return (unsigned int)v7;
      }
    }
    LODWORD(v7) = -1073741816;
    v12 = 2802;
    v13 = 3221225480LL;
    goto LABEL_11;
  }
  v8 = (unsigned int)v6;
  v9 = 2795;
LABEL_17:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v9);
  if ( (int)v7 < 0 && v4 )
  {
    SymCryptEckeyFree(*(_QWORD *)(v3 + 24));
    *(_QWORD *)(v3 + 24) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800766a0  push    rbx
0x1800766a2  push    rbp
0x1800766a3  push    rsi
0x1800766a4  push    rdi
0x1800766a5  sub     rsp, 38h
0x1800766a9  xor     ebx, ebx
0x1800766ab  xor     ebp, ebp
0x1800766ad  mov     [rsp+58h+arg_0], rbx
0x1800766b2  mov     esi, r8d
0x1800766b5  test    rcx, rcx
0x1800766b8  jz      loc_18007679F
0x1800766be  test    edx, edx
0x1800766c0  jz      short loc_1800766CB
0x1800766c2  cmp     edx, 18h
0x1800766c5  jnz     loc_18007679F
0x1800766cb  lea     rax, [rsp+58h+arg_0]
0x1800766d0  mov     r9d, 1
0x1800766d6  xor     r8d, r8d
0x1800766d9  mov     [rsp+58h+var_38], rax
0x1800766de  mov     edx, esi
0x1800766e0  call    ValidateEccKey
0x1800766e5  mov     rbx, [rsp+58h+arg_0]
0x1800766ea  mov     edi, eax
0x1800766ec  test    eax, eax
0x1800766ee  jns     short loc_1800766FD
0x1800766f0  mov     ecx, eax
0x1800766f2  mov     r9d, 0AEBh
0x1800766f8  jmp     loc_1800767AF
0x1800766fd  mov     eax, [rbx+20h]
0x180076700  test    al, 2
0x180076702  jnz     loc_18007678D
0x180076708  mov     rcx, [rbx+10h]
0x18007670c  test    rcx, rcx
0x18007670f  jz      short loc_18007678D
0x180076711  cmp     [rbx+18h], rbp
0x180076715  jnz     short loc_180076785
0x180076717  mov     rcx, [rcx+8]
0x18007671b  call    SymCryptEckeyAllocate
0x180076720  mov     [rbx+18h], rax
0x180076724  test    rax, rax
0x180076727  jnz     short loc_180076751
0x180076729  mov     edi, 0C0000017h
0x18007672e  mov     r9d, 0AFCh
0x180076734  mov     ecx, 0C0000017h
0x180076739  lea     rdx, aStatus; "Status"
0x180076740  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180076747  call    DebugTraceError
0x18007674c  jmp     loc_1800767DB
0x180076751  neg     esi
0x180076753  mov     rdx, rax
0x180076756  sbb     ecx, ecx
0x180076758  and     ecx, 0FFFFF000h
0x18007675e  add     ecx, 2000h
0x180076764  call    SymCryptEckeySetRandom
0x180076769  test    eax, eax
0x18007676b  jz      short loc_180076785
0x18007676d  mov     ecx, eax
0x18007676f  mov     ebp, 1
0x180076774  call    SymcryptErrorCodeToNtStatus
0x180076779  mov     edi, eax
0x18007677b  mov     ecx, eax
0x18007677d  mov     r9d, 0B08h
0x180076783  jmp     short loc_1800767AF
0x180076785  or      dword ptr [rbx+20h], 2
0x180076789  xor     edi, edi
0x18007678b  jmp     short loc_1800767DB
0x18007678d  mov     edi, 0C0000008h
0x180076792  mov     r9d, 0AF2h
0x180076798  mov     ecx, 0C0000008h
0x18007679d  jmp     short loc_180076739
0x18007679f  mov     edi, 0C000000Dh
0x1800767a4  mov     ecx, 0C000000Dh
0x1800767a9  mov     r9d, 0AE4h
0x1800767af  lea     rdx, aStatus; "Status"
0x1800767b6  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800767bd  call    DebugTraceError
0x1800767c2  test    edi, edi
0x1800767c4  jns     short loc_1800767DB
0x1800767c6  test    ebp, ebp
0x1800767c8  jz      short loc_1800767DB
0x1800767ca  mov     rcx, [rbx+18h]
0x1800767ce  call    SymCryptEckeyFree
0x1800767d3  mov     qword ptr [rbx+18h], 0
0x1800767db  mov     eax, edi
0x1800767dd  add     rsp, 38h
0x1800767e1  pop     rdi
0x1800767e2  pop     rsi
0x1800767e3  pop     rbp
0x1800767e4  pop     rbx
0x1800767e5  retn
```
