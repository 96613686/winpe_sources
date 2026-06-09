# ApplySignaturePadding

- ea: `0x180068164`
- end: `0x1800684f8`
- name: `ApplySignaturePadding`
- size: `916`
- prototype: `__int64 __fastcall(char, _QWORD *, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180059d40`

## callees

- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180067990`
- `0x180067a38`
- `0x180067d4c`
- `0x180067ec4`
- `0x180068164`

## string_xrefs

- `0x1800681bc`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800681ec`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800682ee`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800683ba`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800684bc`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplySignaturePadding(char a1, _QWORD *a2, __int64 a3, int a4, __int64 a5, int a6)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  NTSTATUS Property; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-10h] BYREF
  UCHAR v22[4]; // [rsp+54h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+90h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v22 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) == 0 )
    {
      v14 = 1504;
      goto LABEL_44;
    }
    if ( !a2 || !*a2 )
    {
      v9 = 1447;
      goto LABEL_4;
    }
    if ( (int)CachedOpenAlgorithmProvider(&hObject) < 0 )
    {
      v10 = -1073741637;
      DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 1459);
      goto LABEL_9;
    }
    v6 = hObject;
    Property = BCryptGetProperty(hObject, L"ObjectLength", v22, 4u, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1471;
      goto LABEL_12;
    }
    Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1483;
      goto LABEL_12;
    }
    Property = ApplyPSSPaddingSalted(v6, *(unsigned int *)pbOutput, *(unsigned int *)v22);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1497;
      goto LABEL_12;
    }
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v9 = 1329;
LABEL_4:
    v10 = -1073741811;
    v11 = 3221225485LL;
LABEL_5:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v9);
    return v10;
  }
  if ( !*a2 )
  {
    v19 = ApplyPKCS1SigningFormat(0, 0, a5, a6, 0);
    v10 = v19;
    if ( v19 < 0 )
    {
      v9 = 1434;
      v11 = (unsigned int)v19;
      goto LABEL_5;
    }
    goto LABEL_40;
  }
  v12 = CachedOpenAlgorithmProvider(&hObject);
  if ( v12 < 0 )
  {
    DebugTraceError((unsigned int)v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 1342);
    v10 = -1073741637;
LABEL_9:
    v6 = hObject;
    goto LABEL_46;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v10 = Property;
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput != a4 )
    {
      v14 = 1361;
LABEL_44:
      v15 = 3221225485LL;
      v10 = -1073741811;
      goto LABEL_45;
    }
    Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
    v10 = Property;
    if ( Property < 0 )
    {
      v14 = 1373;
      goto LABEL_12;
    }
    v7 = MSCryptAlloc(cbOutput);
    if ( !v7 )
    {
      v10 = -1073741801;
      v14 = 1383;
      v15 = 3221225495LL;
      goto LABEL_45;
    }
    v16 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 1395;
LABEL_21:
      v18 = (unsigned int)v16;
LABEL_22:
      DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v17);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v10 = -1073741595;
      v17 = 1404;
      v18 = 3221225701LL;
      goto LABEL_22;
    }
    v16 = ApplyPKCS1SigningFormat(*(void **)(*(_QWORD *)(v7 + 8) + 8LL), **(unsigned int **)(v7 + 8), a5, a6, 1);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 1418;
      goto LABEL_21;
    }
LABEL_40:
    v10 = 0;
    if ( !v7 )
      goto LABEL_46;
    goto LABEL_41;
  }
  v14 = 1355;
LABEL_12:
  v15 = (unsigned int)Property;
LABEL_45:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v14);
LABEL_46:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v10;
}

```

## disassembly

