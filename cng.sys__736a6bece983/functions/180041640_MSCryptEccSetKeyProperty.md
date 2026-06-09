# MSCryptEccSetKeyProperty

- ea: `0x180041640`
- end: `0x180041946`
- name: `MSCryptEccSetKeyProperty`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180041218`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003e004`
- `0x180041640`
- `0x180041b20`
- `0x180077dc4`
- `0x180077fd4`
- `0x18009f616`

## string_xrefs

- `0x180041657`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004170d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetKeyProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 i; // rdx
  char *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  int Curve; // eax
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD v19[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
    goto LABEL_46;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
    goto LABEL_46;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v9 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 628);
LABEL_46:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          162);
      return v9;
    }
    v11 = byte_1800A8E78;
    if ( !a5 )
      v11 = byte_1800A8DB8;
    if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)&v11[48 * i] )
      break;
  }
  if ( wcscmp_0(a2, L"ECCParameters") )
  {
    if ( !wcscmp_0(a2, L"ECCCurveName") )
    {
      v15 = *(_QWORD *)(a1 + 16) == 0;
      v19[0] = 0;
      v20 = 0;
      if ( !v15 )
      {
        v12 = 3784;
LABEL_15:
        v9 = -1073741637;
        v13 = 3221225659LL;
LABEL_16:
        DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
        return v9;
      }
      Curve = ValidateCurveName(a3, a4, v19, &v20);
      v9 = Curve;
      if ( Curve >= 0 )
      {
        Curve = LoadCurve(a1 + 16, *(unsigned int *)(a1 + 8), v19[0], v20);
        v9 = Curve;
        if ( Curve >= 0 )
          return v9;
        v12 = 3799;
      }
      else
      {
        v12 = 3792;
      }
    }
    else
    {
      if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
      {
        if ( a4 != 4 || !a3 || (v16 = *(_QWORD *)(a1 + 16)) == 0 )
        {
          v9 = -1073741811;
          v12 = 3812;
          v13 = 3221225485LL;
          goto LABEL_16;
        }
        v17 = *(_QWORD *)(v16 + 8);
        if ( *(_DWORD *)(v17 + 12) == *a3 || *(_DWORD *)(v17 + 24) == *a3 )
          return 0;
        v12 = 3825;
        goto LABEL_15;
      }
      if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 196615) > 3 || wcscmp_0(a2, L"PrivKeyVal") )
      {
        v12 = 3846;
        goto LABEL_15;
      }
      Curve = SetEccPrivateKeyVal(a1, a3, a4);
      v9 = Curve;
      if ( Curve >= 0 )
        return v9;
      v12 = 3839;
    }
LABEL_19:
    v13 = (unsigned int)Curve;
    goto LABEL_16;
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    v12 = 3760;
    goto LABEL_15;
  }
  Curve = AssignGenericDomainParameters((int)a1 + 16, *(_DWORD *)(a1 + 8), (_DWORD)a3, a4, 0, 0);
  v9 = Curve;
  if ( Curve < 0 )
  {
    v12 = 3767;
    goto LABEL_19;
  }
  return v9;
}

