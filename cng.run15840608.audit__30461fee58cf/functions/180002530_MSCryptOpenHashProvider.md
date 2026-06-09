# MSCryptOpenHashProvider

- ea: `0x180002530`
- end: `0x1800027cc`
- name: `MSCryptOpenHashProvider`
- size: `668`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001cc4`
- `0x180004820`
- `0x18007cfc4`
- `0x18007d330`
- `0x1800801a8`
- `0x180080c58`

## callees

- `0x180002530`
- `0x1800027e0`
- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x18009d746`

## string_xrefs

- `0x18000267e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800026e8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180002734`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18009e427`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenHashProvider(__int64 *a1, const wchar_t *a2, int a3)
{
  char v3; // si
  char v6; // di
  unsigned int v7; // eax
  int v8; // edx
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
  int v20; // edx
  char v21; // [rsp+30h] [rbp-48h]

  v3 = a3;
  if ( (a3 & 0xFFFFFF92) != 0 )
  {
    v15 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v15;
    v21 = 12;
LABEL_23:
    WPP_SF_sDsd(
      v17[3],
      (_DWORD)a2,
      1,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      v21);
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
    v21 = 26;
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
      && ((v20 = rgHashAlgorithmDefaults[12 * v7 + 1], ((v20 - 131081) & 0xFFFFFFFC) != 0) || v20 == 131082) )
    {
      return (unsigned int)-1073741637;
    }
    else
    {
      v10 = 12LL * v7;
      v11 = MSCryptAlloc(LODWORD(rgHashAlgorithmDefaults[v10]));
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
0x180002530  push    rbx
0x180002532  push    rbp
0x180002533  push    rsi
0x180002534  push    rdi
0x180002535  push    r12
0x180002537  push    r14
0x180002539  push    r15
0x18000253b  sub     rsp, 40h
0x18000253f  mov     esi, r8d
0x180002542  mov     rbx, rdx
0x180002545  mov     r14, rcx
0x180002548  test    r8d, 0FFFFFF92h
0x18000254f  jnz     loc_1800026B2
0x180002555  test    rcx, rcx
0x180002558  jz      loc_180002788
0x18000255e  test    rdx, rdx
0x180002561  jz      loc_18000274D
0x180002567  lea     rdx, aAesCmac_0; "AES-CMAC"
0x18000256e  mov     rcx, rbx; Str1
0x180002571  call    wcscmp_0
0x180002576  mov     edi, esi
0x180002578  and     edi, 0FFFFFFF7h
0x18000257b  test    eax, eax
0x18000257d  cmovnz  edi, esi
0x180002580  mov     r15d, edi
0x180002583  and     r15d, 40h
0x180002587  jnz     loc_18009E439
0x18000258d  mov     edx, 0
0x180002592  mov     ebp, edi
0x180002594  and     ebp, 8
0x180002597  mov     rcx, rbx
0x18000259a  setnz   dl
0x18000259d  call    LookupHashFunction
0x1800025a2  cmp     eax, 1Ah
0x1800025a5  jnb     loc_1800026FE
0x1800025ab  mov     esi, edi
0x1800025ad  mov     ecx, eax
0x1800025af  lea     r12, rgHashAlgorithmDefaults
0x1800025b6  and     esi, 4
0x1800025b9  jnz     loc_18000279D
0x1800025bf  lea     rbx, [rcx+rcx*2]
0x1800025c3  shl     rbx, 5
0x1800025c7  mov     ecx, [rbx+r12]
0x1800025cb  call    MSCryptAlloc
0x1800025d0  mov     r9, rax
0x1800025d3  test    rax, rax
0x1800025d6  jz      short loc_180002650
0x1800025d8  movups  xmm0, xmmword ptr [rbx+r12]
0x1800025dd  xor     edx, edx
0x1800025df  mov     r8d, 1
0x1800025e5  movups  xmmword ptr [rax], xmm0
0x1800025e8  movups  xmm1, xmmword ptr [rbx+r12+10h]
0x1800025ee  movups  xmmword ptr [rax+10h], xmm1
0x1800025f2  movups  xmm0, xmmword ptr [rbx+r12+20h]
0x1800025f8  movups  xmmword ptr [rax+20h], xmm0
0x1800025fc  movsd   xmm1, qword ptr [rbx+r12+30h]
0x180002603  movsd   qword ptr [rax+30h], xmm1
0x180002608  mov     eax, edi
0x18000260a  and     eax, r8d
0x18000260d  test    r15d, r15d
0x180002610  mov     [r9+24h], eax
0x180002614  setnz   dl
0x180002617  test    esi, esi
0x180002619  mov     [r9+2Ch], edx
0x18000261d  setnz   al
0x180002620  test    dil, 20h
0x180002624  movzx   ecx, al
0x180002627  cmovnz  ecx, r8d
0x18000262b  mov     [r9+30h], al
0x18000262f  or      ecx, edx
0x180002631  mov     [r9+28h], ecx
0x180002635  test    ebp, ebp
0x180002637  jnz     short loc_1800026A4
0x180002639  mov     [r14], r9
0x18000263c  xor     ebx, ebx
0x18000263e  mov     eax, ebx
0x180002640  add     rsp, 40h
0x180002644  pop     r15
0x180002646  pop     r14
0x180002648  pop     r12
0x18000264a  pop     rdi
0x18000264b  pop     rsi
0x18000264c  pop     rbp
0x18000264d  pop     rbx
0x18000264e  retn
0x180002650  mov     ebx, 0C0000017h
0x180002655  mov     rcx, cs:WPP_GLOBAL_Control
0x18000265c  lea     rax, WPP_GLOBAL_Control
0x180002663  cmp     rcx, rax
0x180002666  jz      short loc_18000263E
0x180002668  mov     eax, [rcx+2Ch]
0x18000266b  mov     r8d, 1
0x180002671  test    r8b, al
0x180002674  jz      short loc_18000263E
0x180002676  mov     dword ptr [rsp+78h+var_48], 34Dh
0x18000267e  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002685  mov     [rsp+78h+var_50], rax
0x18000268a  mov     [rsp+78h+var_58], 0C0000017h
0x180002692  mov     rcx, [rcx+18h]
0x180002696  lea     r9, aStatus; "Status"
0x18000269d  call    WPP_SF_sDsd
0x1800026a2  jmp     short loc_18000263E
0x1800026a4  cmp     dword ptr [rbx+r12+40h], 0
0x1800026aa  jnz     short loc_180002639
0x1800026ac  mov     [r9+34h], r8d
0x1800026b0  jmp     short loc_180002639
0x1800026b2  mov     ebx, 0C000000Dh
0x1800026b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026be  lea     rax, WPP_GLOBAL_Control
0x1800026c5  cmp     rcx, rax
0x1800026c8  jz      loc_18000263E
0x1800026ce  mov     eax, [rcx+2Ch]
0x1800026d1  mov     r8d, 1
0x1800026d7  test    r8b, al
0x1800026da  jz      loc_18000263E
0x1800026e0  mov     dword ptr [rsp+78h+var_48], 30Ch
0x1800026e8  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800026ef  mov     [rsp+78h+var_50], rax
0x1800026f4  mov     [rsp+78h+var_58], 0C000000Dh
0x1800026fc  jmp     short loc_180002692
0x1800026fe  mov     ebx, 0C00000BBh
0x180002703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000270a  lea     rax, WPP_GLOBAL_Control
0x180002711  cmp     rcx, rax
0x180002714  jz      loc_18000263E
0x18000271a  mov     eax, [rcx+2Ch]
0x18000271d  mov     r8d, 1
0x180002723  test    r8b, al
0x180002726  jz      loc_18000263E
0x18000272c  mov     dword ptr [rsp+78h+var_48], 339h
0x180002734  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000273b  mov     [rsp+78h+var_50], rax
0x180002740  mov     [rsp+78h+var_58], 0C00000BBh
0x180002748  jmp     loc_180002692
0x18000274d  mov     ebx, 0C000000Dh
0x180002752  mov     rcx, cs:WPP_GLOBAL_Control
0x180002759  lea     rax, WPP_GLOBAL_Control
0x180002760  cmp     rcx, rax
0x180002763  jz      loc_18000263E
0x180002769  mov     eax, [rcx+2Ch]
0x18000276c  mov     r8d, 1
0x180002772  test    r8b, al
0x180002775  jz      loc_18000263E
0x18000277b  mov     dword ptr [rsp+78h+var_48], 31Ah
0x180002783  jmp     loc_1800026E8
0x180002788  mov     ebx, 0C000000Dh
0x18000278d  mov     r9d, 313h
0x180002793  mov     ecx, 0C000000Dh
0x180002798  jmp     loc_18009E420
0x18000279d  lea     rax, [rcx+rcx*2]
0x1800027a1  shl     rax, 5
0x1800027a5  mov     edx, [rax+r12+8]
0x1800027aa  lea     eax, [rdx-20009h]
0x1800027b0  test    eax, 0FFFFFFFCh
0x1800027b5  jnz     loc_18009E48B
0x1800027bb  cmp     edx, 2000Ah
0x1800027c1  jnz     loc_1800025BF
0x1800027c7  jmp     loc_18009E48B
0x18009e410  mov     ebx, 0C00000BBh
0x18009e415  mov     r9d, 32Dh
0x18009e41b  mov     ecx, 0C00000BBh
0x18009e420  lea     rdx, aStatus; "Status"
0x18009e427  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009e42e  call    DebugTraceError
0x18009e433  nop
0x18009e434  jmp     loc_18000263E
0x18009e439  lea     rdx, aCshake128_0; "CSHAKE128"
0x18009e440  mov     rcx, rbx; Str1
0x18009e443  call    wcscmp_0
0x18009e448  test    eax, eax
0x18009e44a  jz      short loc_18009E410
0x18009e44c  lea     rdx, aCshake256_0; "CSHAKE256"
0x18009e453  mov     rcx, rbx; Str1
0x18009e456  call    wcscmp_0
0x18009e45b  test    eax, eax
0x18009e45d  jz      short loc_18009E410
0x18009e45f  lea     rdx, aKmac128_0; "KMAC128"
0x18009e466  mov     rcx, rbx; Str1
0x18009e469  call    wcscmp_0
0x18009e46e  test    eax, eax
0x18009e470  jz      short loc_18009E410
0x18009e472  lea     rdx, aKmac256_0; "KMAC256"
0x18009e479  mov     rcx, rbx; Str1
0x18009e47c  call    wcscmp_0
0x18009e481  test    eax, eax
0x18009e483  jnz     loc_18000258D
0x18009e489  jmp     short loc_18009E410
0x18009e48b  mov     ebx, 0C00000BBh
0x18009e490  jmp     loc_18000263E
```
