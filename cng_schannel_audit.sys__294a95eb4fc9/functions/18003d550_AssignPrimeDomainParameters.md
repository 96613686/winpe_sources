# AssignPrimeDomainParameters

- ea: `0x18003d550`
- end: `0x18003d76d`
- name: `AssignPrimeDomainParameters`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003d474`

## callees

- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x18003d550`
- `0x18003d774`
- `0x180046b24`
- `0x180048c14`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x18003d5be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d5f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d6e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a16fa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall AssignPrimeDomainParameters(
        wchar_t **a1,
        unsigned int *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int cbDest)
{
  unsigned __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v16; // ebp
  __int64 v17; // rbx
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  __int64 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r9

  if ( a3 < 0x1C )
  {
    v11 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        206);
    return v11;
  }
  v8 = 5LL * a2[3];
  if ( v8 > 0xFFFFFFFF )
  {
    v11 = -1073741675;
    v12 = 727;
    v13 = 3221225621LL;
LABEL_10:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    return v11;
  }
  LODWORD(v9) = v8 + 28;
  if ( (int)v8 + 28 < (unsigned int)v8
    || (v10 = v9 + a2[4], v10 < (unsigned int)v9)
    || (v9 = v10 + a2[5], (unsigned int)v9 < v10)
    || (v16 = v9 + a2[6], v16 < (unsigned int)v9) )
  {
    v11 = -1073741675;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        (unsigned int)"Status",
        149,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        225);
    return v11;
  }
  if ( a3 < v16 )
  {
    v11 = -1073741789;
    v12 = 746;
    v13 = 3221225507LL;
    goto LABEL_10;
  }
  v17 = cbDest + 24;
  v18 = (wchar_t *)MSCryptAlloc((unsigned int)v17 + v16, v9);
  v19 = v18;
  if ( !v18 )
  {
    v11 = -1073741801;
    v12 = 765;
    v13 = 3221225495LL;
    goto LABEL_10;
  }
  memset(v18, 0, (unsigned int)v17);
  *(_QWORD *)v19 = (char *)v19 + v17;
  memmove((char *)v19 + v17, a2, v16);
  if ( cbDest )
  {
    *((_QWORD *)v19 + 2) = v19 + 12;
    if ( StringCbCopyW(v19 + 12, cbDest, a4) < 0 )
    {
      v11 = -1073741811;
      v21 = 3221225485LL;
      v22 = 785;
LABEL_29:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v22);
      FreeGenericEccKeyParameters(v19);
      return v11;
    }
  }
  v20 = *(__int64 **)v19;
  if ( *(_DWORD *)(*(_QWORD *)v19 + 4LL) == 3 )
    v20 = qword_1800AE860;
  v14 = SymCryptEcurveAllocate(v20);
  *((_QWORD *)v19 + 1) = v14;
  if ( !v14 )
  {
    v11 = -1073741823;
    v21 = 3221225473LL;
    v22 = 802;
    goto LABEL_29;
  }
  *a1 = v19;
  return 0;
}