```

## disassembly

```asm
0x180041640  push    rbx
0x180041642  push    rbp
0x180041643  push    rsi
0x180041644  push    rdi
0x180041645  push    r12
0x180041647  push    r14
0x180041649  sub     rsp, 58h
0x18004164d  lea     r12, WPP_GLOBAL_Control
0x180041654  mov     r14d, r9d
0x180041657  lea     rdi, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004165e  mov     rbx, r8
0x180041661  mov     rbp, rdx
0x180041664  mov     rsi, rcx
0x180041667  test    rcx, rcx
0x18004166a  jz      loc_1800418C3
0x180041670  cmp     dword ptr [rcx+4], 4D534B59h
0x180041677  jz      short loc_1800416A8
0x180041679  mov     ebx, 0C000000Dh
0x18004167e  mov     esi, ebx
0x180041680  mov     rcx, cs:WPP_GLOBAL_Control
0x180041687  cmp     rcx, r12
0x18004168a  jz      loc_180041902
0x180041690  mov     eax, [rcx+2Ch]
0x180041693  test    al, 1
0x180041695  jz      loc_180041902
0x18004169b  mov     [rsp+88h+var_58], 23Ch
0x1800416a3  jmp     loc_1800418E5
0x1800416a8  xor     edx, edx
0x1800416aa  cmp     edx, 4
0x1800416ad  jnb     loc_1800418A0
0x1800416b3  cmp     [rsp+88h+arg_20], 0
0x1800416bb  lea     rax, byte_1800A8DB8
0x1800416c2  lea     rcx, byte_1800A8E78
0x1800416c9  cmovz   rcx, rax
0x1800416cd  lea     rax, [rdx+rdx*2]
0x1800416d1  add     rax, rax
0x1800416d4  mov     eax, [rcx+rax*8]
0x1800416d7  cmp     [rsi+8], eax
0x1800416da  jz      short loc_1800416E0
0x1800416dc  inc     edx
0x1800416de  jmp     short loc_1800416AA
0x1800416e0  lea     rdx, aEccparameters; "ECCParameters"
0x1800416e7  mov     rcx, rbp; Str1
0x1800416ea  call    wcscmp_0
0x1800416ef  test    eax, eax
0x1800416f1  jnz     short loc_180041758
0x1800416f3  lea     rcx, [rsi+10h]
0x1800416f7  cmp     qword ptr [rcx], 0
0x1800416fb  jz      short loc_180041725
0x1800416fd  mov     r9d, 0EB0h
0x180041703  mov     ebx, 0C00000BBh
0x180041708  mov     ecx, 0C00000BBh
0x18004170d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041714  lea     rdx, aStatus; "Status"
0x18004171b  call    DebugTraceError
0x180041720  jmp     loc_180041936
0x180041725  mov     edx, [rsi+8]
0x180041728  mov     r9d, r14d
0x18004172b  mov     dword ptr [rsp+88h+var_60], 0
0x180041733  mov     r8, rbx
0x180041736  mov     [rsp+88h+var_68], 0
0x18004173f  call    AssignGenericDomainParameters
0x180041744  mov     ebx, eax
0x180041746  test    eax, eax
0x180041748  jns     loc_180041936
0x18004174e  mov     r9d, 0EB7h
0x180041754  mov     ecx, eax
0x180041756  jmp     short loc_18004170D
0x180041758  lea     rdx, aEcccurvename; "ECCCurveName"
0x18004175f  mov     rcx, rbp; Str1
0x180041762  call    wcscmp_0
0x180041767  test    eax, eax
0x180041769  jnz     short loc_1800417E1
0x18004176b  cmp     qword ptr [rsi+10h], 0
0x180041770  mov     [rsp+88h+var_48], 0
0x180041779  mov     [rsp+88h+arg_0], eax
0x180041780  jz      short loc_18004178D
0x180041782  mov     r9d, 0EC8h
0x180041788  jmp     loc_180041703
0x18004178d  lea     r9, [rsp+88h+arg_0]
0x180041795  mov     edx, r14d
0x180041798  lea     r8, [rsp+88h+var_48]
0x18004179d  mov     rcx, rbx
0x1800417a0  call    ValidateCurveName
0x1800417a5  mov     ebx, eax
0x1800417a7  test    eax, eax
0x1800417a9  jns     short loc_1800417B3
0x1800417ab  mov     r9d, 0ED0h
0x1800417b1  jmp     short loc_180041754
0x1800417b3  mov     r9d, [rsp+88h+arg_0]
0x1800417bb  lea     rcx, [rsi+10h]
0x1800417bf  mov     r8, [rsp+88h+var_48]
0x1800417c4  mov     edx, [rsi+8]
0x1800417c7  call    LoadCurve
0x1800417cc  mov     ebx, eax
0x1800417ce  test    eax, eax
0x1800417d0  jns     loc_180041936
0x1800417d6  mov     r9d, 0ED7h
0x1800417dc  jmp     loc_180041754
0x1800417e1  lea     rdx, aKeylength; "KeyLength"
0x1800417e8  mov     rcx, rbp; Str1
0x1800417eb  call    wcscmp_0
0x1800417f0  test    eax, eax
0x1800417f2  jz      short loc_180041855
0x1800417f4  lea     rdx, aKeystrength; "KeyStrength"
0x1800417fb  mov     rcx, rbp; Str1
0x1800417fe  call    wcscmp_0
0x180041803  test    eax, eax
0x180041805  jz      short loc_180041855
0x180041807  mov     eax, [rsi+8]
0x18004180a  sub     eax, 30007h
0x18004180f  cmp     eax, 3
0x180041812  ja      short loc_18004184A
0x180041814  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x18004181b  mov     rcx, rbp; Str1
0x18004181e  call    wcscmp_0
0x180041823  test    eax, eax
0x180041825  jnz     short loc_18004184A
0x180041827  mov     r8d, r14d
0x18004182a  mov     rdx, rbx
0x18004182d  mov     rcx, rsi
0x180041830  call    SetEccPrivateKeyVal
0x180041835  mov     ebx, eax
0x180041837  test    eax, eax
0x180041839  jns     loc_180041936
0x18004183f  mov     r9d, 0EFFh
0x180041845  jmp     loc_180041754
0x18004184a  mov     r9d, 0F06h
0x180041850  jmp     loc_180041703
0x180041855  cmp     r14d, 4
0x180041859  jnz     short loc_18004188B
0x18004185b  test    rbx, rbx
0x18004185e  jz      short loc_18004188B
0x180041860  mov     rax, [rsi+10h]
0x180041864  test    rax, rax
0x180041867  jz      short loc_18004188B
0x180041869  mov     rdx, [rax+8]
0x18004186d  mov     ecx, [rbx]
0x18004186f  cmp     [rdx+0Ch], ecx
0x180041872  jz      short loc_180041884
0x180041874  cmp     [rdx+18h], ecx
0x180041877  jz      short loc_180041884
0x180041879  mov     r9d, 0EF1h
0x18004187f  jmp     loc_180041703
0x180041884  xor     ebx, ebx
0x180041886  jmp     loc_180041936
0x18004188b  mov     ebx, 0C000000Dh
0x180041890  mov     r9d, 0EE4h
0x180041896  mov     ecx, 0C000000Dh
0x18004189b  jmp     loc_18004170D
0x1800418a0  mov     ebx, 0C000000Dh
0x1800418a5  lea     rdx, aStatus; "Status"
0x1800418ac  mov     r9d, 274h
0x1800418b2  mov     r8, rdi
0x1800418b5  mov     ecx, 0C000000Dh
0x1800418ba  mov     esi, ebx
0x1800418bc  call    DebugTraceError
0x1800418c1  jmp     short loc_180041902
0x1800418c3  mov     ebx, 0C000000Dh
0x1800418c8  mov     esi, ebx
0x1800418ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418d1  cmp     rcx, r12
0x1800418d4  jz      short loc_180041902
0x1800418d6  mov     eax, [rcx+2Ch]
0x1800418d9  test    al, 1
0x1800418db  jz      short loc_180041902
0x1800418dd  mov     [rsp+88h+var_58], 233h
0x1800418e5  mov     rcx, [rcx+18h]
0x1800418e9  lea     r9, aStatus; "Status"
0x1800418f0  mov     [rsp+88h+var_60], rdi
0x1800418f5  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x1800418fd  call    WPP_SF_sDsd
0x180041902  mov     rcx, cs:WPP_GLOBAL_Control
0x180041909  cmp     rcx, r12
0x18004190c  jz      short loc_180041936
0x18004190e  mov     eax, [rcx+2Ch]
0x180041911  test    al, 1
0x180041913  jz      short loc_180041936
0x180041915  mov     rcx, [rcx+18h]
0x180041919  lea     r9, aStatus; "Status"
0x180041920  mov     [rsp+88h+var_58], 0EA2h
0x180041928  mov     [rsp+88h+var_60], rdi
0x18004192d  mov     dword ptr [rsp+88h+var_68], esi
0x180041931  call    WPP_SF_sDsd
0x180041936  mov     eax, ebx
0x180041938  add     rsp, 58h
0x18004193c  pop     r14
0x18004193e  pop     r12
0x180041940  pop     rdi
0x180041941  pop     rsi
0x180041942  pop     rbp
0x180041943  pop     rbx
0x180041944  retn
```