```asm
0x180068164  mov     [rsp-28h+arg_8], rbx
0x180068169  mov     [rsp-28h+arg_10], rsi
0x18006816e  push    rbp
0x18006816f  push    rdi
0x180068170  push    r12
0x180068172  push    r14
0x180068174  push    r15
0x180068176  mov     rbp, rsp
0x180068179  sub     rsp, 60h
0x18006817d  xor     esi, esi
0x18006817f  xor     edi, edi
0x180068181  mov     [rbp+hObject], rsi
0x180068185  mov     r15d, r9d
0x180068188  mov     dword ptr [rbp+var_C], esi
0x18006818b  mov     r12, r8
0x18006818e  mov     dword ptr [rbp+pbOutput], esi
0x180068191  mov     r14, rdx
0x180068194  mov     [rbp+cbOutput], esi
0x180068197  test    cl, 2
0x18006819a  jz      loc_180068389
0x1800681a0  test    rdx, rdx
0x1800681a3  jnz     short loc_1800681CD
0x1800681a5  mov     r9d, 531h
0x1800681ab  mov     ebx, 0C000000Dh
0x1800681b0  mov     ecx, 0C000000Dh
0x1800681b5  lea     rdx, aStatus; "Status"
0x1800681bc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800681c3  call    DebugTraceError
0x1800681c8  jmp     loc_1800684DC
0x1800681cd  mov     rdx, [rdx]
0x1800681d0  test    rdx, rdx
0x1800681d3  jz      loc_180068355
0x1800681d9  lea     rcx, [rbp+hObject]
0x1800681dd  call    CachedOpenAlgorithmProvider
0x1800681e2  test    eax, eax
0x1800681e4  jns     short loc_18006820F
0x1800681e6  mov     r9d, 53Eh
0x1800681ec  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800681f3  lea     rdx, aStatus; "Status"
0x1800681fa  mov     ecx, eax
0x1800681fc  call    DebugTraceError
0x180068201  mov     ebx, 0C00000BBh
0x180068206  mov     rsi, [rbp+hObject]
0x18006820a  jmp     loc_1800684CF
0x18006820f  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180068213  lea     rax, [rbp+cbOutput]
0x180068217  mov     rsi, [rbp+hObject]
0x18006821b  lea     r8, [rbp+pbOutput]; pbOutput
0x18006821f  mov     rcx, rsi; hObject
0x180068222  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180068227  mov     r9d, 4; cbOutput
0x18006822d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068234  call    BCryptGetProperty
0x180068239  mov     ebx, eax
0x18006823b  test    eax, eax
0x18006823d  jns     short loc_18006824C
0x18006823f  mov     r9d, 54Bh
0x180068245  mov     ecx, eax
0x180068247  jmp     loc_1800684BC
0x18006824c  cmp     dword ptr [rbp+pbOutput], r15d
0x180068250  jz      short loc_18006825D
0x180068252  mov     r9d, 551h
0x180068258  jmp     loc_1800684B2
0x18006825d  lea     rax, [rbp+cbOutput]
0x180068261  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180068265  xor     r9d, r9d; cbOutput
0x180068268  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18006826d  xor     r8d, r8d; pbOutput
0x180068270  lea     rdx, aHashoidlist; "HashOIDList"
0x180068277  mov     rcx, rsi; hObject
0x18006827a  call    BCryptGetProperty
0x18006827f  mov     ebx, eax
0x180068281  test    eax, eax
0x180068283  jns     short loc_18006828D
0x180068285  mov     r9d, 55Dh
0x18006828b  jmp     short loc_180068245
0x18006828d  mov     ecx, [rbp+cbOutput]
0x180068290  call    MSCryptAlloc
0x180068295  mov     rdi, rax
0x180068298  test    rax, rax
0x18006829b  jnz     short loc_1800682B2
0x18006829d  mov     ebx, 0C0000017h
0x1800682a2  mov     r9d, 567h
0x1800682a8  mov     ecx, 0C0000017h
0x1800682ad  jmp     loc_1800684BC
0x1800682b2  mov     r9d, [rbp+cbOutput]; cbOutput
0x1800682b6  lea     rax, [rbp+cbOutput]
0x1800682ba  mov     [rsp+60h+dwFlags], 0; dwFlags
0x1800682c2  lea     rdx, aHashoidlist; "HashOIDList"
0x1800682c9  mov     r8, rdi; pbOutput
0x1800682cc  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800682d1  mov     rcx, rsi; hObject
0x1800682d4  call    BCryptGetProperty
0x1800682d9  mov     ebx, eax
0x1800682db  test    eax, eax
0x1800682dd  jns     short loc_1800682FF
0x1800682df  mov     r9d, 573h
0x1800682e5  mov     ecx, eax
0x1800682e7  lea     rdx, aStatus; "Status"
0x1800682ee  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800682f5  call    DebugTraceError
0x1800682fa  jmp     loc_180068497
0x1800682ff  cmp     dword ptr [rdi], 0
0x180068302  jnz     short loc_180068316
0x180068304  mov     ebx, 0C00000E5h
0x180068309  mov     r9d, 57Ch
0x18006830f  mov     ecx, 0C00000E5h
0x180068314  jmp     short loc_1800682E7
0x180068316  mov     rcx, [rdi+8]
0x18006831a  mov     r9d, r15d
0x18006831d  mov     eax, [rbp+arg_28]
0x180068320  mov     r8, r12
0x180068323  mov     [rsp+60h+var_30], 1; int
0x18006832b  mov     [rsp+60h+dwFlags], eax; int
0x18006832f  mov     edx, [rcx]; Size
0x180068331  mov     rax, [rbp+arg_20]
0x180068335  mov     rcx, [rcx+8]; Src
0x180068339  mov     [rsp+60h+pcbResult], rax; __int64
0x18006833e  call    ApplyPKCS1SigningFormat
0x180068343  mov     ebx, eax
0x180068345  test    eax, eax
0x180068347  jns     loc_180068490
0x18006834d  mov     r9d, 58Ah
0x180068353  jmp     short loc_1800682E5
0x180068355  mov     eax, [rbp+arg_28]
0x180068358  xor     edx, edx; Size
0x18006835a  mov     [rsp+60h+var_30], esi; int
0x18006835e  xor     ecx, ecx; Src
0x180068360  mov     [rsp+60h+dwFlags], eax; int
0x180068364  mov     rax, [rbp+arg_20]
0x180068368  mov     [rsp+60h+pcbResult], rax; __int64
0x18006836d  call    ApplyPKCS1SigningFormat
0x180068372  mov     ebx, eax
0x180068374  test    eax, eax
0x180068376  jns     loc_180068490
0x18006837c  mov     r9d, 59Ah
0x180068382  mov     ecx, eax
0x180068384  jmp     loc_1800681B5
0x180068389  test    cl, 8
0x18006838c  jz      loc_1800684AC
0x180068392  test    r14, r14
0x180068395  jz      loc_1800684A1
0x18006839b  mov     rdx, [rdx]
0x18006839e  test    rdx, rdx
0x1800683a1  jz      loc_1800684A1
0x1800683a7  lea     rcx, [rbp+hObject]
0x1800683ab  call    CachedOpenAlgorithmProvider
0x1800683b0  test    eax, eax
0x1800683b2  jns     short loc_1800683DC
0x1800683b4  mov     r9d, 5B3h
0x1800683ba  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800683c1  lea     rdx, aStatus; "Status"
0x1800683c8  mov     ecx, 0C00000BBh
0x1800683cd  mov     ebx, 0C00000BBh
0x1800683d2  call    DebugTraceError
0x1800683d7  jmp     loc_180068206
0x1800683dc  mov     [rsp+60h+dwFlags], esi; dwFlags
0x1800683e0  lea     rax, [rbp+cbOutput]
0x1800683e4  mov     rsi, [rbp+hObject]
0x1800683e8  lea     r8, [rbp+var_C]; pbOutput
0x1800683ec  mov     rcx, rsi; hObject
0x1800683ef  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800683f4  mov     r9d, 4; cbOutput
0x1800683fa  lea     rdx, aObjectlength; "ObjectLength"
0x180068401  call    BCryptGetProperty
0x180068406  mov     ebx, eax
0x180068408  test    eax, eax
0x18006840a  jns     short loc_180068417
0x18006840c  mov     r9d, 5BFh
0x180068412  jmp     loc_180068245
0x180068417  lea     rax, [rbp+cbOutput]
0x18006841b  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18006841f  mov     r9d, 4; cbOutput
0x180068425  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18006842a  lea     r8, [rbp+pbOutput]; pbOutput
0x18006842e  mov     rcx, rsi; hObject
0x180068431  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068438  call    BCryptGetProperty
0x18006843d  mov     ebx, eax
0x18006843f  test    eax, eax
0x180068441  jns     short loc_18006844E
0x180068443  mov     r9d, 5CBh
0x180068449  jmp     loc_180068245
0x18006844e  mov     eax, [rbp+arg_28]
0x180068451  mov     rcx, rsi
0x180068454  mov     r8d, dword ptr [rbp+var_C]
0x180068458  mov     edx, dword ptr [rbp+pbOutput]
0x18006845b  mov     [rsp+60h+var_20], eax
0x18006845f  mov     rax, [rbp+arg_20]
0x180068463  mov     [rsp+60h+var_28], rax
0x180068468  mov     eax, [r14+8]
0x18006846c  mov     [rsp+60h+var_30], r15d
0x180068471  mov     qword ptr [rsp+60h+dwFlags], r12
0x180068476  mov     dword ptr [rsp+60h+pcbResult], eax
0x18006847a  call    ApplyPSSPaddingSalted
0x18006847f  mov     ebx, eax
0x180068481  test    eax, eax
0x180068483  jns     short loc_180068490
0x180068485  mov     r9d, 5D9h
0x18006848b  jmp     loc_180068245
0x180068490  xor     ebx, ebx
0x180068492  test    rdi, rdi
0x180068495  jz      short loc_1800684CF
0x180068497  mov     rcx, rdi; P
0x18006849a  call    MSCryptFree
0x18006849f  jmp     short loc_1800684CF
0x1800684a1  mov     r9d, 5A7h
0x1800684a7  jmp     loc_1800681AB
0x1800684ac  mov     r9d, 5E0h
0x1800684b2  mov     ecx, 0C000000Dh
0x1800684b7  mov     ebx, 0C000000Dh
0x1800684bc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800684c3  lea     rdx, aStatus; "Status"
0x1800684ca  call    DebugTraceError
0x1800684cf  test    rsi, rsi
0x1800684d2  jz      short loc_1800684DC
0x1800684d4  mov     rcx, rsi; hAlgorithm
0x1800684d7  call    CachedCloseAlgorithmProvider
0x1800684dc  lea     r11, [rsp+60h+var_s0]
0x1800684e1  mov     eax, ebx
0x1800684e3  mov     rbx, [r11+38h]
0x1800684e7  mov     rsi, [r11+40h]
0x1800684eb  mov     rsp, r11
0x1800684ee  pop     r15
0x1800684f0  pop     r14
0x1800684f2  pop     r12
0x1800684f4  pop     rdi
0x1800684f5  pop     rbp
0x1800684f6  retn
```
