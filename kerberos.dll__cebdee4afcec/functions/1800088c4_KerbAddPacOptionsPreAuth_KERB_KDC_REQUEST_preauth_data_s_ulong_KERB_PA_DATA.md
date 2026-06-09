# KerbAddPacOptionsPreAuth(KERB_KDC_REQUEST_preauth_data_s * *,ulong,KERB_PA_DATA *)

- ea: `0x1800088c4`
- end: `0x180008e0f`
- name: `?KerbAddPacOptionsPreAuth@@YAJPEAPEAUKERB_KDC_REQUEST_preauth_data_s@@KPEAUKERB_PA_DATA@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(struct KERB_KDC_REQUEST_preauth_data_s **, unsigned int, struct KERB_PA_DATA *)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180019678`
- `0x180042a40`
- `0x180061e4c`
- `0x1800c0374`

## callees

- `0x1800069a0`
- `0x1800088c4`
- `0x1800093f0`
- `0x1800113f0`
- `0x18001e570`
- `0x180030ea8`
- `0x18006ccec`
- `0x18006d73c`
- `0x1800744cf`
- `0x180077804`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008bd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008bd4`
- `MSASN1!ASN1_CreateModule` at `0x1800089cb`
- `MSASN1!ASN1_CreateModule` at `0x180008c93`
- `MSASN1!ASN1_CreateModule` at `0x1800089cb`
- `MSASN1!ASN1_CreateModule` at `0x180008c93`
- `MSASN1!ASN1_CloseDecoder` at `0x180008b49`
- `MSASN1!ASN1_CloseDecoder` at `0x180008b49`
- `MSASN1!ASN1_CreateDecoder` at `0x1800089f7`
- `MSASN1!ASN1_CreateDecoder` at `0x1800089f7`
- `MSASN1!ASN1_Decode` at `0x180008a8c`
- `MSASN1!ASN1_Decode` at `0x180008a8c`
- `MSASN1!ASN1_CreateEncoder` at `0x180008cbb`
- `MSASN1!ASN1_CreateEncoder` at `0x180008cbb`
- `MSASN1!ASN1_FreeEncoded` at `0x180008d97`
- `MSASN1!ASN1_FreeEncoded` at `0x180008d97`
- `MSASN1!ASN1_Encode` at `0x180008d1b`
- `MSASN1!ASN1_Encode` at `0x180008d1b`
- `MSASN1!ASN1_CloseEncoder` at `0x180008da6`
- `MSASN1!ASN1_CloseEncoder` at `0x180008da6`

## pseudocode

```c
__int64 __fastcall KerbAddPacOptionsPreAuth(
        struct KERB_KDC_REQUEST_preauth_data_s **a1,
        int a2,
        struct KERB_PA_DATA *a3)
{
  struct KERB_KDC_REQUEST_preauth_data_s *v3; // rsi
  struct KERB_KDC_REQUEST_preauth_data_s **v4; // r15
  int v6; // ebx
  struct KERB_KDC_REQUEST_preauth_data_s *v7; // rdi
  int v8; // edi
  __int64 v9; // r12
  __int64 Module; // rax
  unsigned int v11; // eax
  PVOID *v12; // rcx
  int v13; // r15d
  int v14; // edi
  PVOID *v15; // rcx
  unsigned int v16; // ebx
  struct KERB_KDC_REQUEST_preauth_data_s *v17; // rax
  __int64 v18; // rax
  unsigned int v19; // eax
  int v20; // eax
  void *v21; // rax
  struct KERB_KDC_REQUEST_preauth_data_s **v22; // rcx
  int v23; // eax
  struct KERB_KDC_REQUEST_preauth_data_s *v24; // rcx
  struct KERB_KDC_REQUEST_preauth_data_s *v25; // rdx
  struct tagASN1bitstring_t *v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h] BYREF
  unsigned int *v30; // [rsp+68h] [rbp-8h]
  struct KERB_KDC_REQUEST_preauth_data_s **v31; // [rsp+B0h] [rbp+40h] BYREF
  int v32; // [rsp+B8h] [rbp+48h]
  unsigned int v33; // [rsp+C8h] [rbp+58h] BYREF

  v32 = a2;
  v31 = a1;
  v3 = *a1;
  v29 = 0;
  v4 = a1;
  v30 = 0;
  v27 = 0;
  v33 = 0;
  v6 = 60;
  while ( v3 )
  {
    if ( *((_DWORD *)v3 + 2) == 167 )
    {
      v8 = *((_DWORD *)v3 + 4);
      v28 = 0;
      if ( !v8 || (v9 = *((_QWORD *)v3 + 3)) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids);
        return (unsigned int)-1073741670;
      }
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
      v11 = ASN1_CreateDecoder(Module, &v28, 0, 0, 0);
      if ( v11 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v11);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
            WPP_SF_D(v12[2], 39, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
        }
        return (unsigned int)-1073741670;
      }
      v13 = 0;
      v27 = 0;
      v14 = ASN1_Decode(v28, &v27, 41, 8, v9, v8);
      if ( v14 < 0 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
            (unsigned int)v14);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        switch ( v14 )
        {
          case -1009:
            goto LABEL_31;
          case -1011:
            goto LABEL_29;
          case -1002:
LABEL_31:
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
              WPP_SF_d(v15[2], 41, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 41);
            v13 = -2147483647;
            break;
          default:
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
              WPP_SF_d(v15[2], 42, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, (unsigned int)v14);
LABEL_29:
            v13 = 60;
            break;
        }
        v27 = 0;
      }
      if ( v28 )
        ASN1_CloseDecoder();
      if ( v13 )
        return (unsigned int)-1073741670;
      v33 = KerbConvertFlagsToUlong(v27);
      KerbFreeData(41);
      v7 = v3;
      if ( a3 )
      {
        *(_OWORD *)a3 = *(_OWORD *)((char *)v3 + 8);
        *((_QWORD *)a3 + 2) = *((_QWORD *)v3 + 3);
      }
      else
      {
        KerbFree(*((_QWORD *)v3 + 3));
      }
      v4 = v31;
      *((_QWORD *)v3 + 3) = 0;
      *((_DWORD *)v3 + 4) = 0;
      goto LABEL_49;
    }
    v3 = *(struct KERB_KDC_REQUEST_preauth_data_s **)v3;
  }
  if ( KerbGlobalPackageState == 1 )
  {
    v7 = (struct KERB_KDC_REQUEST_preauth_data_s *)((__int64 (__fastcall *)(__int64, __int64 *, __int64 (__fastcall **)(), __int64 (__fastcall **)()))LsaFunctions->AllocateLsaHeap)(
                                                     32,
                                                     qword_1800FE8B0,
                                                     off_1800F6560,
                                                     off_1800F6040);
  }
  else
  {
    v17 = (struct KERB_KDC_REQUEST_preauth_data_s *)LocalAlloc(0, 0x20u);
    v7 = v17;
    if ( v17 )
    {
      *(_OWORD *)v17 = 0;
      *((_OWORD *)v17 + 1) = 0;
    }
  }
  if ( !v7 )
    return (unsigned int)-1073741670;
