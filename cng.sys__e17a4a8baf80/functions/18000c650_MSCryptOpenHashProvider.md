# MSCryptOpenHashProvider

- ea: `0x18000c650`
- end: `0x18000c8ec`
- name: `MSCryptOpenHashProvider`
- size: `668`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bde4`
- `0x18000e940`
- `0x1800871c4`
- `0x180087530`
- `0x18008a398`
- `0x18008ae48`

## callees

- `0x18000c650`
- `0x18000c900`
- `0x18000e090`
- `0x18001155c`
- `0x1800123d0`
- `0x1800a4232`

## string_xrefs

- `0x18000c79e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000c808`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000c854`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a51c5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenHashProvider(__int64 *a1, const wchar_t *a2, int a3)
{
  char v3; // si
  char v6; // di
  unsigned int v7; // eax
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // edx
  BOOL v13; // edx
  BOOL v14; // ecx
  unsigned int v15; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rcx
  char v20; // [rsp+30h] [rbp-48h]

  v3 = a3;
  if ( (a3 & 0xFFFFFF92) != 0 )
  {
    v15 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v15;
    v20 = 12;
LABEL_23:
    WPP_SF_sDsd(
      v17[3],
      (_DWORD)a2,
      1,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      v20);
    return v15;
  }
  if ( !a1 )
  {
    v15 = -1073741811;
    v18 = 787;
    v19 = 3221225485LL;
LABEL_35:
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v18);
    return v15;
  }
  if ( !a2 )
  {
    v15 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v15;
    v20 = 26;
    goto LABEL_23;
  }
  v6 = a3 & 0xF7;
  if ( wcscmp_0(a2, L"AES-CMAC") )
    v6 = v3;
  if ( (v6 & 0x40) != 0
    && (!wcscmp_0(a2, L"CSHAKE128")
     || !wcscmp_0(a2, L"CSHAKE256")
     || !wcscmp_0(a2, L"KMAC128")
     || !wcscmp_0(a2, L"KMAC256")) )
  {
    v15 = -1073741637;
    v18 = 813;
    v19 = 3221225659LL;
    goto LABEL_35;
  }
  v7 = LookupHashFunction(a2, (v6 & 8) != 0);
  if ( v7 >= 0x1A )
  {
    v15 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v8,
        1,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        57);
  }
  else
  {
    v9 = v6 & 4;
    if ( (v6 & 4) != 0
      && ((v8 = LODWORD(rgHashAlgorithmDefaults[12 * v7 + 1]), (((_DWORD)v8 - 131081) & 0xFFFFFFFC) != 0)
       || (_DWORD)v8 == 131082) )
    {
      return (unsigned int)-1073741637;
    }
    else
    {
      v10 = 12LL * v7;
      v11 = MSCryptAlloc(LODWORD(rgHashAlgorithmDefaults[v10]), v8);
      if ( v11 )
      {
        *(_OWORD *)v11 = *(_OWORD *)&rgHashAlgorithmDefaults[v10];
        *(_OWORD *)(v11 + 16) = *(_OWORD *)&rgHashAlgorithmDefaults[v10 + 2];
        *(_OWORD *)(v11 + 32) = *(_OWORD *)&rgHashAlgorithmDefaults[v10 + 4];
        *(_QWORD *)(v11 + 48) = rgHashAlgorithmDefaults[v10 + 6];
        *(_DWORD *)(v11 + 36) = v6 & 1;
        v13 = (v6 & 0x40) != 0;
        *(_DWORD *)(v11 + 44) = v13;
        v14 = v9 != 0;
        if ( (v6 & 0x20) != 0 )
          v14 = 1;
        *(_BYTE *)(v11 + 48) = v9 != 0;
        *(_DWORD *)(v11 + 40) = v13 || v14;
        if ( (v6 & 8) != 0 && !LODWORD(rgHashAlgorithmDefaults[v10 + 8]) )
          *(_DWORD *)(v11 + 52) = 1;
        *a1 = v11;
        return 0;
      }
      else
      {
        v15 = -1073741801;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v12,
            1,
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            77);
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18000c650  push    rbx
0x18000c652  push    rbp
0x18000c653  push    rsi
0x18000c654  push    rdi
0x18000c655  push    r12
0x18000c657  push    r14
0x18000c659  push    r15
0x18000c65b  sub     rsp, 40h
0x18000c65f  mov     esi, r8d
0x18000c662  mov     rbx, rdx
0x18000c665  mov     r14, rcx
0x18000c668  test    r8d, 0FFFFFF92h
0x18000c66f  jnz     loc_18000C7D2
0x18000c675  test    rcx, rcx
0x18000c678  jz      loc_18000C8A8
0x18000c67e  test    rdx, rdx
0x18000c681  jz      loc_18000C86D
0x18000c687  lea     rdx, aAesCmac_0; "AES-CMAC"
0x18000c68e  mov     rcx, rbx; Str1
0x18000c691  call    wcscmp_0
0x18000c696  mov     edi, esi
0x18000c698  and     edi, 0FFFFFFF7h
0x18000c69b  test    eax, eax
0x18000c69d  cmovnz  edi, esi
0x18000c6a0  mov     r15d, edi
0x18000c6a3  and     r15d, 40h
0x18000c6a7  jnz     loc_1800A51D7
0x18000c6ad  mov     edx, 0
0x18000c6b2  mov     ebp, edi
0x18000c6b4  and     ebp, 8
0x18000c6b7  mov     rcx, rbx
0x18000c6ba  setnz   dl
0x18000c6bd  call    LookupHashFunction
0x18000c6c2  cmp     eax, 1Ah
0x18000c6c5  jnb     loc_18000C81E
0x18000c6cb  mov     esi, edi
0x18000c6cd  mov     ecx, eax
0x18000c6cf  lea     r12, rgHashAlgorithmDefaults
0x18000c6d6  and     esi, 4
0x18000c6d9  jnz     loc_18000C8BD
0x18000c6df  lea     rbx, [rcx+rcx*2]
0x18000c6e3  shl     rbx, 5
0x18000c6e7  mov     ecx, [rbx+r12]
0x18000c6eb  call    MSCryptAlloc
0x18000c6f0  mov     r9, rax
0x18000c6f3  test    rax, rax
0x18000c6f6  jz      short loc_18000C770
0x18000c6f8  movups  xmm0, xmmword ptr [rbx+r12]
0x18000c6fd  xor     edx, edx
0x18000c6ff  mov     r8d, 1
0x18000c705  movups  xmmword ptr [rax], xmm0
0x18000c708  movups  xmm1, xmmword ptr [rbx+r12+10h]
0x18000c70e  movups  xmmword ptr [rax+10h], xmm1
0x18000c712  movups  xmm0, xmmword ptr [rbx+r12+20h]
0x18000c718  movups  xmmword ptr [rax+20h], xmm0
0x18000c71c  movsd   xmm1, qword ptr [rbx+r12+30h]
0x18000c723  movsd   qword ptr [rax+30h], xmm1
0x18000c728  mov     eax, edi
0x18000c72a  and     eax, r8d
0x18000c72d  test    r15d, r15d
0x18000c730  mov     [r9+24h], eax
0x18000c734  setnz   dl
0x18000c737  test    esi, esi
0x18000c739  mov     [r9+2Ch], edx
0x18000c73d  setnz   al
0x18000c740  test    dil, 20h
0x18000c744  movzx   ecx, al
0x18000c747  cmovnz  ecx, r8d
0x18000c74b  mov     [r9+30h], al
0x18000c74f  or      ecx, edx
0x18000c751  mov     [r9+28h], ecx
0x18000c755  test    ebp, ebp
0x18000c757  jnz     short loc_18000C7C4
0x18000c759  mov     [r14], r9
0x18000c75c  xor     ebx, ebx
0x18000c75e  mov     eax, ebx
0x18000c760  add     rsp, 40h
0x18000c764  pop     r15
0x18000c766  pop     r14
0x18000c768  pop     r12
0x18000c76a  pop     rdi
0x18000c76b  pop     rsi
0x18000c76c  pop     rbp
0x18000c76d  pop     rbx
0x18000c76e  retn
0x18000c770  mov     ebx, 0C0000017h
0x18000c775  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c77c  lea     rax, WPP_GLOBAL_Control
0x18000c783  cmp     rcx, rax
0x18000c786  jz      short loc_18000C75E
0x18000c788  mov     eax, [rcx+2Ch]
0x18000c78b  mov     r8d, 1
0x18000c791  test    r8b, al
0x18000c794  jz      short loc_18000C75E
0x18000c796  mov     dword ptr [rsp+78h+var_48], 34Dh
0x18000c79e  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c7a5  mov     [rsp+78h+var_50], rax
0x18000c7aa  mov     [rsp+78h+var_58], 0C0000017h
0x18000c7b2  mov     rcx, [rcx+18h]
0x18000c7b6  lea     r9, aStatus; "Status"
0x18000c7bd  call    WPP_SF_sDsd
0x18000c7c2  jmp     short loc_18000C75E
0x18000c7c4  cmp     dword ptr [rbx+r12+40h], 0
0x18000c7ca  jnz     short loc_18000C759
0x18000c7cc  mov     [r9+34h], r8d
0x18000c7d0  jmp     short loc_18000C759
0x18000c7d2  mov     ebx, 0C000000Dh
0x18000c7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7de  lea     rax, WPP_GLOBAL_Control
0x18000c7e5  cmp     rcx, rax
0x18000c7e8  jz      loc_18000C75E
0x18000c7ee  mov     eax, [rcx+2Ch]
0x18000c7f1  mov     r8d, 1
0x18000c7f7  test    r8b, al
0x18000c7fa  jz      loc_18000C75E
0x18000c800  mov     dword ptr [rsp+78h+var_48], 30Ch
0x18000c808  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c80f  mov     [rsp+78h+var_50], rax
0x18000c814  mov     [rsp+78h+var_58], 0C000000Dh
0x18000c81c  jmp     short loc_18000C7B2
0x18000c81e  mov     ebx, 0C00000BBh
0x18000c823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c82a  lea     rax, WPP_GLOBAL_Control
0x18000c831  cmp     rcx, rax
0x18000c834  jz      loc_18000C75E
0x18000c83a  mov     eax, [rcx+2Ch]
0x18000c83d  mov     r8d, 1
0x18000c843  test    r8b, al
0x18000c846  jz      loc_18000C75E
0x18000c84c  mov     dword ptr [rsp+78h+var_48], 339h
0x18000c854  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c85b  mov     [rsp+78h+var_50], rax
0x18000c860  mov     [rsp+78h+var_58], 0C00000BBh
0x18000c868  jmp     loc_18000C7B2
0x18000c86d  mov     ebx, 0C000000Dh
0x18000c872  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c879  lea     rax, WPP_GLOBAL_Control
0x18000c880  cmp     rcx, rax
0x18000c883  jz      loc_18000C75E
0x18000c889  mov     eax, [rcx+2Ch]
0x18000c88c  mov     r8d, 1
0x18000c892  test    r8b, al
0x18000c895  jz      loc_18000C75E
0x18000c89b  mov     dword ptr [rsp+78h+var_48], 31Ah
0x18000c8a3  jmp     loc_18000C808
0x18000c8a8  mov     ebx, 0C000000Dh
0x18000c8ad  mov     r9d, 313h
0x18000c8b3  mov     ecx, 0C000000Dh
0x18000c8b8  jmp     loc_1800A51BE
0x18000c8bd  lea     rax, [rcx+rcx*2]
0x18000c8c1  shl     rax, 5
0x18000c8c5  mov     edx, [rax+r12+8]
0x18000c8ca  lea     eax, [rdx-20009h]
0x18000c8d0  test    eax, 0FFFFFFFCh
0x18000c8d5  jnz     loc_1800A5229
0x18000c8db  cmp     edx, 2000Ah
0x18000c8e1  jnz     loc_18000C6DF
0x18000c8e7  jmp     loc_1800A5229
0x1800a51ae  mov     ebx, 0C00000BBh
0x1800a51b3  mov     r9d, 32Dh
0x1800a51b9  mov     ecx, 0C00000BBh
0x1800a51be  lea     rdx, aStatus; "Status"
0x1800a51c5  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a51cc  call    DebugTraceError
0x1800a51d1  nop
0x1800a51d2  jmp     loc_18000C75E
0x1800a51d7  lea     rdx, aCshake128_0; "CSHAKE128"
0x1800a51de  mov     rcx, rbx; Str1
0x1800a51e1  call    wcscmp_0
0x1800a51e6  test    eax, eax
0x1800a51e8  jz      short loc_1800A51AE
0x1800a51ea  lea     rdx, aCshake256_0; "CSHAKE256"
0x1800a51f1  mov     rcx, rbx; Str1
0x1800a51f4  call    wcscmp_0
0x1800a51f9  test    eax, eax
0x1800a51fb  jz      short loc_1800A51AE
0x1800a51fd  lea     rdx, aKmac128_0; "KMAC128"
0x1800a5204  mov     rcx, rbx; Str1
0x1800a5207  call    wcscmp_0
0x1800a520c  test    eax, eax
0x1800a520e  jz      short loc_1800A51AE
0x1800a5210  lea     rdx, aKmac256_0; "KMAC256"
0x1800a5217  mov     rcx, rbx; Str1
0x1800a521a  call    wcscmp_0
0x1800a521f  test    eax, eax
0x1800a5221  jnz     loc_18000C6AD
0x1800a5227  jmp     short loc_1800A51AE
0x1800a5229  mov     ebx, 0C00000BBh
0x1800a522e  jmp     loc_18000C75E
```
