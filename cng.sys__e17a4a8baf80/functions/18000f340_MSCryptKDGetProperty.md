# MSCryptKDGetProperty

- ea: `0x18000f340`
- end: `0x18000f6a6`
- name: `MSCryptKDGetProperty`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000f340`
- `0x18001155c`
- `0x1800123d0`
- `0x18007eccc`
- `0x1800a4232`
- `0x1800a45c0`

## string_xrefs

- `0x18000f48d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f4d3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f51e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f580`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f58f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f5cb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f5ed`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f629`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f641`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000f64f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800a59e0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800a5a47`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x18000f340  push    rbx
0x18000f342  push    rbp
0x18000f343  push    rsi
0x18000f344  push    rdi
0x18000f345  push    r12
0x18000f347  push    r13
0x18000f349  push    r14
0x18000f34b  push    r15
0x18000f34d  sub     rsp, 48h
0x18000f351  mov     r15, [rsp+88h+arg_20]
0x18000f359  mov     r12, r8
0x18000f35c  mov     r13d, r9d
0x18000f35f  mov     r14, rdx
0x18000f362  mov     rbx, rcx
0x18000f365  mov     esi, [r15]
0x18000f368  mov     dword ptr [rsp+88h+arg_20], esi
0x18000f36f  test    rcx, rcx
0x18000f372  jz      loc_18000F4A8
0x18000f378  cmp     [rsp+88h+arg_28], 0
0x18000f380  jnz     loc_18000F589
0x18000f386  mov     ebp, [rcx+4]
0x18000f389  cmp     ebp, 4D53414Ch
0x18000f38f  jnz     loc_18000F5B1
0x18000f395  mov     edi, [rcx+8]
0x18000f398  lea     eax, [rdi-60001h]
0x18000f39e  cmp     eax, 6
0x18000f3a1  ja      loc_18000F5C5
0x18000f3a7  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000f3ae  mov     rcx, r14; Str1
0x18000f3b1  call    wcscmp_0
0x18000f3b6  test    eax, eax
0x18000f3b8  jz      loc_1800A5934
0x18000f3be  cmp     ebp, 4D53414Ch
0x18000f3c4  jnz     loc_18000F455
0x18000f3ca  cmp     dword ptr [rbx], 14h
0x18000f3cd  jnz     loc_18000F500
0x18000f3d3  lea     eax, [rdi-60001h]
0x18000f3d9  cmp     eax, 6
0x18000f3dc  ja      loc_18000F5ED
0x18000f3e2  lea     rdx, aKeylengths; "KeyLengths"
0x18000f3e9  mov     rcx, r14; Str1
0x18000f3ec  call    wcscmp_0
0x18000f3f1  test    eax, eax
0x18000f3f3  jz      short loc_18000F443
0x18000f3f5  lea     rdx, aObjectlength; "ObjectLength"
0x18000f3fc  mov     rcx, r14; Str1
0x18000f3ff  call    wcscmp_0
0x18000f404  test    eax, eax
0x18000f406  jnz     loc_18000F64F
0x18000f40c  mov     esi, 4
0x18000f411  test    r12, r12
0x18000f414  jz      short loc_18000F43F
0x18000f416  cmp     r13d, esi
0x18000f419  jb      loc_18000F63C
0x18000f41f  mov     eax, [rbx+0Ch]
0x18000f422  xor     edi, edi
0x18000f424  mov     [r12], eax
0x18000f428  mov     [r15], esi
0x18000f42b  mov     eax, edi
0x18000f42d  add     rsp, 48h
0x18000f431  pop     r15
0x18000f433  pop     r14
0x18000f435  pop     r13
0x18000f437  pop     r12
0x18000f439  pop     rdi
0x18000f43a  pop     rsi
0x18000f43b  pop     rbp
0x18000f43c  pop     rbx
0x18000f43d  retn
0x18000f43f  xor     edi, edi
0x18000f441  jmp     short loc_18000F428
0x18000f443  test    r12, r12
0x18000f446  jnz     loc_18000F61A
0x18000f44c  mov     esi, 0Ch
0x18000f451  xor     edi, edi
0x18000f453  jmp     short loc_18000F428
0x18000f455  xor     edi, edi
0x18000f457  cmp     ebp, 4D534B59h
0x18000f45d  jnz     short loc_18000F428
0x18000f45f  lea     rax, [rsp+88h+arg_20]
0x18000f467  mov     r9d, r13d
0x18000f46a  mov     r8, r12
0x18000f46d  mov     [rsp+88h+var_68], rax
0x18000f472  mov     rdx, r14
0x18000f475  mov     rcx, rbx
0x18000f478  call    MSCryptKDGetKeyProperty
0x18000f47d  mov     edi, eax
0x18000f47f  test    eax, eax
0x18000f481  jns     loc_1800A5A79
0x18000f487  mov     r9d, 3EFh
0x18000f48d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f494  lea     rdx, aStatus; "Status"
0x18000f49b  mov     ecx, eax
0x18000f49d  call    DebugTraceError
0x18000f4a2  nop
0x18000f4a3  jmp     loc_1800A5A79
0x18000f4a8  mov     edi, 0C0000008h
0x18000f4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4b4  lea     rbp, WPP_GLOBAL_Control
0x18000f4bb  cmp     rcx, rbp
0x18000f4be  jz      loc_18000F428
0x18000f4c4  mov     eax, [rcx+2Ch]
0x18000f4c7  test    al, 1
0x18000f4c9  jz      loc_18000F428
0x18000f4cf  mov     rcx, [rcx+18h]
0x18000f4d3  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f4da  mov     [rsp+88h+var_58], 375h
0x18000f4e2  lea     r9, aStatus; "Status"
0x18000f4e9  mov     [rsp+88h+var_60], r14
0x18000f4ee  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000f4f6  call    WPP_SF_sDsd
0x18000f4fb  jmp     loc_18000F428
0x18000f500  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f507  lea     rbp, WPP_GLOBAL_Control
0x18000f50e  cmp     rcx, rbp
0x18000f511  jz      short loc_18000F580
0x18000f513  mov     eax, [rcx+2Ch]
0x18000f516  test    al, 1
0x18000f518  jz      short loc_18000F580
0x18000f51a  mov     rcx, [rcx+18h]
0x18000f51e  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f525  mov     [rsp+88h+var_58], 111h
0x18000f52d  lea     r9, aStatus; "Status"
0x18000f534  mov     [rsp+88h+var_60], r14
0x18000f539  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000f541  call    WPP_SF_sDsd
0x18000f546  mov     edi, 0C0000008h
0x18000f54b  mov     ebx, edi
0x18000f54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f554  cmp     rcx, rbp
0x18000f557  jz      short loc_18000F564
0x18000f559  mov     eax, [rcx+2Ch]
0x18000f55c  test    al, 1
0x18000f55e  jnz     loc_18000F67C
0x18000f564  mov     r9d, 3DFh
0x18000f56a  lea     rdx, aStatus; "Status"
0x18000f571  mov     r8, r14
0x18000f574  mov     ecx, ebx
0x18000f576  call    DebugTraceError
0x18000f57b  jmp     loc_18000F428
0x18000f580  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f587  jmp     short loc_18000F546
0x18000f589  mov     r9d, 37Ch
0x18000f58f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f596  lea     rdx, aStatus; "Status"
0x18000f59d  mov     ecx, 0C000000Dh
0x18000f5a2  mov     edi, 0C000000Dh
0x18000f5a7  call    DebugTraceError
0x18000f5ac  jmp     loc_18000F428
0x18000f5b1  cmp     ebp, 4D534B59h
0x18000f5b7  jz      loc_18000F395
0x18000f5bd  mov     r9d, 0D0h
0x18000f5c3  jmp     short loc_18000F5CB
0x18000f5c5  mov     r9d, 0DDh
0x18000f5cb  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f5d2  mov     ecx, 0C0000008h
0x18000f5d7  lea     rdx, aStatus; "Status"
0x18000f5de  call    DebugTraceError
0x18000f5e3  mov     edi, 0C0000008h
0x18000f5e8  jmp     loc_18000F428
0x18000f5ed  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f5f4  mov     r9d, 11Eh
0x18000f5fa  mov     r8, r14
0x18000f5fd  lea     rdx, aStatus; "Status"
0x18000f604  mov     ecx, 0C0000008h
0x18000f609  call    DebugTraceError
0x18000f60e  lea     rbp, WPP_GLOBAL_Control
0x18000f615  jmp     loc_18000F546
0x18000f61a  cmp     r13d, 0Ch
0x18000f61e  jnb     loc_1800A5A03
0x18000f624  mov     edi, 0C0000023h
0x18000f629  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f630  mov     ebx, edi
0x18000f632  mov     esi, 0Ch
0x18000f637  jmp     loc_18000F564
0x18000f63c  mov     edi, 0C0000023h
0x18000f641  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f648  mov     ebx, edi
0x18000f64a  jmp     loc_18000F564
0x18000f64f  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f656  mov     edi, 0C00000BBh
0x18000f65b  mov     r8, r14
0x18000f65e  lea     rdx, aStatus; "Status"
0x18000f665  mov     r9d, 2C8h
0x18000f66b  mov     ecx, 0C00000BBh
0x18000f670  mov     ebx, edi
0x18000f672  call    DebugTraceError
0x18000f677  jmp     loc_18000F564
0x18000f67c  mov     rcx, [rcx+18h]
0x18000f680  lea     r9, aStatus; "Status"
0x18000f687  mov     [rsp+88h+var_58], 260h
0x18000f68f  mov     [rsp+88h+var_60], r14
0x18000f694  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000f69c  call    WPP_SF_sDsd
0x18000f6a1  jmp     loc_18000F564
0x1800a5934  add     edi, 0FFF9FFFFh; switch 7 cases
0x1800a593a  cmp     edi, 6
0x1800a593d  ja      def_1800A5954; jumptable 00000001800A5954 default case
0x1800a5943  lea     rcx, cs:180000000h
0x1800a594a  mov     eax, ds:(jpt_1800A5954 - 180000000h)[rcx+rdi*4]
0x1800a5951  add     rax, rcx
0x1800a5954  jmp     rax; switch jump
0x1800a595a  lea     rdx, aSp800108CtrHma; jumptable 00000001800A5954 case 393217
0x1800a5961  jmp     short loc_1800A5997
0x1800a5963  lea     rdx, aSp80056aConcat; jumptable 00000001800A5954 case 393218
0x1800a596a  jmp     short loc_1800A5997
0x1800a596c  lea     rdx, aPbkdf2; jumptable 00000001800A5954 case 393219
0x1800a5973  jmp     short loc_1800A5997
0x1800a5975  lea     rdx, aCapiKdf; jumptable 00000001800A5954 case 393220
0x1800a597c  jmp     short loc_1800A5997
0x1800a597e  lea     rdx, aTls11Kdf; jumptable 00000001800A5954 case 393221
0x1800a5985  jmp     short loc_1800A5997
0x1800a5987  lea     rdx, aTls12Kdf; jumptable 00000001800A5954 case 393222
0x1800a598e  jmp     short loc_1800A5997
0x1800a5990  lea     rdx, aHkdf; jumptable 00000001800A5954 case 393223
0x1800a5997  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800a599e  cmp     word ptr [rdx+rsi*2+2], 0
0x1800a59a4  lea     rsi, [rsi+1]
0x1800a59a8  jnz     short loc_1800A599E
0x1800a59aa  lea     esi, ds:2[rsi*2]
0x1800a59b1  test    r12, r12
0x1800a59b4  jz      loc_18000F43F
0x1800a59ba  cmp     r13d, esi
0x1800a59bd  jnb     short loc_1800A59C9
0x1800a59bf  mov     edi, 0C0000023h
0x1800a59c4  jmp     loc_18000F428
0x1800a59c9  mov     r8, r13; Size
0x1800a59cc  mov     rcx, r12; void *
0x1800a59cf  call    memmove
0x1800a59d4  nop
0x1800a59d5  jmp     loc_18000F43F
0x1800a59da  mov     r9d, 3B8h; jumptable 00000001800A5954 default case
0x1800a59e0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a59e7  lea     rdx, aStatus; "Status"
0x1800a59ee  mov     ecx, 0C00000BBh
0x1800a59f3  mov     edi, 0C00000BBh
0x1800a59f8  call    DebugTraceError
0x1800a59fd  nop
0x1800a59fe  jmp     loc_18000F428
0x1800a5a03  add     edi, 0FFF9FFFFh; switch 7 cases
0x1800a5a09  cmp     edi, 6
0x1800a5a0c  ja      short def_1800A5A1F; jumptable 00000001800A5A1F default case
0x1800a5a0e  lea     rcx, cs:180000000h
0x1800a5a15  mov     eax, ds:(jpt_1800A5A1F - 180000000h)[rcx+rdi*4]
0x1800a5a1c  add     rax, rcx
0x1800a5a1f  jmp     rax; switch jump
0x1800a5a25  xor     edi, edi; jumptable 00000001800A5A1F cases 393217-393223
0x1800a5a27  mov     esi, 0Ch
0x1800a5a2c  mov     [r12], edi
0x1800a5a30  mov     dword ptr [r12+4], 4000h
0x1800a5a39  mov     dword ptr [r12+8], 8
0x1800a5a42  jmp     loc_18000F428
0x1800a5a47  lea     r14, aOnecoreDsSecur_2; jumptable 00000001800A5A1F default case
0x1800a5a4e  mov     edi, 0C00000BBh
0x1800a5a53  mov     r8, r14
0x1800a5a56  lea     rdx, aStatus; "Status"
0x1800a5a5d  mov     r9d, 2ABh
0x1800a5a63  mov     ecx, 0C00000BBh
0x1800a5a68  mov     ebx, edi
0x1800a5a6a  call    DebugTraceError
0x1800a5a6f  mov     esi, 0Ch
0x1800a5a74  jmp     loc_18000F564
0x1800a5a79  mov     esi, dword ptr [rsp+88h+arg_20]
0x1800a5a80  jmp     loc_18000F428
```
