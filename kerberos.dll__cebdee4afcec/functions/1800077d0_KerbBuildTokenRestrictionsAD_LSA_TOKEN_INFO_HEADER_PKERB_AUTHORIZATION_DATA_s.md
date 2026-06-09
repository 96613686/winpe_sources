# KerbBuildTokenRestrictionsAD(_LSA_TOKEN_INFO_HEADER *,PKERB_AUTHORIZATION_DATA_s * *)

- ea: `0x1800077d0`
- end: `0x180007cca`
- name: `?KerbBuildTokenRestrictionsAD@@YAJPEAU_LSA_TOKEN_INFO_HEADER@@PEAPEAUPKERB_AUTHORIZATION_DATA_s@@@Z`
- size: `1274`
- prototype: `__int64 __fastcall(struct _LSA_TOKEN_INFO_HEADER *, struct PKERB_AUTHORIZATION_DATA_s **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18003d3f0`
- `0x180086258`

## callees

- `0x1800077d0`
- `0x180007e00`
- `0x18006ccec`
- `0x18007108c`
- `0x1800744cf`
- `0x180077804`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a65`
- `MSASN1!ASN1_CreateModule` at `0x1800078b0`
- `MSASN1!ASN1_CreateModule` at `0x1800078b0`
- `MSASN1!ASN1_CreateEncoder` at `0x1800078d3`
- `MSASN1!ASN1_CreateEncoder` at `0x1800078d3`
- `MSASN1!ASN1_FreeEncoded` at `0x180007982`
- `MSASN1!ASN1_FreeEncoded` at `0x180007982`
- `MSASN1!ASN1_Encode` at `0x180007907`
- `MSASN1!ASN1_Encode` at `0x180007907`
- `MSASN1!ASN1_CloseEncoder` at `0x180007a10`
- `MSASN1!ASN1_CloseEncoder` at `0x180007a10`

## pseudocode

```c
__int64 __fastcall KerbBuildTokenRestrictionsAD(
        struct _LSA_TOKEN_INFO_HEADER *a1,
        struct PKERB_AUTHORIZATION_DATA_s **a2)
{
  int v3; // eax
  _QWORD *v4; // rbx
  __int64 Module; // rax
  unsigned int v6; // eax
  int v7; // eax
  void *v8; // rbp
  int v9; // edi
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  _QWORD *v14; // rcx
  _OWORD *v15; // rax
  SIZE_T v16; // rdi
  HLOCAL v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // [rsp+50h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-30h]
  int v21; // [rsp+5Ch] [rbp-2Ch]
  int v22; // [rsp+60h] [rbp-28h]
  int v23; // [rsp+64h] [rbp-24h]
  char *v24; // [rsp+68h] [rbp-20h]
  __int64 v25; // [rsp+90h] [rbp+8h] BYREF
  __int64 *v26; // [rsp+98h] [rbp+10h] BYREF

  v26 = &v19;
  v3 = *((_DWORD *)a1 + 1);
  v19 = 0;
  v21 = 0;
  v23 = 0;
  v20 = v3;
  v22 = *(_DWORD *)a1 - 8;
  v24 = (char *)a1 + 8;
  if ( KerbGlobalPackageState == 1 )
  {
    v4 = (_QWORD *)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(32);
    if ( v4 )
      goto LABEL_3;
    return 3221225495LL;
  }
  v15 = LocalAlloc(0, 0x20u);
  v4 = v15;
  if ( !v15 )
    return 3221225495LL;
  *v15 = 0;
  v15[1] = 0;
LABEL_3:
  v25 = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               81,
               off_1800F62D0,
               off_1800F6040,
               off_1800F6560,
               qword_1800FE8B0,
               895644267);
    KRB5_Module = Module;
  }
  v6 = ASN1_CreateEncoder(Module, &v25, 0, 0, 0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v6);
      v9 = 60;
      goto LABEL_12;
    }
    goto LABEL_23;
  }
  v7 = ASN1_Encode(v25, &v26, 39, 16, 0, 0);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v7);