```

## disassembly

```asm
0x18003d550  push    rbx
0x18003d552  push    rbp
0x18003d553  push    rsi
0x18003d554  push    rdi
0x18003d555  push    r12
0x18003d557  push    r14
0x18003d559  push    r15
0x18003d55b  sub     rsp, 40h
0x18003d55f  mov     r12, r9
0x18003d562  mov     rsi, rdx
0x18003d565  mov     r15, rcx
0x18003d568  cmp     r8d, 1Ch
0x18003d56c  jb      loc_18003D6B6
0x18003d572  mov     eax, [rdx+0Ch]
0x18003d575  lea     rcx, [rax+rax*4]
0x18003d579  mov     eax, 0FFFFFFFFh
0x18003d57e  cmp     rcx, rax
0x18003d581  ja      short loc_18003D5E4
0x18003d583  lea     edx, [rcx+1Ch]
0x18003d586  cmp     edx, ecx
0x18003d588  jb      short loc_18003D597
0x18003d58a  mov     ecx, [rsi+10h]
0x18003d58d  add     ecx, edx
0x18003d58f  cmp     ecx, edx
0x18003d591  jnb     loc_18003D639
0x18003d597  mov     ebx, 0C0000095h
0x18003d59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d5a3  lea     rax, WPP_GLOBAL_Control
0x18003d5aa  cmp     rcx, rax
0x18003d5ad  jz      short loc_18003D627
0x18003d5af  mov     eax, [rcx+2Ch]
0x18003d5b2  test    al, 1
0x18003d5b4  jz      short loc_18003D627
0x18003d5b6  mov     [rsp+78h+var_48], 2E1h
0x18003d5be  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d5c5  mov     [rsp+78h+var_50], r8
0x18003d5ca  mov     [rsp+78h+var_58], 0C0000095h
0x18003d5d2  mov     rcx, [rcx+18h]
0x18003d5d6  lea     r9, aStatus; "Status"
0x18003d5dd  call    WPP_SF_sDsd
0x18003d5e2  jmp     short loc_18003D627
0x18003d5e4  mov     ebx, 0C0000095h
0x18003d5e9  mov     r9d, 2D7h
0x18003d5ef  mov     ecx, 0C0000095h
0x18003d5f4  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d5fb  lea     rdx, aStatus; "Status"
0x18003d602  call    DebugTraceError
0x18003d607  jmp     short loc_18003D627
0x18003d609  lea     rcx, qword_1800AE860
0x18003d610  call    SymCryptEcurveAllocate
0x18003d615  mov     [rdi+8], rax
0x18003d619  test    rax, rax
0x18003d61c  jz      loc_18003D758
0x18003d622  mov     [r15], rdi
0x18003d625  xor     ebx, ebx
0x18003d627  mov     eax, ebx
0x18003d629  add     rsp, 40h
0x18003d62d  pop     r15
0x18003d62f  pop     r14
0x18003d631  pop     r12
0x18003d633  pop     rdi
0x18003d634  pop     rsi
0x18003d635  pop     rbp
0x18003d636  pop     rbx
0x18003d637  retn
0x18003d639  mov     edx, [rsi+14h]
0x18003d63c  add     edx, ecx
0x18003d63e  cmp     edx, ecx
0x18003d640  jb      loc_18003D597
0x18003d646  mov     ebp, [rsi+18h]
0x18003d649  add     ebp, edx
0x18003d64b  cmp     ebp, edx
0x18003d64d  jb      loc_18003D597
0x18003d653  cmp     r8d, ebp
0x18003d656  jb      loc_18003D6FE
0x18003d65c  mov     r14d, dword ptr [rsp+78h+cbDest]
0x18003d664  lea     ebx, [r14+18h]
0x18003d668  lea     ecx, [rbx+rbp]
0x18003d66b  call    MSCryptAlloc
0x18003d670  mov     rdi, rax
0x18003d673  test    rax, rax
0x18003d676  jz      loc_18003D713
0x18003d67c  mov     r8d, ebx; Size
0x18003d67f  xor     edx, edx; Val
0x18003d681  mov     rcx, rax; void *
0x18003d684  call    memset
0x18003d689  lea     rcx, [rbx+rdi]; void *
0x18003d68d  mov     r8d, ebp; Size
0x18003d690  mov     rdx, rsi; Src
0x18003d693  mov     [rdi], rcx
0x18003d696  call    memmove
0x18003d69b  test    r14d, r14d
0x18003d69e  jnz     loc_18003D728
0x18003d6a4  mov     rcx, [rdi]
0x18003d6a7  cmp     dword ptr [rcx+4], 3
0x18003d6ab  jnz     loc_18003D610
0x18003d6b1  jmp     loc_18003D609
0x18003d6b6  mov     ebx, 0C0000023h
0x18003d6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d6c2  lea     rax, WPP_GLOBAL_Control
0x18003d6c9  cmp     rcx, rax
0x18003d6cc  jz      loc_18003D627
0x18003d6d2  mov     eax, [rcx+2Ch]
0x18003d6d5  test    al, 1
0x18003d6d7  jz      loc_18003D627
0x18003d6dd  mov     [rsp+78h+var_48], 2CEh
0x18003d6e5  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d6ec  mov     [rsp+78h+var_50], r8
0x18003d6f1  mov     [rsp+78h+var_58], 0C0000023h
0x18003d6f9  jmp     loc_18003D5D2
0x18003d6fe  mov     ebx, 0C0000023h
0x18003d703  mov     r9d, 2EAh
0x18003d709  mov     ecx, 0C0000023h
0x18003d70e  jmp     loc_18003D5F4
0x18003d713  mov     ebx, 0C0000017h
0x18003d718  mov     r9d, 2FDh
0x18003d71e  mov     ecx, 0C0000017h
0x18003d723  jmp     loc_18003D5F4
0x18003d728  lea     rcx, [rdi+18h]; pszDest
0x18003d72c  mov     rdx, r14; cbDest
0x18003d72f  mov     r8, r12; pszSrc
0x18003d732  mov     [rdi+10h], rcx
0x18003d736  call    StringCbCopyW
0x18003d73b  test    eax, eax
0x18003d73d  jns     loc_18003D6A4
0x18003d743  mov     ebx, 0C000000Dh
0x18003d748  mov     ecx, 0C000000Dh
0x18003d74d  mov     r9d, 311h
0x18003d753  jmp     loc_1800A16FA
0x18003d758  mov     ebx, 0C0000001h
0x18003d75d  mov     ecx, 0C0000001h
0x18003d762  mov     r9d, 322h
0x18003d768  jmp     loc_1800A16FA
0x1800a16fa  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1701  lea     rdx, aStatus; "Status"
0x1800a1708  call    DebugTraceError
0x1800a170d  mov     rcx, rdi; P
0x1800a1710  call    FreeGenericEccKeyParameters
0x1800a1715  nop
0x1800a1716  jmp     loc_18003D627
```