LABEL_49:
  *((_DWORD *)v7 + 2) = 167;
  BYTE3(v31) = v32 | v33;
  LOBYTE(v31) = (v32 | v33) >> 24;
  BYTE1(v31) = (v32 | v33) >> 16;
  BYTE2(v31) = (unsigned __int16)(v32 | v33) >> 8;
  v33 = (unsigned int)v31;
  v30 = &v33;
  LODWORD(v29) = 32;
  v31 = 0;
  if ( fKRB5ModuleStarted )
  {
    v18 = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    v18 = ASN1_CreateModule(
            0x10000,
            1024,
            4096,
            81,
            off_1800F62D0,
            off_1800F6040,
            off_1800F6560,
            qword_1800FE8B0,
            895644267);
    KRB5_Module = v18;
  }
  v19 = ASN1_CreateEncoder(v18, &v31, 0, 0, 0);
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v19);
  }
  else
  {
    v20 = ASN1_Encode(v31, &v29, 41, 16, 0, 0);
    if ( v20 >= 0 )
    {
      v21 = MIDL_user_allocate(*((unsigned int *)v31 + 7));
      *((_QWORD *)v7 + 3) = v21;
      if ( v21 )
      {
        v6 = 0;
        memcpy_0(v21, v31[2], *((unsigned int *)v31 + 7));
        v22 = v31;
        v23 = *((_DWORD *)v31 + 7);
      }
      else
      {
        v22 = v31;
        v23 = 0;
      }
      *((_DWORD *)v7 + 4) = v23;
      ASN1_FreeEncoded(v22, v22[2]);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v20);
    }
  }
  if ( v31 )
    ASN1_CloseEncoder();
  if ( v6 )
  {
    v16 = -1073741670;
    if ( v7 != v3 )
      KerbFreePreAuthData(v7);
  }
  else
  {
    v16 = 0;
    if ( v7 != v3 )
    {
      v24 = *v4;
      if ( *v4 )
      {
        v25 = *(struct KERB_KDC_REQUEST_preauth_data_s **)v24;
        if ( *(_QWORD *)v24 )
        {
          do
          {
            v24 = v25;
            v25 = *(struct KERB_KDC_REQUEST_preauth_data_s **)v25;
          }
          while ( v25 );
        }
        *(_QWORD *)v24 = v7;
      }
      else
      {
        *v4 = v7;
      }
      *(_QWORD *)v7 = 0;
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800088c4  mov     [rsp-38h+arg_10], rbx
0x1800088c9  mov     [rsp-38h+arg_8], edx
0x1800088cd  mov     [rsp-38h+arg_0], rcx
0x1800088d2  push    rbp
0x1800088d3  push    rsi
0x1800088d4  push    rdi
0x1800088d5  push    r12
0x1800088d7  push    r13
0x1800088d9  push    r14
0x1800088db  push    r15
0x1800088dd  mov     rbp, rsp
0x1800088e0  sub     rsp, 70h
0x1800088e4  mov     rsi, [rcx]
0x1800088e7  lea     rdx, qword_1800FE8B0
0x1800088ee  xor     r12d, r12d
0x1800088f1  lea     r9, off_1800F6040
0x1800088f8  xor     eax, eax
0x1800088fa  mov     [rbp+var_10], r12
0x1800088fe  mov     r15, rcx
0x180008901  mov     [rbp+var_8], rax
0x180008905  mov     r13, r8
0x180008908  mov     [rbp+var_20], r12
0x18000890c  mov     [rbp+arg_18], r12d
0x180008910  lea     r8, off_1800F6560
0x180008917  lea     ecx, [rax+20h]
0x18000891a  lea     ebx, [rcx+1Ch]
0x18000891d  lea     r10, off_1800F62D0
0x180008924  lea     rax, WPP_GLOBAL_Control
0x18000892b  lea     r14, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180008932  jmp     short loc_180008940
0x180008934  cmp     dword ptr [rsi+8], 0A7h
0x18000893b  jz      short loc_18000896A
0x18000893d  mov     rsi, [rsi]
0x180008940  test    rsi, rsi
0x180008943  jnz     short loc_180008934
0x180008945  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000894c  jnz     loc_180008BCF
0x180008952  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180008959  mov     rax, [rax+28h]
0x18000895d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008962  mov     rdi, rax
0x180008965  jmp     loc_180008BEC
0x18000896a  mov     edi, [rsi+10h]
0x18000896d  mov     [rbp+var_18], r12
0x180008971  test    edi, edi
0x180008973  jz      loc_180008BA2
0x180008979  mov     r12, [rsi+18h]
0x18000897d  test    r12, r12
0x180008980  jz      loc_180008BA2
0x180008986  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x18000898d  jnz     short loc_1800089DA
0x18000898f  mov     [rsp+70h+var_30], 3562726Bh
0x180008997  mov     ecx, 10000h
0x18000899c  mov     [rsp+70h+var_38], rdx
0x1800089a1  mov     edx, 400h
0x1800089a6  mov     [rsp+70h+var_40], r8
0x1800089ab  mov     r8d, 1000h
0x1800089b1  mov     [rsp+70h+var_48], r9
0x1800089b6  mov     r9d, 51h ; 'Q'
0x1800089bc  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x1800089c6  mov     [rsp+70h+var_50], r10
0x1800089cb  call    cs:__imp_ASN1_CreateModule
0x1800089d1  mov     cs:KRB5_Module, rax
0x1800089d8  jmp     short loc_1800089E1
0x1800089da  mov     rax, cs:KRB5_Module
0x1800089e1  xor     r9d, r9d
0x1800089e4  mov     [rsp+70h+var_50], 0
0x1800089ed  xor     r8d, r8d
0x1800089f0  lea     rdx, [rbp+var_18]
0x1800089f4  mov     rcx, rax
0x1800089f7  call    cs:__imp_ASN1_CreateDecoder
0x1800089fd  test    eax, eax
0x1800089ff  jz      short loc_180008A6C
0x180008a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a08  lea     r13, WPP_GLOBAL_Control
0x180008a0f  cmp     rcx, r13
0x180008a12  jz      loc_180008BC5
0x180008a18  test    byte ptr [rcx+1Ch], 1
0x180008a1c  lea     r14, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180008a23  jz      short loc_180008A40
0x180008a25  mov     rcx, [rcx+10h]
0x180008a29  mov     edx, 24h ; '$'
0x180008a2e  mov     r9d, eax
0x180008a31  mov     r8, r14
0x180008a34  call    WPP_SF_D
0x180008a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a40  cmp     rcx, r13
0x180008a43  jz      loc_180008BC5
0x180008a49  test    byte ptr [rcx+1Ch], 1
0x180008a4d  jz      loc_180008BC5
0x180008a53  mov     rcx, [rcx+10h]
0x180008a57  mov     edx, 27h ; '''
0x180008a5c  mov     r9d, ebx
0x180008a5f  mov     r8, r14
0x180008a62  call    WPP_SF_D
0x180008a67  jmp     loc_180008BC5
0x180008a6c  mov     rcx, [rbp+var_18]
0x180008a70  lea     rdx, [rbp+var_20]
0x180008a74  xor     r15d, r15d
0x180008a77  mov     dword ptr [rsp+70h+var_48], edi
0x180008a7b  mov     [rbp+var_20], r15
0x180008a7f  mov     [rsp+70h+var_50], r12
0x180008a84  lea     r9d, [r15+8]
0x180008a88  lea     r8d, [r15+29h]
0x180008a8c  call    cs:__imp_ASN1_Decode
0x180008a92  xor     r12d, r12d
0x180008a95  mov     edi, eax
0x180008a97  test    eax, eax
0x180008a99  jns     loc_180008B40
0x180008a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aa6  lea     rax, WPP_GLOBAL_Control
0x180008aad  cmp     rcx, rax
0x180008ab0  jz      short loc_180008AD9
0x180008ab2  test    byte ptr [rcx+1Ch], 4
0x180008ab6  jz      short loc_180008AD9
0x180008ab8  mov     rcx, [rcx+10h]
0x180008abc  lea     edx, [r15+28h]
0x180008ac0  mov     r9d, edi
0x180008ac3  mov     r8, r14
0x180008ac6  call    WPP_SF_D
0x180008acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ad2  lea     rax, WPP_GLOBAL_Control
0x180008ad9  cmp     edi, 0FFFFFC0Fh
0x180008adf  jz      short loc_180008B15
0x180008ae1  cmp     edi, 0FFFFFC0Dh
0x180008ae7  jz      short loc_180008B10
0x180008ae9  cmp     edi, 0FFFFFC16h
0x180008aef  jz      short loc_180008B15
0x180008af1  cmp     rcx, rax
0x180008af4  jz      short loc_180008B10
0x180008af6  test    byte ptr [rcx+1Ch], 1
0x180008afa  jz      short loc_180008B10
0x180008afc  mov     rcx, [rcx+10h]
0x180008b00  mov     edx, 2Ah ; '*'
0x180008b05  mov     r9d, edi
0x180008b08  mov     r8, r14
0x180008b0b  call    WPP_SF_d
0x180008b10  mov     r15d, ebx
0x180008b13  jmp     short loc_180008B3C
0x180008b15  cmp     rcx, rax
0x180008b18  jz      short loc_180008B36
0x180008b1a  test    byte ptr [rcx+1Ch], 4
0x180008b1e  jz      short loc_180008B36
0x180008b20  mov     rcx, [rcx+10h]
0x180008b24  mov     eax, 29h ; ')'
0x180008b29  mov     edx, eax
0x180008b2b  mov     r9d, eax
0x180008b2e  mov     r8, r14
0x180008b31  call    WPP_SF_d
0x180008b36  mov     r15d, 80000001h
0x180008b3c  mov     [rbp+var_20], r12
0x180008b40  mov     rcx, [rbp+var_18]
0x180008b44  test    rcx, rcx
0x180008b47  jz      short loc_180008B4F
0x180008b49  call    cs:__imp_ASN1_CloseDecoder
0x180008b4f  test    r15d, r15d
0x180008b52  jnz     short loc_180008BC5
0x180008b54  mov     rcx, [rbp+var_20]; struct tagASN1bitstring_t *
0x180008b58  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x180008b5d  mov     rdx, [rbp+var_20]
0x180008b61  lea     ecx, [r15+29h]
0x180008b65  mov     [rbp+arg_18], eax
0x180008b68  call    KerbFreeData
0x180008b6d  mov     rdi, rsi
0x180008b70  test    r13, r13
0x180008b73  jz      short loc_180008B8B
0x180008b75  movups  xmm0, xmmword ptr [rsi+8]
0x180008b79  movups  xmmword ptr [r13+0], xmm0
0x180008b7e  movsd   xmm1, qword ptr [rsi+18h]
0x180008b83  movsd   qword ptr [r13+10h], xmm1
0x180008b89  jmp     short loc_180008B94
0x180008b8b  mov     rcx, [rsi+18h]
0x180008b8f  call    KerbFree
0x180008b94  mov     r15, [rbp+arg_0]
0x180008b98  mov     [rsi+18h], r12
0x180008b9c  mov     [rsi+10h], r12d
0x180008ba0  jmp     short loc_180008BF1
0x180008ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ba9  cmp     rcx, rax
0x180008bac  jz      short loc_180008BC5
0x180008bae  test    byte ptr [rcx+1Ch], 1
0x180008bb2  jz      short loc_180008BC5
0x180008bb4  mov     rcx, [rcx+10h]
0x180008bb8  mov     edx, 26h ; '&'
0x180008bbd  mov     r8, r14
0x180008bc0  call    WPP_SF_
0x180008bc5  mov     ebx, 0C000009Ah
0x180008bca  jmp     loc_180008DF5
0x180008bcf  mov     rdx, rcx; uBytes
0x180008bd2  xor     ecx, ecx; uFlags
0x180008bd4  call    cs:__imp_LocalAlloc
0x180008bda  mov     rdi, rax
0x180008bdd  test    rax, rax
0x180008be0  jz      short loc_180008BEC
0x180008be2  xorps   xmm0, xmm0
0x180008be5  movups  xmmword ptr [rax], xmm0
0x180008be8  movups  xmmword ptr [rax+10h], xmm0
0x180008bec  test    rdi, rdi
0x180008bef  jz      short loc_180008BC5
0x180008bf1  mov     dword ptr [rdi+8], 0A7h
0x180008bf8  mov     ecx, [rbp+arg_18]
0x180008bfb  or      ecx, [rbp+arg_8]
0x180008bfe  mov     eax, ecx
0x180008c00  mov     byte ptr [rbp+arg_0+3], cl
0x180008c03  shr     eax, 18h
0x180008c06  mov     byte ptr [rbp+arg_0], al
0x180008c09  mov     eax, ecx
0x180008c0b  shr     eax, 10h
0x180008c0e  mov     byte ptr [rbp+arg_0+1], al
0x180008c11  mov     eax, ecx
0x180008c13  shr     eax, 8
0x180008c16  cmp     cs:?fKRB5ModuleStarted@@3HA, r12d; int fKRB5ModuleStarted
0x180008c1d  mov     byte ptr [rbp+arg_0+2], al
0x180008c20  mov     eax, dword ptr [rbp+arg_0]
0x180008c23  mov     [rbp+arg_18], eax
0x180008c26  lea     rax, [rbp+arg_18]
0x180008c2a  mov     [rbp+var_8], rax
0x180008c2e  mov     dword ptr [rbp+var_10], 20h ; ' '
0x180008c35  mov     [rbp+arg_0], r12
0x180008c39  jnz     short loc_180008CA2
0x180008c3b  mov     [rsp+70h+var_30], 3562726Bh
0x180008c43  lea     rax, qword_1800FE8B0
0x180008c4a  mov     [rsp+70h+var_38], rax
0x180008c4f  mov     edx, 400h
0x180008c54  lea     rax, off_1800F6560
0x180008c5b  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180008c65  mov     [rsp+70h+var_40], rax
0x180008c6a  mov     ecx, 10000h
0x180008c6f  lea     rax, off_1800F6040
0x180008c76  mov     r9d, 51h ; 'Q'
0x180008c7c  mov     [rsp+70h+var_48], rax
0x180008c81  mov     r8d, 1000h
0x180008c87  lea     rax, off_1800F62D0
0x180008c8e  mov     [rsp+70h+var_50], rax
0x180008c93  call    cs:__imp_ASN1_CreateModule
0x180008c99  mov     cs:KRB5_Module, rax
0x180008ca0  jmp     short loc_180008CA9
0x180008ca2  mov     rax, cs:KRB5_Module
0x180008ca9  xor     r9d, r9d
0x180008cac  mov     [rsp+70h+var_50], r12
0x180008cb1  xor     r8d, r8d
0x180008cb4  lea     rdx, [rbp+arg_0]
0x180008cb8  mov     rcx, rax
0x180008cbb  call    cs:__imp_ASN1_CreateEncoder
0x180008cc1  test    eax, eax
0x180008cc3  jz      short loc_180008CFF
0x180008cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ccc  lea     r13, WPP_GLOBAL_Control
0x180008cd3  cmp     rcx, r13
0x180008cd6  jz      loc_180008D9D
0x180008cdc  test    byte ptr [rcx+1Ch], 1
0x180008ce0  jz      loc_180008D9D
0x180008ce6  mov     rcx, [rcx+10h]
0x180008cea  mov     edx, 24h ; '$'
0x180008cef  mov     r9d, eax
0x180008cf2  mov     r8, r14
0x180008cf5  call    WPP_SF_D
0x180008cfa  jmp     loc_180008D9D
0x180008cff  mov     rcx, [rbp+arg_0]
0x180008d03  lea     rdx, [rbp+var_10]
0x180008d07  mov     r9d, 10h
0x180008d0d  mov     dword ptr [rsp+70h+var_48], r12d
0x180008d12  mov     [rsp+70h+var_50], r12
0x180008d17  lea     r8d, [r9+19h]
0x180008d1b  call    cs:__imp_ASN1_Encode
0x180008d21  test    eax, eax
0x180008d23  jns     short loc_180008D54
0x180008d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d2c  lea     r13, WPP_GLOBAL_Control
0x180008d33  cmp     rcx, r13
0x180008d36  jz      short loc_180008D9D
0x180008d38  test    byte ptr [rcx+1Ch], 1
0x180008d3c  jz      short loc_180008D9D
0x180008d3e  mov     rcx, [rcx+10h]
0x180008d42  mov     edx, 25h ; '%'
0x180008d47  mov     r9d, eax
0x180008d4a  mov     r8, r14
0x180008d4d  call    WPP_SF_d
0x180008d52  jmp     short loc_180008D9D
0x180008d54  mov     rax, [rbp+arg_0]
0x180008d58  mov     ecx, [rax+1Ch]; size
0x180008d5b  call    MIDL_user_allocate
0x180008d60  mov     [rdi+18h], rax
0x180008d64  test    rax, rax
0x180008d67  jnz     short loc_180008D72
0x180008d69  mov     rcx, [rbp+arg_0]
0x180008d6d  mov     eax, r12d
0x180008d70  jmp     short loc_180008D90
0x180008d72  mov     rdx, [rbp+arg_0]
0x180008d76  mov     rcx, rax; void *
0x180008d79  mov     ebx, r12d
0x180008d7c  mov     r8d, [rdx+1Ch]; Size
0x180008d80  mov     rdx, [rdx+10h]; Src
0x180008d84  call    memcpy_0
0x180008d89  mov     rcx, [rbp+arg_0]
0x180008d8d  mov     eax, [rcx+1Ch]
0x180008d90  mov     [rdi+10h], eax
0x180008d93  mov     rdx, [rcx+10h]
0x180008d97  call    cs:__imp_ASN1_FreeEncoded
0x180008d9d  mov     rcx, [rbp+arg_0]
  ... truncated ...
```
