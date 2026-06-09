# MSCryptKDGetProperty

- ea: `0x180005220`
- end: `0x180005586`
- name: `MSCryptKDGetProperty`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005220`
- `0x18000743c`
- `0x1800082b0`
- `0x18007553c`
- `0x18009f616`
- `0x18009f780`

## string_xrefs

- `0x18000536d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800053b3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800053fe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005460`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000546f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800054ab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800054cd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005509`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180005521`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000552f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800a0a72`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800a0ad9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGetProperty(
        _DWORD *a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  unsigned int *v6; // r15
  size_t v8; // r13
  unsigned int v11; // esi
  int v12; // ebp
  int v13; // edi
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // edi
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // r9
  const wchar_t *v21; // rdx
  __int64 v22; // rsi

  v6 = a5;
  v8 = a4;
  v11 = *a5;
  LODWORD(a5) = *a5;
  if ( !a1 )
  {
    v16 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        117);
    goto LABEL_14;
  }
  if ( a6 )
  {
    v16 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      892);
    goto LABEL_14;
  }
  v12 = a1[1];
  if ( v12 != 1297301836 && v12 != 1297304409 )
  {
    v20 = 208;
LABEL_35:
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v20);
    v16 = -1073741816;
    goto LABEL_14;
  }
  v13 = a1[2];
  if ( (unsigned int)(v13 - 393217) > 6 )
  {
    v20 = 221;
    goto LABEL_35;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    switch ( v13 )
    {
      case 393217:
        v21 = L"SP800_108_CTR_HMAC";
        goto LABEL_49;
      case 393218:
        v21 = L"SP800_56A_CONCAT";
        goto LABEL_49;
      case 393219:
        v21 = L"PBKDF2";
        goto LABEL_49;
      case 393220:
        v21 = L"CAPI_KDF";
        goto LABEL_49;
      case 393221:
        v21 = L"TLS1_1_KDF";
        goto LABEL_49;
      case 393222:
        v21 = L"TLS1_2_KDF";
        goto LABEL_49;
      case 393223:
        v21 = L"HKDF";
LABEL_49:
        v22 = -1;
        while ( v21[++v22] != 0 )
          ;
        v11 = 2 * v22 + 2;
        if ( !a3 )
          goto LABEL_15;
        if ( (unsigned int)v8 < v11 )
        {
          v16 = -1073741789;
          goto LABEL_14;
        }
        memmove(a3, v21, v8);
        break;
      default:
        v16 = -1073741637;
        DebugTraceError(
          3221225659LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          952);
        goto LABEL_14;
    }
    goto LABEL_15;
  }
  if ( v12 != 1297301836 )
  {
    v18 = MSCryptKDGetKeyProperty(a1, a2, a3, (unsigned int)v8, &a5);
    v16 = v18;
    if ( v18 < 0 )
      DebugTraceError(
        (unsigned int)v18,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        1007);
    v11 = (unsigned int)a5;
    goto LABEL_14;
  }
  if ( *a1 != 20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v14,
        v15,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
    goto LABEL_26;
  }
  if ( (unsigned int)(v13 - 393217) > 6 )
  {
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      286);
LABEL_26:
    v16 = -1073741816;
    v19 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v14,
        v15,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        96);
    goto LABEL_29;
  }
  if ( wcscmp_0(a2, L"KeyLengths") )
  {
    if ( wcscmp_0(a2, L"ObjectLength") )
    {
      v16 = -1073741637;
      v19 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        712);
      goto LABEL_29;
    }
    v11 = 4;
    if ( a3 )
    {
      if ( (unsigned int)v8 >= 4 )
      {
        v16 = 0;
        *a3 = a1[3];
        goto LABEL_14;
      }
      v16 = -1073741789;
      v19 = -1073741789;
LABEL_29:
      DebugTraceError(
        v19,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        991);
      goto LABEL_14;
    }
LABEL_15:
    v16 = 0;
    goto LABEL_14;
  }
  if ( !a3 )
  {
    v11 = 12;
    v16 = 0;
    goto LABEL_14;
  }
  if ( (unsigned int)v8 < 0xC )
  {
    v16 = -1073741789;
    v19 = -1073741789;
    v11 = 12;
    goto LABEL_29;
  }
  switch ( v13 )
  {
    case 393217:
    case 393218:
    case 393219:
    case 393220:
    case 393221:
    case 393222:
    case 393223:
      v16 = 0;
      v11 = 12;
      *a3 = 0;
      a3[1] = 0x4000;
      a3[2] = 8;
      break;
    default:
      v16 = -1073741637;
      v19 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        683);
      v11 = 12;
      goto LABEL_29;
  }
