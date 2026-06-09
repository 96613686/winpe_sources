# Pku2uBuildApRequest(_PKU2U_CONTEXT *,KERB_ERROR *,uchar * *,ulong *,_SEC_CHANNEL_BINDINGS *)

- ea: `0x180006250`
- end: `0x18000718f`
- name: `?Pku2uBuildApRequest@@YAJPEAU_PKU2U_CONTEXT@@PEAUKERB_ERROR@@PEAPEAEPEAKPEAU_SEC_CHANNEL_BINDINGS@@@Z`
- size: `3903`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct KERB_ERROR *, unsigned __int8 **, unsigned int *, struct _SEC_CHANNEL_BINDINGS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cc90`

## callees

- `0x1800057f0`
- `0x180006250`
- `0x1800071a0`
- `0x1800075d0`
- `0x180007800`
- `0x180007b18`
- `0x180007dc8`
- `0x180015190`
- `0x180016a10`
- `0x18001a1d0`
- `0x18001a448`
- `0x180021a54`
- `0x180023ce0`
- `0x180023d9c`
- `0x1800313ec`
- `0x180038e7c`
- `0x180044d98`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800062c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800062c6`
- `MSASN1!ASN1_CreateEncoder` at `0x18000661d`
- `MSASN1!ASN1_CreateEncoder` at `0x1800068f4`
- `MSASN1!ASN1_CreateEncoder` at `0x180006e0c`
- `MSASN1!ASN1_CreateEncoder` at `0x18000661d`
- `MSASN1!ASN1_CreateEncoder` at `0x1800068f4`
- `MSASN1!ASN1_CreateEncoder` at `0x180006e0c`
- `MSASN1!ASN1_CloseEncoder` at `0x180006797`
- `MSASN1!ASN1_CloseEncoder` at `0x180006a7e`
- `MSASN1!ASN1_CloseEncoder` at `0x180006f73`
- `MSASN1!ASN1_CloseEncoder` at `0x180006797`
- `MSASN1!ASN1_CloseEncoder` at `0x180006a7e`
- `MSASN1!ASN1_CloseEncoder` at `0x180006f73`
- `MSASN1!ASN1_Encode` at `0x180006688`
- `MSASN1!ASN1_Encode` at `0x18000696a`
- `MSASN1!ASN1_Encode` at `0x180006e7b`
- `MSASN1!ASN1_Encode` at `0x180006688`
- `MSASN1!ASN1_Encode` at `0x18000696a`
- `MSASN1!ASN1_Encode` at `0x180006e7b`
- `MSASN1!ASN1_FreeEncoded` at `0x18000677f`
- `MSASN1!ASN1_FreeEncoded` at `0x180006a66`
- `MSASN1!ASN1_FreeEncoded` at `0x180006f5c`
- `MSASN1!ASN1_FreeEncoded` at `0x18000677f`
- `MSASN1!ASN1_FreeEncoded` at `0x180006a66`
- `MSASN1!ASN1_FreeEncoded` at `0x180006f5c`
- `MSASN1!ASN1_CreateModule` at `0x1800065f2`
- `MSASN1!ASN1_CreateModule` at `0x1800068c9`
- `MSASN1!ASN1_CreateModule` at `0x180006de3`
- `MSASN1!ASN1_CreateModule` at `0x1800065f2`
- `MSASN1!ASN1_CreateModule` at `0x1800068c9`
- `MSASN1!ASN1_CreateModule` at `0x180006de3`
- `bcrypt!BCryptGenRandom` at `0x180006322`
- `bcrypt!BCryptGenRandom` at `0x180006322`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000650f`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000650f`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x180006444`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x180006444`

## string_xrefs