LABEL_23:
    v9 = 60;
    goto LABEL_12;
  }
  if ( KerbGlobalPackageState == 1 )
  {
    v8 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(*(unsigned int *)(v25 + 28));
  }
  else
  {
    v16 = *(unsigned int *)(v25 + 28);
    v17 = LocalAlloc(0, v16);
    v8 = v17;
    if ( v17 )
    {
      memset_0(v17, 0, v16);
      v4[3] = v8;
      goto LABEL_10;
    }
  }
  v4[3] = v8;
  if ( !v8 )
  {
    v10 = v25;
    v9 = 60;
    v11 = 0;
    goto LABEL_11;
  }
LABEL_10:
  v9 = 0;
  memcpy_0(v8, *(const void **)(v25 + 16), *(unsigned int *)(v25 + 28));
  v10 = v25;
  v11 = *(_DWORD *)(v25 + 28);
LABEL_11:
  *((_DWORD *)v4 + 4) = v11;
  ASN1_FreeEncoded(v10, *(_QWORD *)(v10 + 16));
LABEL_12:
  if ( v25 )
    ASN1_CloseEncoder();
  if ( v9 )
  {
    switch ( v9 )
    {
      case 5:
      case 75:
      case 76:
        v12 = -1073741063;
        break;
      case 6:
        v12 = -1073741724;
        break;
      case 7:
        v12 = -1073741429;
        break;
      case 12:
        v12 = -1073741714;
        break;
      case 14:
      case 80:
        v12 = -1073741059;
        break;
      case 16:
        v12 = -1073741637;
        break;
      case 18:
        v12 = -1073741710;
        break;
      case 23:
        v12 = -1073741711;
        break;
      case 24:
      case 41:
        v12 = -1073741718;
        break;
      case 27:
      case 69:
        v12 = -1073740792;
        break;
      case 28:
        v12 = -1073741424;
        break;
      case 29:
      case 68:
        v12 = -1073741730;
        break;
      case 32:
      case 33:
      case 37:
      case 90:
        v12 = -1073741517;
        break;
      case 35:
        v12 = -2146893022;
        break;
      case 39:
      case 40:
      case 71:
        v12 = -1073741811;
        break;
      case 45:
        v12 = -1073741022;
        break;
      case 52:
        v12 = -1073741306;
        break;
      case 60:
        v12 = -1073741670;
        break;
      case 70:
        v12 = -2146869247;
        break;
      case 72:
        v12 = -2146885616;
        break;
      case 73:
        v12 = -2146885614;
        break;
      case 74:
        v12 = -2146885613;
        break;
      case 77:
        v12 = -2146762480;
        break;
      default:
        v12 = -1073741715;
        break;
    }
    KerbFreeAuthData(v4);
  }
  else
  {
    *v4 = 0;
    v12 = 0;
    *((_DWORD *)v4 + 2) = 141;
    v14 = *a2;
    if ( *a2 )
    {
      do
      {
        v18 = v14;
        v14 = (_QWORD *)*v14;
      }
      while ( v14 );
      *v18 = v4;
    }
    else
    {
      *a2 = (struct PKERB_AUTHORIZATION_DATA_s *)v4;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800077d0  mov     r11, rsp
0x1800077d3  push    rbx
0x1800077d4  push    rsi
0x1800077d5  push    r14
0x1800077d7  sub     rsp, 70h
0x1800077db  xor     r14d, r14d
0x1800077de  lea     rax, [r11-38h]
0x1800077e2  mov     [r11+10h], rax
0x1800077e6  mov     rsi, rdx
0x1800077e9  mov     eax, [rcx+4]
0x1800077ec  mov     [r11-38h], r14
0x1800077f0  mov     [r11-2Ch], r14d
0x1800077f4  mov     [r11-24h], r14d
0x1800077f8  mov     [rsp+88h+var_30], eax
0x1800077fc  mov     eax, [rcx]
0x1800077fe  sub     eax, 8
0x180007801  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180007808  mov     [rsp+88h+var_28], eax
0x18000780c  lea     rax, [rcx+8]
0x180007810  mov     [r11-20h], rax
0x180007814  jnz     loc_180007A39
0x18000781a  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180007821  mov     ecx, 20h ; ' '
0x180007826  mov     rax, [rax+28h]
0x18000782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782f  mov     rbx, rax
0x180007832  test    rax, rax
0x180007835  jz      loc_1800079DA
0x18000783b  cmp     cs:?fKRB5ModuleStarted@@3HA, r14d; int fKRB5ModuleStarted
0x180007842  mov     [rsp+88h+arg_18], rdi
0x18000784a  mov     [rsp+88h+arg_0], r14
0x180007852  jnz     loc_180007AA2
0x180007858  mov     [rsp+88h+var_48], 3562726Bh
0x180007860  lea     rax, qword_1800FE8B0
0x180007867  mov     [rsp+88h+var_50], rax
0x18000786c  mov     edx, 400h
0x180007871  lea     rax, off_1800F6560
0x180007878  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180007882  mov     [rsp+88h+var_58], rax
0x180007887  mov     ecx, 10000h
0x18000788c  lea     rax, off_1800F6040
0x180007893  mov     r9d, 51h ; 'Q'
0x180007899  mov     [rsp+88h+var_60], rax
0x18000789e  mov     r8d, 1000h
0x1800078a4  lea     rax, off_1800F62D0
0x1800078ab  mov     [rsp+88h+var_68], rax
0x1800078b0  call    cs:__imp_ASN1_CreateModule
0x1800078b6  mov     cs:KRB5_Module, rax
0x1800078bd  xor     r9d, r9d
0x1800078c0  mov     [rsp+88h+var_68], r14
0x1800078c5  xor     r8d, r8d
0x1800078c8  lea     rdx, [rsp+88h+arg_0]
0x1800078d0  mov     rcx, rax
0x1800078d3  call    cs:__imp_ASN1_CreateEncoder
0x1800078d9  test    eax, eax
0x1800078db  jnz     loc_180007AAE
0x1800078e1  mov     rcx, [rsp+88h+arg_0]
0x1800078e9  lea     rdx, [rsp+88h+arg_8]
0x1800078f1  mov     dword ptr [rsp+88h+var_60], r14d
0x1800078f6  mov     r9d, 10h
0x1800078fc  mov     r8d, 27h ; '''
0x180007902  mov     [rsp+88h+var_68], r14
0x180007907  call    cs:__imp_ASN1_Encode
0x18000790d  test    eax, eax
0x18000790f  js      loc_180007A18
0x180007915  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000791c  mov     rax, [rsp+88h+arg_0]
0x180007924  mov     [rsp+88h+arg_10], rbp
0x18000792c  mov     ecx, [rax+1Ch]
0x18000792f  jnz     loc_180007A5D
0x180007935  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000793c  mov     rax, [rax+28h]
0x180007940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007945  mov     rbp, rax
0x180007948  mov     [rbx+18h], rbp
0x18000794c  test    rbp, rbp
0x18000794f  jz      loc_180007A8D
0x180007955  mov     rdx, [rsp+88h+arg_0]
0x18000795d  mov     rcx, rbp; void *
0x180007960  mov     edi, r14d
0x180007963  mov     r8d, [rdx+1Ch]; Size
0x180007967  mov     rdx, [rdx+10h]; Src
0x18000796b  call    memcpy_0
0x180007970  mov     rcx, [rsp+88h+arg_0]
0x180007978  mov     eax, [rcx+1Ch]
0x18000797b  mov     [rbx+10h], eax
0x18000797e  mov     rdx, [rcx+10h]
0x180007982  call    cs:__imp_ASN1_FreeEncoded
0x180007988  mov     rbp, [rsp+88h+arg_10]
0x180007990  mov     rcx, [rsp+88h+arg_0]
0x180007998  test    rcx, rcx
0x18000799b  jnz     short loc_180007A10
0x18000799d  test    edi, edi
0x18000799f  jz      short loc_1800079E1
0x1800079a1  add     edi, 0FFFFFFFBh; switch 86 cases
0x1800079a4  cmp     edi, 55h
0x1800079a7  ja      def_1800079C9; jumptable 00000001800079C9 default case, cases 8-11,13,15,17,19-22,25,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x1800079ad  lea     rdx, __ImageBase
0x1800079b4  movsxd  rax, edi
0x1800079b7  movzx   eax, ds:(byte_180007C74 - 180000000h)[rdx+rax]
0x1800079bf  mov     ecx, ds:(jpt_1800079C9 - 180000000h)[rdx+rax*4]
0x1800079c6  add     rcx, rdx
0x1800079c9  jmp     rcx; switch jump
0x1800079cb  mov     edi, 0C000018Bh; jumptable 00000001800079C9 case 7
0x1800079d0  mov     rcx, rbx; hMem
0x1800079d3  call    KerbFreeAuthData
0x1800079d8  jmp     short loc_1800079FD
0x1800079da  mov     eax, 0C0000017h
0x1800079df  jmp     short loc_180007A07
0x1800079e1  mov     [rbx], r14
0x1800079e4  mov     edi, r14d
0x1800079e7  mov     dword ptr [rbx+8], 8Dh
0x1800079ee  mov     rcx, [rsi]
0x1800079f1  test    rcx, rcx
0x1800079f4  jnz     loc_180007B18
0x1800079fa  mov     [rsi], rbx
0x1800079fd  mov     eax, edi
0x1800079ff  mov     rdi, [rsp+88h+arg_18]
0x180007a07  add     rsp, 70h
0x180007a0b  pop     r14
0x180007a0d  pop     rsi
0x180007a0e  pop     rbx
0x180007a0f  retn
0x180007a10  call    cs:__imp_ASN1_CloseEncoder
0x180007a16  jmp     short loc_18000799D
0x180007a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a1f  lea     rdx, WPP_GLOBAL_Control
0x180007a26  cmp     rcx, rdx
0x180007a29  jnz     loc_180007AF1
0x180007a2f  mov     edi, 3Ch ; '<'
0x180007a34  jmp     loc_180007990
0x180007a39  mov     edx, 20h ; ' '; uBytes
0x180007a3e  xor     ecx, ecx; uFlags
0x180007a40  call    cs:__imp_LocalAlloc
0x180007a46  mov     rbx, rax
0x180007a49  test    rax, rax
0x180007a4c  jz      short loc_1800079DA
0x180007a4e  xorps   xmm0, xmm0
0x180007a51  movups  xmmword ptr [rax], xmm0
0x180007a54  movups  xmmword ptr [rax+10h], xmm0
0x180007a58  jmp     loc_18000783B
0x180007a5d  mov     rdi, rcx
0x180007a60  mov     rdx, rcx; uBytes
0x180007a63  xor     ecx, ecx; uFlags
0x180007a65  call    cs:__imp_LocalAlloc
0x180007a6b  mov     rbp, rax
0x180007a6e  test    rax, rax
0x180007a71  jz      loc_180007948
0x180007a77  mov     r8, rdi; Size
0x180007a7a  xor     edx, edx; Val
0x180007a7c  mov     rcx, rax; void *
0x180007a7f  call    memset_0
0x180007a84  mov     [rbx+18h], rbp
0x180007a88  jmp     loc_180007955
0x180007a8d  mov     rcx, [rsp+88h+arg_0]
0x180007a95  mov     edi, 3Ch ; '<'
0x180007a9a  mov     eax, r14d
0x180007a9d  jmp     loc_18000797B
0x180007aa2  mov     rax, cs:KRB5_Module
0x180007aa9  jmp     loc_1800078BD
0x180007aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ab5  lea     rdx, WPP_GLOBAL_Control
0x180007abc  cmp     rcx, rdx
0x180007abf  jz      loc_180007A2F
0x180007ac5  test    byte ptr [rcx+1Ch], 1
0x180007ac9  jz      loc_180007A2F
0x180007acf  mov     rcx, [rcx+10h]
0x180007ad3  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180007ada  mov     edx, 24h ; '$'
0x180007adf  mov     r9d, eax
0x180007ae2  call    WPP_SF_D
0x180007ae7  mov     edi, 3Ch ; '<'
0x180007aec  jmp     loc_180007990
0x180007af1  test    byte ptr [rcx+1Ch], 1
0x180007af5  jz      loc_180007A2F
0x180007afb  mov     rcx, [rcx+10h]
0x180007aff  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180007b06  mov     edx, 25h ; '%'
0x180007b0b  mov     r9d, eax
0x180007b0e  call    WPP_SF_d
0x180007b13  jmp     loc_180007A2F
0x180007b18  mov     rax, [rcx]
0x180007b1b  lea     rdx, [rcx]
0x180007b1e  mov     rcx, rax
0x180007b21  test    rax, rax
0x180007b24  jnz     short loc_180007B18
0x180007b26  mov     [rdx], rbx
0x180007b29  jmp     loc_1800079FD
0x180007b2e  mov     edi, 0C0000072h; jumptable 00000001800079C9 case 18
0x180007b33  jmp     loc_1800079D0
0x180007b38  mov     edi, 0C0000071h; jumptable 00000001800079C9 case 23
0x180007b3d  jmp     loc_1800079D0
0x180007b42  mov     edi, 0C000009Ah; jumptable 00000001800079C9 case 60
0x180007b47  jmp     loc_1800079D0
0x180007b4c  mov     edi, 0C0000133h; jumptable 00000001800079C9 cases 32,33,37,90
0x180007b51  jmp     loc_1800079D0
0x180007b56  mov     edi, 0C000006Eh; jumptable 00000001800079C9 case 12
0x180007b5b  jmp     loc_1800079D0
0x180007b60  mov     edi, 0C0000064h; jumptable 00000001800079C9 case 6
0x180007b65  jmp     loc_1800079D0
0x180007b6a  mov     edi, 0C0000206h; jumptable 00000001800079C9 case 52
0x180007b6f  jmp     loc_1800079D0
0x180007b74  mov     edi, 0C00000BBh; jumptable 00000001800079C9 case 16
0x180007b79  jmp     loc_1800079D0
0x180007b7e  mov     edi, 80090322h; jumptable 00000001800079C9 case 35
0x180007b83  jmp     loc_1800079D0
0x180007b88  mov     edi, 0C000005Eh; jumptable 00000001800079C9 cases 29,68
0x180007b8d  jmp     loc_1800079D0
0x180007b92  mov     edi, 80096001h; jumptable 00000001800079C9 case 70
0x180007b97  jmp     loc_1800079D0
0x180007b9c  mov     edi, 0C000000Dh; jumptable 00000001800079C9 cases 39,40,71
0x180007ba1  jmp     loc_1800079D0
0x180007ba6  mov     edi, 80092010h; jumptable 00000001800079C9 case 72
0x180007bab  jmp     loc_1800079D0
0x180007bb0  mov     edi, 80092012h; jumptable 00000001800079C9 case 73
0x180007bb5  jmp     loc_1800079D0
0x180007bba  mov     edi, 800B0110h; jumptable 00000001800079C9 case 77
0x180007bbf  jmp     loc_1800079D0
0x180007bc4  mov     edi, 80092013h; jumptable 00000001800079C9 case 74
0x180007bc9  jmp     loc_1800079D0
0x180007bce  mov     edi, 0C00002F9h; jumptable 00000001800079C9 cases 5,75,76
0x180007bd3  jmp     loc_1800079D0
0x180007bd8  mov     edi, 0C0000190h; jumptable 00000001800079C9 case 28
0x180007bdd  jmp     loc_1800079D0
0x180007be2  mov     edi, 0C00002FDh; jumptable 00000001800079C9 cases 14,80
0x180007be7  jmp     loc_1800079D0
0x180007bec  mov     edi, 0C0000408h; jumptable 00000001800079C9 cases 27,69
0x180007bf1  jmp     loc_1800079D0
0x180007bf6  mov     edi, 0C0000322h; jumptable 00000001800079C9 case 45
0x180007bfb  jmp     loc_1800079D0
0x180007c00  mov     edi, 0C000006Ah; jumptable 00000001800079C9 cases 24,41
0x180007c05  jmp     loc_1800079D0
0x180007c0a  mov     edi, 0C000006Dh; jumptable 00000001800079C9 default case, cases 8-11,13,15,17,19-22,25,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180007c0f  jmp     loc_1800079D0
```
