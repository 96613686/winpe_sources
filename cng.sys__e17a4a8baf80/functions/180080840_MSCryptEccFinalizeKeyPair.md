# MSCryptEccFinalizeKeyPair

- ea: `0x180080840`
- end: `0x180080987`
- name: `MSCryptEccFinalizeKeyPair`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007fbe0`
- `0x18007fff0`

## callees

- `0x18001155c`
- `0x180046ab8`
- `0x180050c88`
- `0x180051dd0`
- `0x180080840`
- `0x1800920d4`
- `0x1800924c0`

## string_xrefs

- `0x1800808e0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180080956`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x180080840  push    rbx
0x180080842  push    rbp
0x180080843  push    rsi
0x180080844  push    rdi
0x180080845  sub     rsp, 38h
0x180080849  xor     ebx, ebx
0x18008084b  xor     ebp, ebp
0x18008084d  mov     [rsp+58h+arg_0], rbx
0x180080852  mov     esi, r8d
0x180080855  test    rcx, rcx
0x180080858  jz      loc_18008093F
0x18008085e  test    edx, edx
0x180080860  jz      short loc_18008086B
0x180080862  cmp     edx, 18h
0x180080865  jnz     loc_18008093F
0x18008086b  lea     rax, [rsp+58h+arg_0]
0x180080870  mov     r9d, 1
0x180080876  xor     r8d, r8d
0x180080879  mov     [rsp+58h+var_38], rax
0x18008087e  mov     edx, esi
0x180080880  call    ValidateEccKey
0x180080885  mov     rbx, [rsp+58h+arg_0]
0x18008088a  mov     edi, eax
0x18008088c  test    eax, eax
0x18008088e  jns     short loc_18008089D
0x180080890  mov     ecx, eax
0x180080892  mov     r9d, 0AEBh
0x180080898  jmp     loc_18008094F
0x18008089d  mov     eax, [rbx+20h]
0x1800808a0  test    al, 2
0x1800808a2  jnz     loc_18008092D
0x1800808a8  mov     rcx, [rbx+10h]
0x1800808ac  test    rcx, rcx
0x1800808af  jz      short loc_18008092D
0x1800808b1  cmp     [rbx+18h], rbp
0x1800808b5  jnz     short loc_180080925
0x1800808b7  mov     rcx, [rcx+8]
0x1800808bb  call    SymCryptEckeyAllocate
0x1800808c0  mov     [rbx+18h], rax
0x1800808c4  test    rax, rax
0x1800808c7  jnz     short loc_1800808F1
0x1800808c9  mov     edi, 0C0000017h
0x1800808ce  mov     r9d, 0AFCh
0x1800808d4  mov     ecx, 0C0000017h
0x1800808d9  lea     rdx, aStatus; "Status"
0x1800808e0  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800808e7  call    DebugTraceError
0x1800808ec  jmp     loc_18008097B
0x1800808f1  neg     esi
0x1800808f3  mov     rdx, rax
0x1800808f6  sbb     ecx, ecx
0x1800808f8  and     ecx, 0FFFFF000h
0x1800808fe  add     ecx, 2000h
0x180080904  call    SymCryptEckeySetRandom
0x180080909  test    eax, eax
0x18008090b  jz      short loc_180080925
0x18008090d  mov     ecx, eax
0x18008090f  mov     ebp, 1
0x180080914  call    SymcryptErrorCodeToNtStatus
0x180080919  mov     edi, eax
0x18008091b  mov     ecx, eax
0x18008091d  mov     r9d, 0B08h
0x180080923  jmp     short loc_18008094F
0x180080925  or      dword ptr [rbx+20h], 2
0x180080929  xor     edi, edi
0x18008092b  jmp     short loc_18008097B
0x18008092d  mov     edi, 0C0000008h
0x180080932  mov     r9d, 0AF2h
0x180080938  mov     ecx, 0C0000008h
0x18008093d  jmp     short loc_1800808D9
0x18008093f  mov     edi, 0C000000Dh
0x180080944  mov     ecx, 0C000000Dh
0x180080949  mov     r9d, 0AE4h
0x18008094f  lea     rdx, aStatus; "Status"
0x180080956  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008095d  call    DebugTraceError
0x180080962  test    edi, edi
0x180080964  jns     short loc_18008097B
0x180080966  test    ebp, ebp
0x180080968  jz      short loc_18008097B
0x18008096a  mov     rcx, [rbx+18h]
0x18008096e  call    SymCryptEckeyFree
0x180080973  mov     qword ptr [rbx+18h], 0
0x18008097b  mov     eax, edi
0x18008097d  add     rsp, 38h
0x180080981  pop     rdi
0x180080982  pop     rsi
0x180080983  pop     rbp
0x180080984  pop     rbx
0x180080985  retn
```