- `0x1800063fa`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x180006d46`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uBuildApRequest(
        struct _PKU2U_CONTEXT *a1,
        struct KERB_ERROR *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        struct _SEC_CHANNEL_BINDINGS *a5)
{
  char *v8; // rsi
  struct PKERB_AUTHORIZATION_DATA *v9; // r14
  void *v10; // r13
  unsigned int *v11; // r15
  signed int v12; // ebx
  void (*v13)(void); // rax
  int Key; // eax
  union _LARGE_INTEGER v15; // rbx
  _OWORD *v16; // rax
  __int64 Module; // rax
  unsigned int v18; // eax
  int v19; // ebx
  int v20; // eax
  void *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  struct PKERB_AUTHORIZATION_DATA *QuadPart; // rcx
  struct PKERB_AUTHORIZATION_DATA *v25; // r8
  _QWORD *v26; // rdx
  __int64 v27; // rbx
  bool v28; // zf
  __int64 v29; // rax
  unsigned int v30; // eax
  int v31; // eax
  int v32; // eax
  void *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  union _LARGE_INTEGER *v36; // rbx
  union _LARGE_INTEGER AuthenticatorTime; // rax
  __int64 v38; // rcx
  const struct _UNICODE_STRING *v39; // r9
  __int64 v40; // r9
  struct KERB_ENCRYPTION_KEY *v41; // r10
  char v42; // r8
  char v43; // dl
  __int128 v44; // xmm1
  struct KERB_ENCRYPTION_KEY *v45; // rcx
  unsigned int v46; // edx
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  struct _KERB_INTERNAL_NAME *v49; // r9
  unsigned int v50; // eax
  unsigned int v51; // ebx
  PVOID *v52; // r8
  void *v53; // r15
  __int64 v54; // rax
  unsigned int v55; // eax
  PVOID *v56; // r10
  int v57; // eax
  size_t v58; // rbx
  struct PKERB_AUTHORIZATION_DATA *v59; // rcx
  void *v60; // rax
  void *v61; // rcx
  __int64 v62; // xmm1_8
  unsigned int v63; // eax
  __int64 v64; // rdx
  int v65; // eax
  unsigned int v66; // ecx
  unsigned int v67; // edi
  struct gss_OID_desc_struct *v68; // rcx
  unsigned __int8 *v69; // rbx
  unsigned __int8 *v70; // rax
  unsigned __int8 v72; // [rsp+40h] [rbp-C0h]
  struct PKERB_AUTHORIZATION_DATA *v73; // [rsp+50h] [rbp-B0h] BYREF
  struct PKERB_AUTHORIZATION_DATA *v74; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER v75; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v76; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v77; // [rsp+78h] [rbp-88h] BYREF
  __int128 v78; // [rsp+80h] [rbp-80h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h]
  union _LARGE_INTEGER Time; // [rsp+98h] [rbp-68h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v82; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v83; // [rsp+B0h] [rbp-50h] BYREF
  int v84; // [rsp+B8h] [rbp-48h]
  int v85; // [rsp+BCh] [rbp-44h]
  int v86; // [rsp+C0h] [rbp-40h]
  int v87; // [rsp+C4h] [rbp-3Ch]
  _DWORD *v88; // [rsp+C8h] [rbp-38h]
  __int128 v89; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v90; // [rsp+E0h] [rbp-20h]
  _DWORD v91[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v92; // [rsp+F8h] [rbp-8h]
  unsigned int *v93; // [rsp+100h] [rbp+0h]
  __int128 v94; // [rsp+108h] [rbp+8h]
  __int128 v95; // [rsp+118h] [rbp+18h]
  __int128 v96; // [rsp+128h] [rbp+28h]
  __int128 v97; // [rsp+138h] [rbp+38h]
  _OWORD v98[2]; // [rsp+148h] [rbp+48h] BYREF
  void *v99; // [rsp+168h] [rbp+68h]
  unsigned int Size; // [rsp+1C0h] [rbp+C0h]
  int Sizea; // [rsp+1C0h] [rbp+C0h]
  int Sizeb; // [rsp+1C0h] [rbp+C0h]
  unsigned int Sizec; // [rsp+1C0h] [rbp+C0h]
  unsigned int v104; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int8 *v105; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v106; // [rsp+1D8h] [rbp+D8h] BYREF

  v105 = (unsigned __int8 *)a3;
  v104 = 0;
  v90 = 0;
  v73 = 0;
  v8 = (char *)a1 + 176;
  Time.QuadPart = 0;
  v9 = 0;
  v79 = 0;
  v10 = 0;
  *a4 = 0;
  *a3 = 0;
  v89 = 0;
  v78 = 0;
  if ( a2 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    KerbConvertGeneralizedTimeToLargeInt(&Time, (struct KERB_ERROR *)((char *)a2 + 32), *((_DWORD *)a2 + 12));
    _InterlockedExchange(
      (volatile __int32 *)(*(_QWORD *)v8 + 176LL),
      (signed int)(Time.LowPart - SystemTimeAsFileTime.dwLowDateTime) / 10000000);
  }
  v11 = (unsigned int *)((char *)a1 + 288);
  if ( a1 == (struct _PKU2U_CONTEXT *)-288LL )
    goto LABEL_6;
  if ( BCryptGenRandom(0, (PUCHAR)a1 + 288, 4u, 2u) < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_6:
    v12 = -1073741670;
    goto LABEL_7;
  }
  *v11 &= ~0x80000000;
  Key = KerbMakeKeyEx(*(_DWORD *)(*(_QWORD *)v8 + 56LL), 0, 0, 0, 0, 0, 0, (struct KERB_ENCRYPTION_KEY *)&v78);
  if ( Key )
  {
    v12 = KerbMapKerbError(Key);
    goto LABEL_7;
  }
  v12 = Pku2uBuildGssChecksum((struct KERB_ENCRYPTION_KEY *)&v78, a1, (struct KERB_CHECKSUM *)&v89, &v104, a5);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v12,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        100);
    goto LABEL_7;
  }
  v74 = 0;
  v77 = 0;
  v12 = LsaIGetSupplementalTokenInfo(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 24LL) + 32LL), &v77);
  if ( v12 < 0 )
    goto LABEL_23;
  v83 = 0;
  v85 = 0;
  v87 = 0;
  v82 = &v83;
  v84 = v77[1];
  v86 = *v77 - 8;
  v88 = v77 + 2;
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v75.QuadPart = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(32);
    v15 = v75;
    if ( !v75.QuadPart )
    {
LABEL_19:
      v12 = -1073741801;
LABEL_20:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          (unsigned int)v12);
      goto LABEL_23;
    }
  }
  else
  {
    v16 = (_OWORD *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(32);
    v75.QuadPart = (LONGLONG)v16;
    v15.QuadPart = (LONGLONG)v16;
    if ( !v16 )
      goto LABEL_19;
    *v16 = 0;
    v16[1] = 0;
  }
  v106 = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v18 = ASN1_CreateEncoder(Module, &v106, 0, 0, 0);
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v18);
      v19 = 60;
      goto LABEL_53;
    }
    goto LABEL_44;
  }
  v20 = ASN1_Encode(v106, &v82, 29, 16, 0, 0);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v20);
LABEL_44:
    v19 = 60;
    goto LABEL_53;
  }
  Size = *(_DWORD *)(v106 + 28);
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v21 = (void *)(*(__int64 (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))();
  }
  else
  {
    v21 = (void *)(**((__int64 (***)(void))Pku2uGlobalBaseSSP + 31))();
    *(_QWORD *)&v76.Length = v21;
    if ( v21 )
    {
      memset_0(v21, 0, Size);
      v21 = *(void **)&v76.Length;
      *(_QWORD *)(v15.QuadPart + 24) = *(_QWORD *)&v76.Length;
      goto LABEL_51;
    }
  }
  *(_QWORD *)(v15.QuadPart + 24) = v21;
  if ( v21 )
  {
LABEL_51:
    Sizea = 0;
    memcpy_0(v21, *(const void **)(v106 + 16), *(unsigned int *)(v106 + 28));
    v22 = v106;
    LODWORD(v21) = *(_DWORD *)(v106 + 28);
    goto LABEL_52;
  }
  v22 = v106;
  Sizea = 60;
LABEL_52:
  *(_DWORD *)(v15.QuadPart + 16) = (_DWORD)v21;
  ASN1_FreeEncoded(v22, *(_QWORD *)(v22 + 16));
  v19 = Sizea;
LABEL_53:
  if ( v106 )
    ASN1_CloseEncoder();
  v23 = KerbMapKerbError(v19);
  QuadPart = (struct PKERB_AUTHORIZATION_DATA *)v75.QuadPart;
  v12 = v23;
  if ( v23 < 0 )
  {
    KerbFreeAuthData((struct PKERB_AUTHORIZATION_DATA *)v75.QuadPart);
    goto LABEL_20;
  }
  *(_QWORD *)v75.QuadPart = 0;
  *((_DWORD *)QuadPart + 2) = 141;
  v25 = v74;
  if ( v74 )
  {
    do
    {
      v26 = v25;
      v25 = *(struct PKERB_AUTHORIZATION_DATA **)v25;
    }
    while ( v25 );
    *v26 = QuadPart;
    QuadPart = v74;
  }
  else
  {
    v74 = QuadPart;
  }
  if ( !QuadPart )
  {
    v12 = 0;
    goto LABEL_25;
  }
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v27 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(32);
  }
  else
  {
    v27 = (**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(32);
    if ( v27 )
    {
      *(_QWORD *)(v27 + 12) = 0;
      *(_QWORD *)(v27 + 20) = 0;
      *(_DWORD *)(v27 + 28) = 0;
LABEL_68:
      v28 = fKRB5ModuleStarted == 0;
      *(_QWORD *)v27 = 0;
      *(_DWORD *)(v27 + 8) = 1;
      v106 = 0;
      if ( v28 )
      {
        fKRB5ModuleStarted = 1;
        v29 = ASN1_CreateModule(
                0x10000,
                1024,
                4096,
                49,
                off_180047350,
                off_1800471C0,
                off_180047030,
                qword_180049F80,
                846556016);
        PKU2UMSG_Module = v29;
      }
      else
      {
        v29 = PKU2UMSG_Module;
      }
      v30 = ASN1_CreateEncoder(v29, &v106, 0, 0, 0);
      if ( v30 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v30);
          v31 = 60;
          Sizeb = 60;
LABEL_88:
          if ( v106 )
          {
            ASN1_CloseEncoder();
            v31 = Sizeb;
          }
          if ( v31 )
          {
            KerbFreeData(1u, *(void **)(v27 + 24));
            Pku2uFree((void *)v27);
            v12 = -1073741801;
          }
          else
          {
            v9 = (struct PKERB_AUTHORIZATION_DATA *)v27;
            v73 = (struct PKERB_AUTHORIZATION_DATA *)v27;
            v12 = 0;
          }
          goto LABEL_23;
        }
LABEL_79:
        v31 = 60;
        Sizeb = 60;
        goto LABEL_88;
      }
      v32 = ASN1_Encode(v106, &v74, 1, 16, 0, 0);
      if ( v32 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
            (unsigned int)v32);
        goto LABEL_79;
      }
      Sizec = *(_DWORD *)(v106 + 28);
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v33 = (void *)(*(__int64 (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))();
      }
      else
      {
        v33 = (void *)(**((__int64 (***)(void))Pku2uGlobalBaseSSP + 31))();
        *(_QWORD *)&v76.Length = v33;
        if ( v33 )
        {
          memset_0(v33, 0, Sizec);
          v33 = *(void **)&v76.Length;
          *(_QWORD *)(v27 + 24) = *(_QWORD *)&v76.Length;
          goto LABEL_86;
        }
      }
      *(_QWORD *)(v27 + 24) = v33;
      if ( !v33 )
      {
        v34 = v106;
        Sizeb = 60;
LABEL_87:
        *(_DWORD *)(v27 + 16) = (_DWORD)v33;
        ASN1_FreeEncoded(v34, *(_QWORD *)(v34 + 16));
        v31 = Sizeb;
        goto LABEL_88;
      }
LABEL_86:
      Sizeb = 0;
      memcpy_0(v33, *(const void **)(v106 + 16), *(unsigned int *)(v106 + 28));
      v34 = v106;
      LODWORD(v33) = *(_DWORD *)(v106 + 28);
      goto LABEL_87;
    }
  }
  if ( v27 )
    goto LABEL_68;
  v12 = -1073741801;
LABEL_23:
  if ( v74 )
    KerbFreeAuthData(v74);
LABEL_25:
  if ( v77 )
    LsaIFreeSupplementalTokenInfo();
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v12);
    goto LABEL_7;
  }
  v35 = *(_QWORD *)v8;
  v36 = (union _LARGE_INTEGER *)((char *)a1 + 280);
  *((_QWORD *)a1 + 6) = *(_QWORD *)(*(_QWORD *)v8 + 88LL);
  v75.QuadPart = 10000000LL * *(int *)(v35 + 176);
  AuthenticatorTime = Pku2uGetAuthenticatorTime(&v75);
  v38 = *((_QWORD *)a1 + 4);
  *((union _LARGE_INTEGER *)a1 + 35) = AuthenticatorTime;
  if ( v38 && (*((unsigned int (__fastcall **)(__int64))Pku2uGlobalIdpExtTable + 2))(v38 + 120) )
  {
    v12 = Pku2uBuildClientPac(
            *(HANDLE *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 24LL) + 32LL),
            (union _LARGE_INTEGER *)a1 + 35,
            (struct KERB_ENCRYPTION_KEY *)(*(_QWORD *)v8 + 56LL),
            v39,
            &v73);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          (unsigned int)v12);
      v9 = v73;
      goto LABEL_7;
    }
    v9 = v73;
    v36 = (union _LARGE_INTEGER *)((char *)a1 + 280);
  }
  v40 = *(_QWORD *)v8;
  v41 = (struct KERB_ENCRYPTION_KEY *)&v78;
  v42 = v104;
  v43 = BYTE1(v104);
  if ( !v79 )
    v41 = 0;
  v44 = *(_OWORD *)(v40 + 120);
  BYTE1(v104) = BYTE2(v104);
  v76.Buffer = (PWSTR)L"WELLKNOWN:PKU2U";
  v45 = (struct KERB_ENCRYPTION_KEY *)(v40 + 56);
  BYTE2(v104) = v43;
  v46 = *v11;
  v99 = 0;
  LOBYTE(v104) = HIBYTE(v104);
  memset(v98, 0, sizeof(v98));
  HIBYTE(v104) = v42;
  v93 = &v104;
  v94 = *(_OWORD *)(v40 + 104);
  v47 = *(_OWORD *)(v40 + 136);
  v95 = v44;
  v48 = *(_OWORD *)(v40 + 152);
  *(_QWORD *)&v76.Length = 2097182;
  v96 = v47;
  v92 = 32;
  *(_QWORD *)&v47 = *(_QWORD *)(v40 + 168);
  v49 = *(struct _KERB_INTERNAL_NAME **)(v40 + 40);
  v91[0] = 5;
  v91[1] = 14;
  v97 = v48;
  *(_QWORD *)&v98[0] = v47;
  v50 = KerbCreateAuthenticator(
          v45,
          v46,
          v36,
          v49,
          &v76,
          v41,
          v9,
          (struct KERB_CHECKSUM *)&v89,
          v72,
          (struct KERB_ENCRYPTED_DATA *)((char *)v98 + 8));
  v51 = v50;
  if ( v50 )
  {
    v52 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v50);
      LODWORD(v53) = 0;
LABEL_108:
      v52 = &WPP_GLOBAL_Control;
      goto LABEL_109;
    }
    LODWORD(v53) = 0;
    goto LABEL_109;
  }
  v73 = 0;
  if ( fKRB5ModuleStarted )
  {
    v54 = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    v54 = ASN1_CreateModule(
            0x10000,
            1024,
            4096,
            49,
            off_180047350,
            off_1800471C0,
            off_180047030,
            qword_180049F80,
            846556016);
    PKU2UMSG_Module = v54;
  }
  v55 = ASN1_CreateEncoder(v54, &v73, 0, 0, 0);
  if ( !v55 )
  {
    v57 = ASN1_Encode(v73, v91, 35, 16, 0, 0);
    if ( v57 < 0 )
    {
      v56 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          (unsigned int)v57);
        v56 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_127;
    }
    v58 = *((unsigned int *)v73 + 7);
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v53 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v58);
    }
    else
    {
      v60 = (void *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v58);
      v53 = v60;
      if ( v60 )
      {
        memset_0(v60, 0, v58);
        v10 = v53;
        goto LABEL_134;
      }
    }
    v10 = v53;
    if ( !v53 )
    {
      v59 = v73;
      v51 = 60;
LABEL_135:
      ASN1_FreeEncoded(v59, *((_QWORD *)v59 + 2));
      goto LABEL_136;
    }
LABEL_134:
    v51 = 0;
    memcpy_0(v53, *((const void **)v73 + 2), *((unsigned int *)v73 + 7));
    v59 = v73;
    LODWORD(v53) = *((_DWORD *)v73 + 7);
    goto LABEL_135;
  }
  v56 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
LABEL_127:
    v51 = 60;
    LODWORD(v53) = 0;
    goto LABEL_137;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v55);
  v51 = 60;
  LODWORD(v53) = 0;
LABEL_136:
  v56 = (PVOID *)WPP_GLOBAL_Control;
LABEL_137:
  if ( v73 )
  {
    ASN1_CloseEncoder();
    v56 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v51 )
    goto LABEL_108;
  v52 = &WPP_GLOBAL_Control;
  if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 )
  {
    WPP_SF_d(v56[2], 18, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v51);
    goto LABEL_108;
  }
LABEL_109:
  if ( v99 )
  {
    Pku2uFree(v99);
    v52 = &WPP_GLOBAL_Control;
  }
  _InterlockedExchange((volatile __int32 *)(*(_QWORD *)v8 + 176LL), (signed int)v75.LowPart / 10000000);
  if ( v51 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v51,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        174);
    v12 = KerbMapKerbError(v51);
    goto LABEL_7;
  }
  v61 = (void *)*((_QWORD *)a1 + 30);
  if ( v61 )
    Pku2uFree(v61);
  v62 = v79;
  *((_OWORD *)a1 + 14) = v78;
  v79 = 0;
  *a4 = 0;
  *((_QWORD *)a1 + 30) = v62;
  v63 = (_DWORD)pku2u_global_oids + 4;
  v78 = 0;
  if ( (unsigned int)pku2u_global_oids >= 0xFFFFFFFC )
  {
    *a4 = -1;
    v12 = -1073741675;
    goto LABEL_7;
  }
  v64 = v63 + (unsigned int)v53;
  if ( (unsigned int)v64 < v63 )
  {
    *a4 = -1;
    v12 = -1073741675;
    goto LABEL_7;
  }
  if ( (int)v64 >= 128 )
  {
    if ( (int)v64 >= 256 )
    {
      if ( (int)v64 >= 0x10000 )
        v65 = ((int)v64 >= 0x1000000) + 5;
      else
        v65 = 4;
    }
    else
    {
      v65 = 3;
    }
  }
  else
  {
    v65 = 2;
  }
  v66 = v65 + v64;
  v67 = -1;
  if ( v65 + (int)v64 >= (unsigned int)v64 )
    v67 = v65 + v64;
  v12 = v66 < (unsigned int)v64 ? 0xC0000095 : 0;
  *a4 = v67;
  if ( v66 >= (unsigned int)v64 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v69 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, __int64, PVOID *))(*((_QWORD *)Pku2uGlobalBaseSSP + 30)
                                                                                   + 384LL))(
                                 v67,
                                 v64,
                                 v52);
    }
    else
    {
      v70 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD, __int64, PVOID *))Pku2uGlobalBaseSSP + 31))(
                                 v67,
                                 v64,
                                 v52);
      v69 = v70;
      if ( v70 )
      {
        memset_0(v70, 0, v67);
        *(_QWORD *)v105 = v69;
LABEL_166:
        v105 = v69;
        g_make_token_header(v68, (int)v53, &v105, 256);
        memcpy_0(v105, v10, (unsigned int)v53);
        v12 = 0;
        goto LABEL_7;
      }
    }
    *(_QWORD *)v105 = v69;
    if ( !v69 )
    {
      v12 = -1073741801;
      goto LABEL_7;
    }
    goto LABEL_166;
  }
LABEL_7:
  if ( v90 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v13 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v13 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v13();
  }
  if ( v9 )
    KerbFreeAuthData(v9);
  if ( v10 )
    Pku2uFree(v10);
  if ( v79 )
    KerbFreeKey((struct KERB_ENCRYPTION_KEY *)&v78);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006250  mov     [rsp-8+arg_10], r8
0x180006255  push    rbp
0x180006256  push    rbx
0x180006257  push    rsi
0x180006258  push    rdi
0x180006259  push    r12
0x18000625b  push    r13
0x18000625d  push    r14
0x18000625f  push    r15
0x180006261  lea     rbp, [rsp-78h]
0x180006266  sub     rsp, 178h
0x18000626d  mov     rdi, rcx
0x180006270  mov     rbx, rdx
0x180006273  xor     edx, edx
0x180006275  xor     ecx, ecx
0x180006277  mov     [rbp+0B0h+arg_8], edx
0x18000627d  xorps   xmm0, xmm0
0x180006280  mov     [rbp+0B0h+var_D0], rcx
0x180006284  mov     r12, r9
0x180006287  mov     [rsp+1B0h+var_160], rdx
0x18000628c  lea     rsi, [rdi+0B0h]
0x180006293  mov     qword ptr [rbp+0B0h+Time], rdx
0x180006297  mov     r14d, edx
0x18000629a  mov     [rbp+0B0h+var_120], rcx
0x18000629e  mov     r13d, edx
0x1800062a1  mov     [r9], edx
0x1800062a4  mov     r15, 0D6BF94D5E57A42BDh
0x1800062ae  mov     [r8], rdx
0x1800062b1  movups  [rbp+0B0h+var_E0], xmm0
0x1800062b5  movups  [rbp+0B0h+var_130], xmm0
0x1800062b9  test    rbx, rbx
0x1800062bc  jz      short loc_180006305
0x1800062be  lea     rcx, [rbp+0B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800062c2  mov     qword ptr [rbp+0B0h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x1800062c6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800062cc  mov     r8d, [rbx+30h]; int
0x1800062d0  lea     rdx, [rbx+20h]; struct tagASN1generalizedtime_t *
0x1800062d4  lea     rcx, [rbp+0B0h+Time]; Time
0x1800062d8  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
0x1800062dd  mov     rcx, qword ptr [rbp+0B0h+Time]
0x1800062e1  mov     rax, r15
0x1800062e4  sub     rcx, qword ptr [rbp+0B0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800062e8  imul    rcx
0x1800062eb  add     rdx, rcx
0x1800062ee  sar     rdx, 17h
0x1800062f2  mov     rax, rdx
0x1800062f5  shr     rax, 3Fh
0x1800062f9  add     rdx, rax
0x1800062fc  mov     rax, [rsi]
0x1800062ff  xchg    edx, [rax+0B0h]
0x180006305  lea     r15, [rdi+120h]
0x18000630c  test    r15, r15
0x18000630f  jz      short loc_180006331
0x180006311  mov     r9d, 2; dwFlags
0x180006317  mov     r8d, 4; cbBuffer
0x18000631d  mov     rdx, r15; pbBuffer
0x180006320  xor     ecx, ecx; hAlgorithm
0x180006322  call    cs:__imp_BCryptGenRandom
0x180006328  test    eax, eax
0x18000632a  jns     short loc_18000636A
0x18000632c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006331  mov     ebx, 0C000009Ah
0x180006336  mov     rcx, [rbp+0B0h+var_D0]
0x18000633a  test    rcx, rcx
0x18000633d  jz      loc_18000714F
0x180006343  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000634a  cmp     dword ptr [rax+0D0h], 1
0x180006351  jnz     loc_18000713F
0x180006357  mov     rax, [rax+0F0h]
0x18000635e  mov     rax, [rax+188h]
0x180006365  jmp     loc_18000714A
0x18000636a  and     dword ptr [r15], 7FFFFFFFh
0x180006371  lea     rax, [rbp+0B0h+var_130]
0x180006375  mov     rcx, [rsi]
0x180006378  xor     r9d, r9d; unsigned int
0x18000637b  mov     [rsp+1B0h+var_178], rax; struct KERB_ENCRYPTION_KEY *
0x180006380  xor     r8d, r8d; unsigned __int8 *
0x180006383  xor     eax, eax
0x180006385  xor     edx, edx; unsigned int
0x180006387  mov     [rsp+1B0h+var_180], rax; unsigned __int8 *
0x18000638c  mov     ecx, [rcx+38h]; unsigned int
0x18000638f  mov     dword ptr [rsp+1B0h+var_188], eax; unsigned int
0x180006393  mov     [rsp+1B0h+var_190], rax; unsigned __int8 *
0x180006398  call    ?KerbMakeKeyEx@@YAJKKPEAEK0K0PEAUKERB_ENCRYPTION_KEY@@@Z; KerbMakeKeyEx(ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,KERB_ENCRYPTION_KEY *)
0x18000639d  test    eax, eax
0x18000639f  jz      short loc_1800063AC
0x1800063a1  mov     ecx, eax; int
0x1800063a3  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800063a8  mov     ebx, eax
0x1800063aa  jmp     short loc_180006336
0x1800063ac  mov     rax, [rbp+0B0h+arg_20]
0x1800063b3  lea     r9, [rbp+0B0h+arg_8]; unsigned int *
0x1800063ba  lea     r8, [rbp+0B0h+var_E0]; struct KERB_CHECKSUM *
0x1800063be  mov     [rsp+1B0h+var_190], rax; struct _SEC_CHANNEL_BINDINGS *
0x1800063c3  mov     rdx, rdi; struct _PKU2U_CONTEXT *
0x1800063c6  lea     rcx, [rbp+0B0h+var_130]; struct KERB_ENCRYPTION_KEY *
0x1800063ca  call    ?Pku2uBuildGssChecksum@@YAJPEAUKERB_ENCRYPTION_KEY@@PEAU_PKU2U_CONTEXT@@PEAUKERB_CHECKSUM@@PEAKPEAU_SEC_CHANNEL_BINDINGS@@@Z; Pku2uBuildGssChecksum(KERB_ENCRYPTION_KEY *,_PKU2U_CONTEXT *,KERB_CHECKSUM *,ulong *,_SEC_CHANNEL_BINDINGS *)
0x1800063cf  mov     ebx, eax
0x1800063d1  test    eax, eax
0x1800063d3  jns     short loc_180006427
0x1800063d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063dc  lea     rax, WPP_GLOBAL_Control
0x1800063e3  cmp     rcx, rax
0x1800063e6  jz      loc_180006336
0x1800063ec  test    byte ptr [rcx+1Ch], 1
0x1800063f0  jz      loc_180006336
0x1800063f6  mov     rcx, [rcx+10h]
0x1800063fa  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x180006401  mov     edx, 0Ch
0x180006406  mov     dword ptr [rsp+1B0h+var_188], 264h
0x18000640e  mov     r9d, ebx
0x180006411  mov     [rsp+1B0h+var_190], rax
0x180006416  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000641d  call    WPP_SF_dsd
0x180006422  jmp     loc_180006336
0x180006427  xor     eax, eax
0x180006429  lea     rdx, [rsp+1B0h+var_138]
0x18000642e  mov     [rsp+1B0h+var_158], rax
0x180006433  mov     [rsp+1B0h+var_138], rax
0x180006438  mov     rax, [rdi+10h]
0x18000643c  mov     rcx, [rax+18h]
0x180006440  mov     rcx, [rcx+20h]
0x180006444  call    cs:__imp_LsaIGetSupplementalTokenInfo
0x18000644a  mov     ebx, eax
0x18000644c  test    eax, eax
0x18000644e  js      loc_1800064F6
0x180006454  mov     rcx, [rsp+1B0h+var_138]
0x180006459  xor     eax, eax
0x18000645b  mov     [rbp+0B0h+var_100], rax
0x18000645f  mov     [rbp+0B0h+var_F4], eax
0x180006462  mov     [rbp+0B0h+var_EC], eax
0x180006465  lea     rax, [rbp+0B0h+var_100]
0x180006469  mov     [rbp+0B0h+var_108], rax
0x18000646d  mov     eax, [rcx+4]
0x180006470  mov     [rbp+0B0h+var_F8], eax
0x180006473  mov     eax, [rcx]
0x180006475  sub     eax, 8
0x180006478  mov     [rbp+0B0h+var_F0], eax
0x18000647b  lea     rax, [rcx+8]
0x18000647f  mov     [rbp+0B0h+var_E8], rax
0x180006483  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000648a  cmp     dword ptr [rax+0D0h], 1
0x180006491  jnz     loc_18000655B
0x180006497  mov     rax, [rax+0F0h]
0x18000649e  mov     ecx, 20h ; ' '
0x1800064a3  mov     rax, [rax+180h]
0x1800064aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064af  mov     qword ptr [rsp+1B0h+var_150], rax
0x1800064b4  mov     rbx, rax
0x1800064b7  test    rax, rax
0x1800064ba  jnz     loc_18000658A
0x1800064c0  mov     ebx, 0C0000017h
0x1800064c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064cc  lea     rax, WPP_GLOBAL_Control
0x1800064d3  cmp     rcx, rax
0x1800064d6  jz      short loc_1800064F6
0x1800064d8  test    byte ptr [rcx+1Ch], 1
0x1800064dc  jz      short loc_1800064F6
0x1800064de  mov     rcx, [rcx+10h]
0x1800064e2  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800064e9  mov     edx, 0Bh
0x1800064ee  mov     r9d, ebx
0x1800064f1  call    WPP_SF_d
0x1800064f6  mov     rcx, [rsp+1B0h+var_158]; struct PKERB_AUTHORIZATION_DATA *
0x1800064fb  test    rcx, rcx
0x1800064fe  jz      short loc_180006505
0x180006500  call    ?KerbFreeAuthData@@YAXPEAUPKERB_AUTHORIZATION_DATA@@@Z; KerbFreeAuthData(PKERB_AUTHORIZATION_DATA *)
0x180006505  mov     rcx, [rsp+1B0h+var_138]
0x18000650a  test    rcx, rcx
0x18000650d  jz      short loc_180006515
0x18000650f  call    cs:__imp_LsaIFreeSupplementalTokenInfo
0x180006515  test    ebx, ebx
0x180006517  jns     loc_180006AC7
0x18000651d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006524  lea     rax, WPP_GLOBAL_Control
0x18000652b  cmp     rcx, rax
0x18000652e  jz      loc_180006336
0x180006534  test    byte ptr [rcx+1Ch], 1
0x180006538  jz      loc_180006336
0x18000653e  mov     rcx, [rcx+10h]
0x180006542  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180006549  mov     edx, 0Dh
0x18000654e  mov     r9d, ebx
0x180006551  call    WPP_SF_d
0x180006556  jmp     loc_180006336
0x18000655b  mov     rax, [rax+0F8h]
0x180006562  mov     ecx, 20h ; ' '
0x180006567  mov     rax, [rax]
0x18000656a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656f  mov     qword ptr [rsp+1B0h+var_150], rax
0x180006574  mov     rbx, rax
0x180006577  test    rax, rax
0x18000657a  jz      loc_1800064C0
0x180006580  xorps   xmm0, xmm0
0x180006583  movups  xmmword ptr [rax], xmm0
0x180006586  movups  xmmword ptr [rax+10h], xmm0
0x18000658a  cmp     cs:?fKRB5ModuleStarted@@3HA, r13d; int fKRB5ModuleStarted
0x180006591  mov     [rbp+0B0h+arg_18], r13
0x180006598  jnz     short loc_180006601
0x18000659a  mov     dword ptr [rsp+1B0h+var_170], 32756B70h
0x1800065a2  lea     rax, qword_180049F80
0x1800065a9  mov     [rsp+1B0h+var_178], rax
0x1800065ae  mov     edx, 400h
0x1800065b3  lea     rax, off_180047030
0x1800065ba  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x1800065c4  mov     [rsp+1B0h+var_180], rax
0x1800065c9  mov     ecx, 10000h
0x1800065ce  lea     rax, off_1800471C0
0x1800065d5  mov     r9d, 31h ; '1'
0x1800065db  mov     [rsp+1B0h+var_188], rax
0x1800065e0  mov     r8d, 1000h
0x1800065e6  lea     rax, off_180047350
0x1800065ed  mov     [rsp+1B0h+var_190], rax
0x1800065f2  call    cs:__imp_ASN1_CreateModule
0x1800065f8  mov     cs:PKU2UMSG_Module, rax
0x1800065ff  jmp     short loc_180006608
0x180006601  mov     rax, cs:PKU2UMSG_Module
0x180006608  xor     r9d, r9d
0x18000660b  mov     [rsp+1B0h+var_190], r13
0x180006610  xor     r8d, r8d
0x180006613  lea     rdx, [rbp+0B0h+arg_18]
0x18000661a  mov     rcx, rax
0x18000661d  call    cs:__imp_ASN1_CreateEncoder
0x180006623  test    eax, eax
0x180006625  jz      short loc_180006666
0x180006627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000662e  lea     rdx, WPP_GLOBAL_Control
0x180006635  cmp     rcx, rdx
0x180006638  jz      loc_1800066C3
0x18000663e  test    byte ptr [rcx+1Ch], 1
0x180006642  jz      short loc_1800066C3
0x180006644  mov     rcx, [rcx+10h]
0x180006648  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000664f  mov     edx, 4Dh ; 'M'
0x180006654  mov     r9d, eax
0x180006657  call    WPP_SF_d
0x18000665c  mov     ebx, 3Ch ; '<'
0x180006661  jmp     loc_18000678B
0x180006666  mov     rcx, [rbp+0B0h+arg_18]
0x18000666d  lea     rdx, [rbp+0B0h+var_108]
0x180006671  xor     eax, eax
0x180006673  mov     r9d, 10h
0x180006679  mov     dword ptr [rsp+1B0h+var_188], eax
0x18000667d  mov     r8d, 1Dh
0x180006683  mov     [rsp+1B0h+var_190], rax
0x180006688  call    cs:__imp_ASN1_Encode
0x18000668e  test    eax, eax
0x180006690  jns     short loc_1800066CD
0x180006692  mov     rcx, cs:WPP_GLOBAL_Control
0x180006699  lea     rdx, WPP_GLOBAL_Control
0x1800066a0  cmp     rcx, rdx
0x1800066a3  jz      short loc_1800066C3
0x1800066a5  test    byte ptr [rcx+1Ch], 1
0x1800066a9  jz      short loc_1800066C3
0x1800066ab  mov     rcx, [rcx+10h]
0x1800066af  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800066b6  mov     edx, 4Eh ; 'N'
0x1800066bb  mov     r9d, eax
0x1800066be  call    WPP_SF_d
0x1800066c3  mov     ebx, 3Ch ; '<'
0x1800066c8  jmp     loc_18000678B
0x1800066cd  mov     rax, [rbp+0B0h+arg_18]
0x1800066d4  mov     ecx, [rax+1Ch]
0x1800066d7  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x1800066de  mov     dword ptr [rbp+0B0h+Size], ecx
0x1800066e4  cmp     dword ptr [rax+0D0h], 1
0x1800066eb  jnz     short loc_18000671C
0x1800066ed  mov     rax, [rax+0F0h]
0x1800066f4  mov     rax, [rax+180h]
0x1800066fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006700  mov     [rbx+18h], rax
0x180006704  test    rax, rax
0x180006707  jnz     short loc_18000674F
0x180006709  mov     rcx, [rbp+0B0h+arg_18]
0x180006710  mov     dword ptr [rbp+0B0h+Size], 3Ch ; '<'
0x18000671a  jmp     short loc_180006778
0x18000671c  mov     rax, [rax+0F8h]
0x180006723  mov     rax, [rax]
0x180006726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000672b  mov     qword ptr [rsp+1B0h+var_148.Length], rax
0x180006730  test    rax, rax
0x180006733  jz      short loc_180006700
0x180006735  mov     r8d, dword ptr [rbp+0B0h+Size]; Size
0x18000673c  xor     edx, edx; Val
0x18000673e  mov     rcx, rax; void *
0x180006741  call    memset_0
0x180006746  mov     rax, qword ptr [rsp+1B0h+var_148.Length]
0x18000674b  mov     [rbx+18h], rax
0x18000674f  mov     rdx, [rbp+0B0h+arg_18]
0x180006756  xor     ecx, ecx
0x180006758  mov     dword ptr [rbp+0B0h+Size], ecx
0x18000675e  mov     rcx, rax; void *
0x180006761  mov     r8d, [rdx+1Ch]; Size
0x180006765  mov     rdx, [rdx+10h]; Src
0x180006769  call    memcpy_0
0x18000676e  mov     rcx, [rbp+0B0h+arg_18]
0x180006775  mov     eax, [rcx+1Ch]
0x180006778  mov     [rbx+10h], eax
0x18000677b  mov     rdx, [rcx+10h]
0x18000677f  call    cs:__imp_ASN1_FreeEncoded
  ... truncated ...
```
