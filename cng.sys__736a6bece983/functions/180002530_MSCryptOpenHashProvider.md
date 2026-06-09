# MSCryptOpenHashProvider

- ea: `0x180002530`
- end: `0x1800027cc`
- name: `MSCryptOpenHashProvider`
- size: `668`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001cc4`
- `0x180004820`
- `0x18007dfb4`
- `0x18007e320`
- `0x180081198`
- `0x180081c48`

## callees

- `0x180002530`
- `0x1800027e0`
- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x18009f616`

## string_xrefs

- `0x18000267e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800026e8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180002734`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a0257`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenHashProvider(__int64 *a1, const wchar_t *a2, int a3)
{
  char v3; // si
  char v6; // di
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // esi
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // edx
  BOOL v15; // edx
  BOOL v16; // ecx
  unsigned int v17; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  char v22; // [rsp+30h] [rbp-48h]

  v3 = a3;
  if ( (a3 & 0xFFFFFF92) != 0 )
  {
    v17 = -1073741811;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v17;
    v22 = 12;
LABEL_23:
    WPP_SF_sDsd(
      v19[3],
      (_DWORD)a2,
      1,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      v22);
    return v17;
  }
  if ( !a1 )
  {
    v17 = -1073741811;
    v20 = 787;
    v21 = 3221225485LL;
LABEL_35:
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v20);
    return v17;
  }
  if ( !a2 )
  {
    v17 = -1073741811;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v17;
    v22 = 26;
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
    v17 = -1073741637;
    v20 = 813;
    v21 = 3221225659LL;
    goto LABEL_35;
  }
  v7 = LookupHashFunction(a2, (v6 & 8) != 0);
  if ( v7 >= 0x1A )
  {
    v17 = -1073741637;
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
    v11 = v6 & 4;
    if ( (v6 & 4) != 0
      && ((v8 = LODWORD(rgHashAlgorithmDefaults[12 * v7 + 1]), (((_DWORD)v8 - 131081) & 0xFFFFFFFC) != 0)
       || (_DWORD)v8 == 131082) )
    {
      return (unsigned int)-1073741637;
    }
    else
    {
      v12 = 12LL * v7;
      v13 = MSCryptAlloc(LODWORD(rgHashAlgorithmDefaults[v12]), v8, v9, v10);
      if ( v13 )
      {
        *(_OWORD *)v13 = *(_OWORD *)&rgHashAlgorithmDefaults[v12];
        *(_OWORD *)(v13 + 16) = *(_OWORD *)&rgHashAlgorithmDefaults[v12 + 2];
        *(_OWORD *)(v13 + 32) = *(_OWORD *)&rgHashAlgorithmDefaults[v12 + 4];
        *(_QWORD *)(v13 + 48) = rgHashAlgorithmDefaults[v12 + 6];
        *(_DWORD *)(v13 + 36) = v6 & 1;
        v15 = (v6 & 0x40) != 0;
        *(_DWORD *)(v13 + 44) = v15;
        v16 = v11 != 0;
        if ( (v6 & 0x20) != 0 )
          v16 = 1;
        *(_BYTE *)(v13 + 48) = v11 != 0;
        *(_DWORD *)(v13 + 40) = v15 || v16;
        if ( (v6 & 8) != 0 && !LODWORD(rgHashAlgorithmDefaults[v12 + 8]) )
          *(_DWORD *)(v13 + 52) = 1;
        *a1 = v13;
        return 0;
      }
      else
      {
        v17 = -1073741801;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v14,
            1,
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            77);
      }
    }
  }
  return v17;
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
0x180002587  jnz     loc_1800A0269
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
0x18000267e  lea     rax, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
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
0x1800026e8  lea     rax, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
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
0x180002734  lea     rax, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
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
0x180002798  jmp     loc_1800A0250
0x18000279d  lea     rax, [rcx+rcx*2]
0x1800027a1  shl     rax, 5
0x1800027a5  mov     edx, [rax+r12+8]
0x1800027aa  lea     eax, [rdx-20009h]
0x1800027b0  test    eax, 0FFFFFFFCh
0x1800027b5  jnz     loc_1800A02BB
0x1800027bb  cmp     edx, 2000Ah
0x1800027c1  jnz     loc_1800025BF
0x1800027c7  jmp     loc_1800A02BB
0x1800a0240  mov     ebx, 0C00000BBh
0x1800a0245  mov     r9d, 32Dh
0x1800a024b  mov     ecx, 0C00000BBh
0x1800a0250  lea     rdx, aStatus; "Status"
0x1800a0257  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a025e  call    DebugTraceError
0x1800a0263  nop
0x1800a0264  jmp     loc_18000263E
0x1800a0269  lea     rdx, aCshake128_0; "CSHAKE128"
0x1800a0270  mov     rcx, rbx; Str1
0x1800a0273  call    wcscmp_0
0x1800a0278  test    eax, eax
0x1800a027a  jz      short loc_1800A0240
0x1800a027c  lea     rdx, aCshake256_0; "CSHAKE256"
0x1800a0283  mov     rcx, rbx; Str1
0x1800a0286  call    wcscmp_0
0x1800a028b  test    eax, eax
0x1800a028d  jz      short loc_1800A0240
0x1800a028f  lea     rdx, aKmac128_0; "KMAC128"
0x1800a0296  mov     rcx, rbx; Str1
0x1800a0299  call    wcscmp_0
0x1800a029e  test    eax, eax
0x1800a02a0  jz      short loc_1800A0240
0x1800a02a2  lea     rdx, aKmac256_0; "KMAC256"
0x1800a02a9  mov     rcx, rbx; Str1
0x1800a02ac  call    wcscmp_0
0x1800a02b1  test    eax, eax
0x1800a02b3  jnz     loc_18000258D
0x1800a02b9  jmp     short loc_1800A0240
0x1800a02bb  mov     ebx, 0C00000BBh
0x1800a02c0  jmp     loc_18000263E
```
