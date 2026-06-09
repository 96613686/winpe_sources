# AssignPrimeDomainParameters

- ea: `0x18003e0e0`
- end: `0x18003e2fd`
- name: `AssignPrimeDomainParameters`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003e004`

## callees

- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x18003e0e0`
- `0x18003e304`
- `0x1800475b4`
- `0x1800496a4`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x18003e14e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003e184`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003e275`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a352a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall AssignPrimeDomainParameters(
        wchar_t **a1,
        unsigned int *a2,
        __int64 a3,
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

  if ( (unsigned int)a3 < 0x1C )
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
  if ( (unsigned int)a3 < v16 )
  {
    v11 = -1073741789;
    v12 = 746;
    v13 = 3221225507LL;
    goto LABEL_10;
  }
  v17 = cbDest + 24;
  v18 = (wchar_t *)MSCryptAlloc((unsigned int)v17 + v16, v9, a3, a4);
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
    v20 = qword_1800B0C60;
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
0x18003e0e0  push    rbx
0x18003e0e2  push    rbp
0x18003e0e3  push    rsi
0x18003e0e4  push    rdi
0x18003e0e5  push    r12
0x18003e0e7  push    r14
0x18003e0e9  push    r15
0x18003e0eb  sub     rsp, 40h
0x18003e0ef  mov     r12, r9
0x18003e0f2  mov     rsi, rdx
0x18003e0f5  mov     r15, rcx
0x18003e0f8  cmp     r8d, 1Ch
0x18003e0fc  jb      loc_18003E246
0x18003e102  mov     eax, [rdx+0Ch]
0x18003e105  lea     rcx, [rax+rax*4]
0x18003e109  mov     eax, 0FFFFFFFFh
0x18003e10e  cmp     rcx, rax
0x18003e111  ja      short loc_18003E174
0x18003e113  lea     edx, [rcx+1Ch]
0x18003e116  cmp     edx, ecx
0x18003e118  jb      short loc_18003E127
0x18003e11a  mov     ecx, [rsi+10h]
0x18003e11d  add     ecx, edx
0x18003e11f  cmp     ecx, edx
0x18003e121  jnb     loc_18003E1C9
0x18003e127  mov     ebx, 0C0000095h
0x18003e12c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e133  lea     rax, WPP_GLOBAL_Control
0x18003e13a  cmp     rcx, rax
0x18003e13d  jz      short loc_18003E1B7
0x18003e13f  mov     eax, [rcx+2Ch]
0x18003e142  test    al, 1
0x18003e144  jz      short loc_18003E1B7
0x18003e146  mov     [rsp+78h+var_48], 2E1h
0x18003e14e  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003e155  mov     [rsp+78h+var_50], r8
0x18003e15a  mov     [rsp+78h+var_58], 0C0000095h
0x18003e162  mov     rcx, [rcx+18h]
0x18003e166  lea     r9, aStatus; "Status"
0x18003e16d  call    WPP_SF_sDsd
0x18003e172  jmp     short loc_18003E1B7
0x18003e174  mov     ebx, 0C0000095h
0x18003e179  mov     r9d, 2D7h
0x18003e17f  mov     ecx, 0C0000095h
0x18003e184  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003e18b  lea     rdx, aStatus; "Status"
0x18003e192  call    DebugTraceError
0x18003e197  jmp     short loc_18003E1B7
0x18003e199  lea     rcx, qword_1800B0C60
0x18003e1a0  call    SymCryptEcurveAllocate
0x18003e1a5  mov     [rdi+8], rax
0x18003e1a9  test    rax, rax
0x18003e1ac  jz      loc_18003E2E8
0x18003e1b2  mov     [r15], rdi
0x18003e1b5  xor     ebx, ebx
0x18003e1b7  mov     eax, ebx
0x18003e1b9  add     rsp, 40h
0x18003e1bd  pop     r15
0x18003e1bf  pop     r14
0x18003e1c1  pop     r12
0x18003e1c3  pop     rdi
0x18003e1c4  pop     rsi
0x18003e1c5  pop     rbp
0x18003e1c6  pop     rbx
0x18003e1c7  retn
0x18003e1c9  mov     edx, [rsi+14h]
0x18003e1cc  add     edx, ecx
0x18003e1ce  cmp     edx, ecx
0x18003e1d0  jb      loc_18003E127
0x18003e1d6  mov     ebp, [rsi+18h]
0x18003e1d9  add     ebp, edx
0x18003e1db  cmp     ebp, edx
0x18003e1dd  jb      loc_18003E127
0x18003e1e3  cmp     r8d, ebp
0x18003e1e6  jb      loc_18003E28E
0x18003e1ec  mov     r14d, dword ptr [rsp+78h+cbDest]
0x18003e1f4  lea     ebx, [r14+18h]
0x18003e1f8  lea     ecx, [rbx+rbp]
0x18003e1fb  call    MSCryptAlloc
0x18003e200  mov     rdi, rax
0x18003e203  test    rax, rax
0x18003e206  jz      loc_18003E2A3
0x18003e20c  mov     r8d, ebx; Size
0x18003e20f  xor     edx, edx; Val
0x18003e211  mov     rcx, rax; void *
0x18003e214  call    memset
0x18003e219  lea     rcx, [rbx+rdi]; void *
0x18003e21d  mov     r8d, ebp; Size
0x18003e220  mov     rdx, rsi; Src
0x18003e223  mov     [rdi], rcx
0x18003e226  call    memmove
0x18003e22b  test    r14d, r14d
0x18003e22e  jnz     loc_18003E2B8
0x18003e234  mov     rcx, [rdi]
0x18003e237  cmp     dword ptr [rcx+4], 3
0x18003e23b  jnz     loc_18003E1A0
0x18003e241  jmp     loc_18003E199
0x18003e246  mov     ebx, 0C0000023h
0x18003e24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e252  lea     rax, WPP_GLOBAL_Control
0x18003e259  cmp     rcx, rax
0x18003e25c  jz      loc_18003E1B7
0x18003e262  mov     eax, [rcx+2Ch]
0x18003e265  test    al, 1
0x18003e267  jz      loc_18003E1B7
0x18003e26d  mov     [rsp+78h+var_48], 2CEh
0x18003e275  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003e27c  mov     [rsp+78h+var_50], r8
0x18003e281  mov     [rsp+78h+var_58], 0C0000023h
0x18003e289  jmp     loc_18003E162
0x18003e28e  mov     ebx, 0C0000023h
0x18003e293  mov     r9d, 2EAh
0x18003e299  mov     ecx, 0C0000023h
0x18003e29e  jmp     loc_18003E184
0x18003e2a3  mov     ebx, 0C0000017h
0x18003e2a8  mov     r9d, 2FDh
0x18003e2ae  mov     ecx, 0C0000017h
0x18003e2b3  jmp     loc_18003E184
0x18003e2b8  lea     rcx, [rdi+18h]; pszDest
0x18003e2bc  mov     rdx, r14; cbDest
0x18003e2bf  mov     r8, r12; pszSrc
0x18003e2c2  mov     [rdi+10h], rcx
0x18003e2c6  call    StringCbCopyW
0x18003e2cb  test    eax, eax
0x18003e2cd  jns     loc_18003E234
0x18003e2d3  mov     ebx, 0C000000Dh
0x18003e2d8  mov     ecx, 0C000000Dh
0x18003e2dd  mov     r9d, 311h
0x18003e2e3  jmp     loc_1800A352A
0x18003e2e8  mov     ebx, 0C0000001h
0x18003e2ed  mov     ecx, 0C0000001h
0x18003e2f2  mov     r9d, 322h
0x18003e2f8  jmp     loc_1800A352A
0x1800a352a  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3531  lea     rdx, aStatus; "Status"
0x1800a3538  call    DebugTraceError
0x1800a353d  mov     rcx, rdi; P
0x1800a3540  call    FreeGenericEccKeyParameters
0x1800a3545  nop
0x1800a3546  jmp     loc_18003E1B7
```
