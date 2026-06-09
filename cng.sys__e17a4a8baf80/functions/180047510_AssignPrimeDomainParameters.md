# AssignPrimeDomainParameters

- ea: `0x180047510`
- end: `0x18004772d`
- name: `AssignPrimeDomainParameters`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180047434`

## callees

- `0x18000e090`
- `0x18001155c`
- `0x1800123d0`
- `0x180047510`
- `0x180047734`
- `0x180050c14`
- `0x180052d04`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x18004757e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800475b4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800476a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a8498`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
    v20 = qword_1800B5C60;
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
0x180047510  push    rbx
0x180047512  push    rbp
0x180047513  push    rsi
0x180047514  push    rdi
0x180047515  push    r12
0x180047517  push    r14
0x180047519  push    r15
0x18004751b  sub     rsp, 40h
0x18004751f  mov     r12, r9
0x180047522  mov     rsi, rdx
0x180047525  mov     r15, rcx
0x180047528  cmp     r8d, 1Ch
0x18004752c  jb      loc_180047676
0x180047532  mov     eax, [rdx+0Ch]
0x180047535  lea     rcx, [rax+rax*4]
0x180047539  mov     eax, 0FFFFFFFFh
0x18004753e  cmp     rcx, rax
0x180047541  ja      short loc_1800475A4
0x180047543  lea     edx, [rcx+1Ch]
0x180047546  cmp     edx, ecx
0x180047548  jb      short loc_180047557
0x18004754a  mov     ecx, [rsi+10h]
0x18004754d  add     ecx, edx
0x18004754f  cmp     ecx, edx
0x180047551  jnb     loc_1800475F9
0x180047557  mov     ebx, 0C0000095h
0x18004755c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047563  lea     rax, WPP_GLOBAL_Control
0x18004756a  cmp     rcx, rax
0x18004756d  jz      short loc_1800475E7
0x18004756f  mov     eax, [rcx+2Ch]
0x180047572  test    al, 1
0x180047574  jz      short loc_1800475E7
0x180047576  mov     [rsp+78h+var_48], 2E1h
0x18004757e  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047585  mov     [rsp+78h+var_50], r8
0x18004758a  mov     [rsp+78h+var_58], 0C0000095h
0x180047592  mov     rcx, [rcx+18h]
0x180047596  lea     r9, aStatus; "Status"
0x18004759d  call    WPP_SF_sDsd
0x1800475a2  jmp     short loc_1800475E7
0x1800475a4  mov     ebx, 0C0000095h
0x1800475a9  mov     r9d, 2D7h
0x1800475af  mov     ecx, 0C0000095h
0x1800475b4  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800475bb  lea     rdx, aStatus; "Status"
0x1800475c2  call    DebugTraceError
0x1800475c7  jmp     short loc_1800475E7
0x1800475c9  lea     rcx, qword_1800B5C60
0x1800475d0  call    SymCryptEcurveAllocate
0x1800475d5  mov     [rdi+8], rax
0x1800475d9  test    rax, rax
0x1800475dc  jz      loc_180047718
0x1800475e2  mov     [r15], rdi
0x1800475e5  xor     ebx, ebx
0x1800475e7  mov     eax, ebx
0x1800475e9  add     rsp, 40h
0x1800475ed  pop     r15
0x1800475ef  pop     r14
0x1800475f1  pop     r12
0x1800475f3  pop     rdi
0x1800475f4  pop     rsi
0x1800475f5  pop     rbp
0x1800475f6  pop     rbx
0x1800475f7  retn
0x1800475f9  mov     edx, [rsi+14h]
0x1800475fc  add     edx, ecx
0x1800475fe  cmp     edx, ecx
0x180047600  jb      loc_180047557
0x180047606  mov     ebp, [rsi+18h]
0x180047609  add     ebp, edx
0x18004760b  cmp     ebp, edx
0x18004760d  jb      loc_180047557
0x180047613  cmp     r8d, ebp
0x180047616  jb      loc_1800476BE
0x18004761c  mov     r14d, dword ptr [rsp+78h+cbDest]
0x180047624  lea     ebx, [r14+18h]
0x180047628  lea     ecx, [rbx+rbp]
0x18004762b  call    MSCryptAlloc
0x180047630  mov     rdi, rax
0x180047633  test    rax, rax
0x180047636  jz      loc_1800476D3
0x18004763c  mov     r8d, ebx; Size
0x18004763f  xor     edx, edx; Val
0x180047641  mov     rcx, rax; void *
0x180047644  call    memset
0x180047649  lea     rcx, [rbx+rdi]; void *
0x18004764d  mov     r8d, ebp; Size
0x180047650  mov     rdx, rsi; Src
0x180047653  mov     [rdi], rcx
0x180047656  call    memmove
0x18004765b  test    r14d, r14d
0x18004765e  jnz     loc_1800476E8
0x180047664  mov     rcx, [rdi]
0x180047667  cmp     dword ptr [rcx+4], 3
0x18004766b  jnz     loc_1800475D0
0x180047671  jmp     loc_1800475C9
0x180047676  mov     ebx, 0C0000023h
0x18004767b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047682  lea     rax, WPP_GLOBAL_Control
0x180047689  cmp     rcx, rax
0x18004768c  jz      loc_1800475E7
0x180047692  mov     eax, [rcx+2Ch]
0x180047695  test    al, 1
0x180047697  jz      loc_1800475E7
0x18004769d  mov     [rsp+78h+var_48], 2CEh
0x1800476a5  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800476ac  mov     [rsp+78h+var_50], r8
0x1800476b1  mov     [rsp+78h+var_58], 0C0000023h
0x1800476b9  jmp     loc_180047592
0x1800476be  mov     ebx, 0C0000023h
0x1800476c3  mov     r9d, 2EAh
0x1800476c9  mov     ecx, 0C0000023h
0x1800476ce  jmp     loc_1800475B4
0x1800476d3  mov     ebx, 0C0000017h
0x1800476d8  mov     r9d, 2FDh
0x1800476de  mov     ecx, 0C0000017h
0x1800476e3  jmp     loc_1800475B4
0x1800476e8  lea     rcx, [rdi+18h]; pszDest
0x1800476ec  mov     rdx, r14; cbDest
0x1800476ef  mov     r8, r12; pszSrc
0x1800476f2  mov     [rdi+10h], rcx
0x1800476f6  call    StringCbCopyW
0x1800476fb  test    eax, eax
0x1800476fd  jns     loc_180047664
0x180047703  mov     ebx, 0C000000Dh
0x180047708  mov     ecx, 0C000000Dh
0x18004770d  mov     r9d, 311h
0x180047713  jmp     loc_1800A8498
0x180047718  mov     ebx, 0C0000001h
0x18004771d  mov     ecx, 0C0000001h
0x180047722  mov     r9d, 322h
0x180047728  jmp     loc_1800A8498
0x1800a8498  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a849f  lea     rdx, aStatus; "Status"
0x1800a84a6  call    DebugTraceError
0x1800a84ab  mov     rcx, rdi; P
0x1800a84ae  call    FreeGenericEccKeyParameters
0x1800a84b3  nop
0x1800a84b4  jmp     loc_1800475E7
```