LABEL_14:
  *v6 = v11;
  return v16;
}

```

## disassembly

```asm
0x180005220  push    rbx
0x180005222  push    rbp
0x180005223  push    rsi
0x180005224  push    rdi
0x180005225  push    r12
0x180005227  push    r13
0x180005229  push    r14
0x18000522b  push    r15
0x18000522d  sub     rsp, 48h
0x180005231  mov     r15, [rsp+88h+arg_20]
0x180005239  mov     r12, r8
0x18000523c  mov     r13d, r9d
0x18000523f  mov     r14, rdx
0x180005242  mov     rbx, rcx
0x180005245  mov     esi, [r15]
0x180005248  mov     dword ptr [rsp+88h+arg_20], esi
0x18000524f  test    rcx, rcx
0x180005252  jz      loc_180005388
0x180005258  cmp     [rsp+88h+arg_28], 0
0x180005260  jnz     loc_180005469
0x180005266  mov     ebp, [rcx+4]
0x180005269  cmp     ebp, 4D53414Ch
0x18000526f  jnz     loc_180005491
0x180005275  mov     edi, [rcx+8]
0x180005278  lea     eax, [rdi-60001h]
0x18000527e  cmp     eax, 6
0x180005281  ja      loc_1800054A5
0x180005287  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000528e  mov     rcx, r14; Str1
0x180005291  call    wcscmp_0
0x180005296  test    eax, eax
0x180005298  jz      loc_1800A09C6
0x18000529e  cmp     ebp, 4D53414Ch
0x1800052a4  jnz     loc_180005335
0x1800052aa  cmp     dword ptr [rbx], 14h
0x1800052ad  jnz     loc_1800053E0
0x1800052b3  lea     eax, [rdi-60001h]
0x1800052b9  cmp     eax, 6
0x1800052bc  ja      loc_1800054CD
0x1800052c2  lea     rdx, aKeylengths; "KeyLengths"
0x1800052c9  mov     rcx, r14; Str1
0x1800052cc  call    wcscmp_0
0x1800052d1  test    eax, eax
0x1800052d3  jz      short loc_180005323
0x1800052d5  lea     rdx, aObjectlength; "ObjectLength"
0x1800052dc  mov     rcx, r14; Str1
0x1800052df  call    wcscmp_0
0x1800052e4  test    eax, eax
0x1800052e6  jnz     loc_18000552F
0x1800052ec  mov     esi, 4
0x1800052f1  test    r12, r12
0x1800052f4  jz      short loc_18000531F
0x1800052f6  cmp     r13d, esi
0x1800052f9  jb      loc_18000551C
0x1800052ff  mov     eax, [rbx+0Ch]
0x180005302  xor     edi, edi
0x180005304  mov     [r12], eax
0x180005308  mov     [r15], esi
0x18000530b  mov     eax, edi
0x18000530d  add     rsp, 48h
0x180005311  pop     r15
0x180005313  pop     r14
0x180005315  pop     r13
0x180005317  pop     r12
0x180005319  pop     rdi
0x18000531a  pop     rsi
0x18000531b  pop     rbp
0x18000531c  pop     rbx
0x18000531d  retn
0x18000531f  xor     edi, edi
0x180005321  jmp     short loc_180005308
0x180005323  test    r12, r12
0x180005326  jnz     loc_1800054FA
0x18000532c  mov     esi, 0Ch
0x180005331  xor     edi, edi
0x180005333  jmp     short loc_180005308
0x180005335  xor     edi, edi
0x180005337  cmp     ebp, 4D534B59h
0x18000533d  jnz     short loc_180005308
0x18000533f  lea     rax, [rsp+88h+arg_20]
0x180005347  mov     r9d, r13d
0x18000534a  mov     r8, r12
0x18000534d  mov     [rsp+88h+var_68], rax
0x180005352  mov     rdx, r14
0x180005355  mov     rcx, rbx
0x180005358  call    MSCryptKDGetKeyProperty
0x18000535d  mov     edi, eax
0x18000535f  test    eax, eax
0x180005361  jns     loc_1800A0B0B
0x180005367  mov     r9d, 3EFh
0x18000536d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005374  lea     rdx, aStatus; "Status"
0x18000537b  mov     ecx, eax
0x18000537d  call    DebugTraceError
0x180005382  nop
0x180005383  jmp     loc_1800A0B0B
0x180005388  mov     edi, 0C0000008h
0x18000538d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005394  lea     rbp, WPP_GLOBAL_Control
0x18000539b  cmp     rcx, rbp
0x18000539e  jz      loc_180005308
0x1800053a4  mov     eax, [rcx+2Ch]
0x1800053a7  test    al, 1
0x1800053a9  jz      loc_180005308
0x1800053af  mov     rcx, [rcx+18h]
0x1800053b3  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800053ba  mov     [rsp+88h+var_58], 375h
0x1800053c2  lea     r9, aStatus; "Status"
0x1800053c9  mov     [rsp+88h+var_60], r14
0x1800053ce  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x1800053d6  call    WPP_SF_sDsd
0x1800053db  jmp     loc_180005308
0x1800053e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053e7  lea     rbp, WPP_GLOBAL_Control
0x1800053ee  cmp     rcx, rbp
0x1800053f1  jz      short loc_180005460
0x1800053f3  mov     eax, [rcx+2Ch]
0x1800053f6  test    al, 1
0x1800053f8  jz      short loc_180005460
0x1800053fa  mov     rcx, [rcx+18h]
0x1800053fe  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005405  mov     [rsp+88h+var_58], 111h
0x18000540d  lea     r9, aStatus; "Status"
0x180005414  mov     [rsp+88h+var_60], r14
0x180005419  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x180005421  call    WPP_SF_sDsd
0x180005426  mov     edi, 0C0000008h
0x18000542b  mov     ebx, edi
0x18000542d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005434  cmp     rcx, rbp
0x180005437  jz      short loc_180005444
0x180005439  mov     eax, [rcx+2Ch]
0x18000543c  test    al, 1
0x18000543e  jnz     loc_18000555C
0x180005444  mov     r9d, 3DFh
0x18000544a  lea     rdx, aStatus; "Status"
0x180005451  mov     r8, r14
0x180005454  mov     ecx, ebx
0x180005456  call    DebugTraceError
0x18000545b  jmp     loc_180005308
0x180005460  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005467  jmp     short loc_180005426
0x180005469  mov     r9d, 37Ch
0x18000546f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005476  lea     rdx, aStatus; "Status"
0x18000547d  mov     ecx, 0C000000Dh
0x180005482  mov     edi, 0C000000Dh
0x180005487  call    DebugTraceError
0x18000548c  jmp     loc_180005308
0x180005491  cmp     ebp, 4D534B59h
0x180005497  jz      loc_180005275
0x18000549d  mov     r9d, 0D0h
0x1800054a3  jmp     short loc_1800054AB
0x1800054a5  mov     r9d, 0DDh
0x1800054ab  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800054b2  mov     ecx, 0C0000008h
0x1800054b7  lea     rdx, aStatus; "Status"
0x1800054be  call    DebugTraceError
0x1800054c3  mov     edi, 0C0000008h
0x1800054c8  jmp     loc_180005308
0x1800054cd  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800054d4  mov     r9d, 11Eh
0x1800054da  mov     r8, r14
0x1800054dd  lea     rdx, aStatus; "Status"
0x1800054e4  mov     ecx, 0C0000008h
0x1800054e9  call    DebugTraceError
0x1800054ee  lea     rbp, WPP_GLOBAL_Control
0x1800054f5  jmp     loc_180005426
0x1800054fa  cmp     r13d, 0Ch
0x1800054fe  jnb     loc_1800A0A95
0x180005504  mov     edi, 0C0000023h
0x180005509  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005510  mov     ebx, edi
0x180005512  mov     esi, 0Ch
0x180005517  jmp     loc_180005444
0x18000551c  mov     edi, 0C0000023h
0x180005521  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005528  mov     ebx, edi
0x18000552a  jmp     loc_180005444
0x18000552f  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005536  mov     edi, 0C00000BBh
0x18000553b  mov     r8, r14
0x18000553e  lea     rdx, aStatus; "Status"
0x180005545  mov     r9d, 2C8h
0x18000554b  mov     ecx, 0C00000BBh
0x180005550  mov     ebx, edi
0x180005552  call    DebugTraceError
0x180005557  jmp     loc_180005444
0x18000555c  mov     rcx, [rcx+18h]
0x180005560  lea     r9, aStatus; "Status"
0x180005567  mov     [rsp+88h+var_58], 260h
0x18000556f  mov     [rsp+88h+var_60], r14
0x180005574  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000557c  call    WPP_SF_sDsd
0x180005581  jmp     loc_180005444
0x1800a09c6  add     edi, 0FFF9FFFFh; switch 7 cases
0x1800a09cc  cmp     edi, 6
0x1800a09cf  ja      def_1800A09E6; jumptable 00000001800A09E6 default case
0x1800a09d5  lea     rcx, cs:180000000h
0x1800a09dc  mov     eax, ds:(jpt_1800A09E6 - 180000000h)[rcx+rdi*4]
0x1800a09e3  add     rax, rcx
0x1800a09e6  jmp     rax; switch jump
0x1800a09ec  lea     rdx, aSp800108CtrHma; jumptable 00000001800A09E6 case 393217
0x1800a09f3  jmp     short loc_1800A0A29
0x1800a09f5  lea     rdx, aSp80056aConcat; jumptable 00000001800A09E6 case 393218
0x1800a09fc  jmp     short loc_1800A0A29
0x1800a09fe  lea     rdx, aPbkdf2; jumptable 00000001800A09E6 case 393219
0x1800a0a05  jmp     short loc_1800A0A29
0x1800a0a07  lea     rdx, aCapiKdf; jumptable 00000001800A09E6 case 393220
0x1800a0a0e  jmp     short loc_1800A0A29
0x1800a0a10  lea     rdx, aTls11Kdf; jumptable 00000001800A09E6 case 393221
0x1800a0a17  jmp     short loc_1800A0A29
0x1800a0a19  lea     rdx, aTls12Kdf; jumptable 00000001800A09E6 case 393222
0x1800a0a20  jmp     short loc_1800A0A29
0x1800a0a22  lea     rdx, aHkdf; jumptable 00000001800A09E6 case 393223
0x1800a0a29  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800a0a30  cmp     word ptr [rdx+rsi*2+2], 0
0x1800a0a36  lea     rsi, [rsi+1]
0x1800a0a3a  jnz     short loc_1800A0A30
0x1800a0a3c  lea     esi, ds:2[rsi*2]
0x1800a0a43  test    r12, r12
0x1800a0a46  jz      loc_18000531F
0x1800a0a4c  cmp     r13d, esi
0x1800a0a4f  jnb     short loc_1800A0A5B
0x1800a0a51  mov     edi, 0C0000023h
0x1800a0a56  jmp     loc_180005308
0x1800a0a5b  mov     r8, r13; Size
0x1800a0a5e  mov     rcx, r12; void *
0x1800a0a61  call    memmove
0x1800a0a66  nop
0x1800a0a67  jmp     loc_18000531F
0x1800a0a6c  mov     r9d, 3B8h; jumptable 00000001800A09E6 default case
0x1800a0a72  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0a79  lea     rdx, aStatus; "Status"
0x1800a0a80  mov     ecx, 0C00000BBh
0x1800a0a85  mov     edi, 0C00000BBh
0x1800a0a8a  call    DebugTraceError
0x1800a0a8f  nop
0x1800a0a90  jmp     loc_180005308
0x1800a0a95  add     edi, 0FFF9FFFFh; switch 7 cases
0x1800a0a9b  cmp     edi, 6
0x1800a0a9e  ja      short def_1800A0AB1; jumptable 00000001800A0AB1 default case
0x1800a0aa0  lea     rcx, cs:180000000h
0x1800a0aa7  mov     eax, ds:(jpt_1800A0AB1 - 180000000h)[rcx+rdi*4]
0x1800a0aae  add     rax, rcx
0x1800a0ab1  jmp     rax; switch jump
0x1800a0ab7  xor     edi, edi; jumptable 00000001800A0AB1 cases 393217-393223
0x1800a0ab9  mov     esi, 0Ch
0x1800a0abe  mov     [r12], edi
0x1800a0ac2  mov     dword ptr [r12+4], 4000h
0x1800a0acb  mov     dword ptr [r12+8], 8
0x1800a0ad4  jmp     loc_180005308
0x1800a0ad9  lea     r14, aOnecoreDsSecur_1; jumptable 00000001800A0AB1 default case
0x1800a0ae0  mov     edi, 0C00000BBh
0x1800a0ae5  mov     r8, r14
0x1800a0ae8  lea     rdx, aStatus; "Status"
0x1800a0aef  mov     r9d, 2ABh
0x1800a0af5  mov     ecx, 0C00000BBh
0x1800a0afa  mov     ebx, edi
0x1800a0afc  call    DebugTraceError
0x1800a0b01  mov     esi, 0Ch
0x1800a0b06  jmp     loc_180005444
0x1800a0b0b  mov     esi, dword ptr [rsp+88h+arg_20]
0x1800a0b12  jmp     loc_180005308
```
