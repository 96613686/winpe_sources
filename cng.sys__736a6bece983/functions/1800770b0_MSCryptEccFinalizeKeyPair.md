# MSCryptEccFinalizeKeyPair

- ea: `0x1800770b0`
- end: `0x1800771f7`
- name: `MSCryptEccFinalizeKeyPair`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180076450`
- `0x180076860`

## callees

- `0x18000743c`
- `0x18003d5f8`
- `0x180047628`
- `0x180048770`
- `0x1800770b0`
- `0x1800890b4`
- `0x1800894a0`

## string_xrefs

- `0x180077150`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800771c6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x1800770b0  push    rbx
0x1800770b2  push    rbp
0x1800770b3  push    rsi
0x1800770b4  push    rdi
0x1800770b5  sub     rsp, 38h
0x1800770b9  xor     ebx, ebx
0x1800770bb  xor     ebp, ebp
0x1800770bd  mov     [rsp+58h+arg_0], rbx
0x1800770c2  mov     esi, r8d
0x1800770c5  test    rcx, rcx
0x1800770c8  jz      loc_1800771AF
0x1800770ce  test    edx, edx
0x1800770d0  jz      short loc_1800770DB
0x1800770d2  cmp     edx, 18h
0x1800770d5  jnz     loc_1800771AF
0x1800770db  lea     rax, [rsp+58h+arg_0]
0x1800770e0  mov     r9d, 1
0x1800770e6  xor     r8d, r8d
0x1800770e9  mov     [rsp+58h+var_38], rax
0x1800770ee  mov     edx, esi
0x1800770f0  call    ValidateEccKey
0x1800770f5  mov     rbx, [rsp+58h+arg_0]
0x1800770fa  mov     edi, eax
0x1800770fc  test    eax, eax
0x1800770fe  jns     short loc_18007710D
0x180077100  mov     ecx, eax
0x180077102  mov     r9d, 0AEBh
0x180077108  jmp     loc_1800771BF
0x18007710d  mov     eax, [rbx+20h]
0x180077110  test    al, 2
0x180077112  jnz     loc_18007719D
0x180077118  mov     rcx, [rbx+10h]
0x18007711c  test    rcx, rcx
0x18007711f  jz      short loc_18007719D
0x180077121  cmp     [rbx+18h], rbp
0x180077125  jnz     short loc_180077195
0x180077127  mov     rcx, [rcx+8]
0x18007712b  call    SymCryptEckeyAllocate
0x180077130  mov     [rbx+18h], rax
0x180077134  test    rax, rax
0x180077137  jnz     short loc_180077161
0x180077139  mov     edi, 0C0000017h
0x18007713e  mov     r9d, 0AFCh
0x180077144  mov     ecx, 0C0000017h
0x180077149  lea     rdx, aStatus; "Status"
0x180077150  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077157  call    DebugTraceError
0x18007715c  jmp     loc_1800771EB
0x180077161  neg     esi
0x180077163  mov     rdx, rax
0x180077166  sbb     ecx, ecx
0x180077168  and     ecx, 0FFFFF000h
0x18007716e  add     ecx, 2000h
0x180077174  call    SymCryptEckeySetRandom
0x180077179  test    eax, eax
0x18007717b  jz      short loc_180077195
0x18007717d  mov     ecx, eax
0x18007717f  mov     ebp, 1
0x180077184  call    SymcryptErrorCodeToNtStatus
0x180077189  mov     edi, eax
0x18007718b  mov     ecx, eax
0x18007718d  mov     r9d, 0B08h
0x180077193  jmp     short loc_1800771BF
0x180077195  or      dword ptr [rbx+20h], 2
0x180077199  xor     edi, edi
0x18007719b  jmp     short loc_1800771EB
0x18007719d  mov     edi, 0C0000008h
0x1800771a2  mov     r9d, 0AF2h
0x1800771a8  mov     ecx, 0C0000008h
0x1800771ad  jmp     short loc_180077149
0x1800771af  mov     edi, 0C000000Dh
0x1800771b4  mov     ecx, 0C000000Dh
0x1800771b9  mov     r9d, 0AE4h
0x1800771bf  lea     rdx, aStatus; "Status"
0x1800771c6  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800771cd  call    DebugTraceError
0x1800771d2  test    edi, edi
0x1800771d4  jns     short loc_1800771EB
0x1800771d6  test    ebp, ebp
0x1800771d8  jz      short loc_1800771EB
0x1800771da  mov     rcx, [rbx+18h]
0x1800771de  call    SymCryptEckeyFree
0x1800771e3  mov     qword ptr [rbx+18h], 0
0x1800771eb  mov     eax, edi
0x1800771ed  add     rsp, 38h
0x1800771f1  pop     rdi
0x1800771f2  pop     rsi
0x1800771f3  pop     rbp
0x1800771f4  pop     rbx
0x1800771f5  retn
```
