# Pku2uBuildClientPac(void *,_LARGE_INTEGER *,KERB_ENCRYPTION_KEY *,_UNICODE_STRING const *,PKERB_AUTHORIZATION_DATA * *)

- ea: `0x180038e7c`
- end: `0x1800394b1`
- name: `?Pku2uBuildClientPac@@YAJPEAXPEAT_LARGE_INTEGER@@PEAUKERB_ENCRYPTION_KEY@@PEBU_UNICODE_STRING@@PEAPEAUPKERB_AUTHORIZATION_DATA@@@Z`
- size: `1589`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, union _LARGE_INTEGER *, struct KERB_ENCRYPTION_KEY *, const struct _UNICODE_STRING *, struct PKERB_AUTHORIZATION_DATA **)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006250`

## callees

- `0x180007dc8`
- `0x180014660`
- `0x180018870`
- `0x180019334`
- `0x18001b190`
- `0x18001fce8`
- `0x180021a54`
- `0x180023ce0`
- `0x1800372f0`
- `0x18003872c`
- `0x1800387ec`
- `0x180038d38`
- `0x180038e7c`
- `0x1800394b8`
- `0x1800396bc`
- `0x18003970c`
- `0x18003a688`
- `0x18003a998`
- `0x1800443ec`
- `0x180044434`
- `0x1800446f4`

## import_xrefs

- `LSASRV!LsaICopyToTokenInfoFromHandle` at `0x180038fff`
- `LSASRV!LsaICopyToTokenInfoFromHandle` at `0x180038fff`

## pseudocode

```c
__int64 __fastcall Pku2uBuildClientPac(
        HANDLE TokenHandle,
        union _LARGE_INTEGER *a2,
        struct KERB_ENCRYPTION_KEY *a3,
        const struct _UNICODE_STRING *a4,
        struct PKERB_AUTHORIZATION_DATA **a5)
{
  int LogonServerName; // ebx
  int v10; // eax
  _DWORD *v11; // rcx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  int inited; // eax
  unsigned __int8 *v17; // rax
  int inserted; // eax
  struct PKERB_AUTHORIZATION_DATA *v19; // rdx
  size_t v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21; // [rsp+38h] [rbp-C8h]
  union _LARGE_INTEGER *v22; // [rsp+50h] [rbp-B0h]
  union _LARGE_INTEGER *v23; // [rsp+58h] [rbp-A8h]
  struct _LSA_LAST_INTER_LOGON_INFO *v24; // [rsp+60h] [rbp-A0h]
  unsigned int v25; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  void *v28; // [rsp+88h] [rbp-78h] BYREF
  struct _PACTYPE *Src; // [rsp+90h] [rbp-70h] BYREF
  struct _SECURITY_CAPABILITIES *v30; // [rsp+98h] [rbp-68h] BYREF
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v33; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v34; // [rsp+B8h] [rbp-48h] BYREF
  struct _PAC_INFO_BUFFER *v35[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v36[14]; // [rsp+D0h] [rbp-30h] BYREF
  char v37; // [rsp+140h] [rbp+40h]
  __int128 v38; // [rsp+150h] [rbp+50h] BYREF
  __int128 v39; // [rsp+160h] [rbp+60h] BYREF
  __int128 v40; // [rsp+170h] [rbp+70h] BYREF
  __int128 v41; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING v42; // [rsp+190h] [rbp+90h] BYREF
  __int128 v43; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int8 *v44[2]; // [rsp+1B0h] [rbp+B0h]
  _DWORD v45[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _DWORD *v46; // [rsp+1C8h] [rbp+C8h]
  struct _UNICODE_STRING v47; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v48; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v49; // [rsp+1F0h] [rbp+F0h] BYREF
  struct _PAC_INFO_BUFFER *v50[6]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v51[368]; // [rsp+230h] [rbp+130h] BYREF
  const struct _UNICODE_STRING *v52; // [rsp+3C8h] [rbp+2C8h] BYREF

  v52 = a4;
  *(_QWORD *)&v42.Length = 2097182;
  v42.Buffer = (PWSTR)L"WELLKNOWN:PKU2U";
  v27 = 0;
  memset_0(v51, 0, 0x13Cu);
  v49 = 0;
  v48 = 0;
  LODWORD(v52) = 0;
  v28 = 0;
  v47 = 0;
  Src = 0;
  v43 = 0;
  *(_OWORD *)v44 = 0;
  v32 = 0;
  v30 = 0;
  v33 = 0;
  v25 = 0;
  v31 = 0;
  v34 = 0;
  v26 = 0;
  v35[0] = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v36[0] = &v43;
  v36[1] = &v27;
  v36[2] = v51;
  v36[3] = &v49;
  v36[4] = &v48;
  v36[5] = &Src;
  v36[6] = v35;
  v36[7] = &v32;
  v36[8] = &v30;
  v36[9] = &v33;
  v36[10] = &v31;
  v36[11] = &v34;
  v36[12] = &v28;
  v36[13] = &v47;
  v37 = 1;
  LogonServerName = Pku2uGetLogonServerName(&v47);
  if ( LogonServerName < 0
    || (LogonServerName = LsaICopyToTokenInfoFromHandle(TokenHandle, 2, 0, &v27), LogonServerName < 0)
    || (LogonServerName = Pku2uComputeDomainRelativeSid(*(PSID *)(v27 + 8), &v28, (unsigned int *)&v52),
        LogonServerName < 0) )
  {
LABEL_2:
    v37 = 0;
    lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b_::operator()(v36);
    return (unsigned int)LogonServerName;
  }
  v10 = Pku2uComputeUserInfo(
          &Pku2uGlobalContainerUserName,
          (unsigned int)v52,
          (unsigned int)v52,
          (struct _SAMPR_USER_ALL_INFORMATION *)v51);
  LogonServerName = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)v10);
    goto LABEL_2;
  }
  v11 = *(_DWORD **)(v27 + 24);
  if ( v11 )
  {
    v45[1] = 0;
    v45[0] = *v11;
    v46 = v11 + 2;
    LogonServerName = Pku2uFilterGroupMembership(
                        (struct _SID_AND_ATTRIBUTES_LIST *)v45,
                        v28,
                        (struct _SAMPR_GET_GROUPS_BUFFER *)&v49,
                        (struct _SID_AND_ATTRIBUTES_LIST *)&v48,
                        (unsigned int *)&v52);
    if ( LogonServerName < 0 )
      goto LABEL_2;
  }
  LogonServerName = Pku2uBuildPacVerifier(a2, &Pku2uGlobalContainerUserName, v35);
  if ( LogonServerName < 0 )
    goto LABEL_2;
  LogonServerName = Pku2uQueryNtTokenBuffer<_TOKEN_PRIVILEGES>(TokenHandle);
  if ( LogonServerName < 0 )
    goto LABEL_2;
  v12 = Pku2uBuildTokenSecurityCapabilitiesBuffer(TokenHandle, &v30, (unsigned int *)&v52);
  LogonServerName = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)v12);
    goto LABEL_2;
  }
  v13 = Pku2uMarshalTokenSecurityCapabilitiesBuffer(v30, &v33, &v25);
  LogonServerName = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)v13);
    goto LABEL_29;
  }
  LogonServerName = Pku2uQueryNtTokenBuffer<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(TokenHandle);
  if ( LogonServerName < 0
    || (LogonServerName = Pku2uMarshalTokenSecurityAttributesBuffer(v31, v14, &v34, &v26), LogonServerName < 0) )
  {
LABEL_29:
    v37 = 0;
    lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b_::operator()(v36);
    return (unsigned int)LogonServerName;
  }
  v15 = *(_QWORD *)(v27 + 64);
  if ( v15 )
  {
    DWORD1(v38) = *(_DWORD *)v15;
    *((_QWORD *)&v38 + 1) = *(_QWORD *)(v15 + 8);
  }
  LODWORD(v38) = 13;
  *((_QWORD *)&v39 + 1) = v32;
  *(_QWORD *)&v39 = 256;
  DWORD1(v40) = v25;
  *((_QWORD *)&v40 + 1) = v33;
  LODWORD(v40) = 257;
  DWORD1(v41) = v26;
  *((_QWORD *)&v41 + 1) = v34;
  LODWORD(v41) = 258;
  v50[0] = v35[0];
  v50[1] = (struct _PAC_INFO_BUFFER *)&v38;
  v50[2] = (struct _PAC_INFO_BUFFER *)&v39;
  v50[3] = (struct _PAC_INFO_BUFFER *)&v40;
  v50[4] = (struct _PAC_INFO_BUFFER *)&v41;
  inited = PAC_InitEx2(
             (struct _SAMPR_USER_ALL_INFORMATION *)v51,
             (struct _SAMPR_GET_GROUPS_BUFFER *)&v49,
             (struct _SID_AND_ATTRIBUTES_LIST *)&v48,
             v28,
             &v42,
             &v47,
             v20,
             v21,
             5u,
             v50,
             v22,
             v23,
             v24,
             &Src);
  LogonServerName = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)inited);
    goto LABEL_29;
  }
  DWORD2(v43) = 128;
  LODWORD(v44[0]) = PAC_GetSize(Src);
  v17 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, LODWORD(v44[0]));
  v44[1] = v17;
  if ( v17 )
  {
    PAC_Marshal(Src, (unsigned int)v44[0], v17);
    inserted = Pku2uSignPac(a3, (unsigned int)v44[0], v44[1]);
    if ( inserted || (inserted = Pku2uInsertPacIntoAuthData(*a5, v19, (struct PKERB_AUTHORIZATION_DATA *)&v43, a5)) != 0 )
    {
      LogonServerName = KerbMapKerbError(inserted);
      v37 = 0;
      lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b_::operator()(v36);
      return (unsigned int)LogonServerName;
    }
    v37 = 0;
    lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b_::operator()(v36);
    return 0;
  }
  else
  {
    v37 = 0;
    lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b_::operator()(v36);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x180038e7c  mov     [rsp-8+arg_18], r9
0x180038e81  push    rbp
0x180038e82  push    rbx
0x180038e83  push    rsi
0x180038e84  push    rdi
0x180038e85  push    r14
0x180038e87  push    r15
0x180038e89  lea     rbp, [rsp-278h]
0x180038e91  sub     rsp, 378h
0x180038e98  mov     r14, r8
0x180038e9b  mov     rsi, rdx
0x180038e9e  mov     rdi, rcx
0x180038ea1  mov     qword ptr [rbp+2A0h+var_210.Length], 20001Eh
0x180038eac  lea     rax, WideCharStr; "WELLKNOWN:PKU2U"
0x180038eb3  mov     [rbp+2A0h+var_210.Buffer], rax
0x180038eba  xor     r15d, r15d
0x180038ebd  mov     [rbp+2A0h+var_320], r15
0x180038ec1  xor     edx, edx; Val
0x180038ec3  mov     r8d, 13Ch; Size
0x180038ec9  lea     rcx, [rbp+2A0h+var_170]; void *
0x180038ed0  call    memset_0
0x180038ed5  xorps   xmm0, xmm0
0x180038ed8  movups  [rbp+2A0h+var_1B0], xmm0
0x180038edf  xorps   xmm1, xmm1
0x180038ee2  movups  [rbp+2A0h+var_1C0], xmm1
0x180038ee9  mov     dword ptr [rbp+2A0h+arg_18], r15d
0x180038ef0  mov     [rbp+2A0h+var_318], r15
0x180038ef4  movups  xmmword ptr [rbp+2A0h+var_1D0.Length], xmm0
0x180038efb  mov     [rbp+2A0h+Src], r15
0x180038eff  movups  [rbp+2A0h+var_200], xmm1
0x180038f06  movups  xmmword ptr [rbp+2A0h+var_1F0], xmm1
0x180038f0d  mov     [rbp+2A0h+var_2F8], r15
0x180038f11  mov     [rsp+3A0h+var_330], r15d
0x180038f16  mov     [rbp+2A0h+var_308], r15
0x180038f1a  mov     [rbp+2A0h+var_2F0], r15
0x180038f1e  mov     [rsp+3A0h+var_32C], r15d
0x180038f23  mov     [rbp+2A0h+var_300], r15
0x180038f27  mov     [rbp+2A0h+var_2E8], r15
0x180038f2b  mov     [rsp+3A0h+var_328], r15d
0x180038f30  mov     [rbp+2A0h+var_2E0], r15
0x180038f34  movups  [rbp+2A0h+var_250], xmm0
0x180038f38  movups  [rbp+2A0h+var_240], xmm1
0x180038f3c  movups  [rbp+2A0h+var_230], xmm0
0x180038f40  movups  [rbp+2A0h+var_220], xmm1
0x180038f47  lea     rax, [rbp+2A0h+var_200]
0x180038f4e  mov     [rbp+2A0h+var_2D0], rax
0x180038f52  lea     rax, [rbp+2A0h+var_320]
0x180038f56  mov     [rbp+2A0h+var_2C8], rax
0x180038f5a  lea     rax, [rbp+2A0h+var_170]
0x180038f61  mov     [rbp+2A0h+var_2C0], rax
0x180038f65  lea     rax, [rbp+2A0h+var_1B0]
0x180038f6c  mov     [rbp+2A0h+var_2B8], rax
0x180038f70  lea     rax, [rbp+2A0h+var_1C0]
0x180038f77  mov     [rbp+2A0h+var_2B0], rax
0x180038f7b  lea     rax, [rbp+2A0h+Src]
0x180038f7f  mov     [rbp+2A0h+var_2A8], rax
0x180038f83  lea     rax, [rbp+2A0h+var_2E0]
0x180038f87  mov     [rbp+2A0h+var_2A0], rax
0x180038f8b  lea     rax, [rbp+2A0h+var_2F8]
0x180038f8f  mov     [rbp+2A0h+var_298], rax
0x180038f93  lea     rax, [rbp+2A0h+var_308]
0x180038f97  mov     [rbp+2A0h+var_290], rax
0x180038f9b  lea     rax, [rbp+2A0h+var_2F0]
0x180038f9f  mov     [rbp+2A0h+var_288], rax
0x180038fa3  lea     rax, [rbp+2A0h+var_300]
0x180038fa7  mov     [rbp+2A0h+var_280], rax
0x180038fab  lea     rax, [rbp+2A0h+var_2E8]
0x180038faf  mov     [rbp+2A0h+var_278], rax
0x180038fb3  lea     rax, [rbp+2A0h+var_318]
0x180038fb7  mov     [rbp+2A0h+var_270], rax
0x180038fbb  lea     rax, [rbp+2A0h+var_1D0]
0x180038fc2  mov     [rbp+2A0h+var_268], rax
0x180038fc6  mov     [rbp+2A0h+var_260], 1
0x180038fca  lea     rcx, [rbp+2A0h+var_1D0]; struct _UNICODE_STRING *
0x180038fd1  call    ?Pku2uGetLogonServerName@@YAJPEAU_UNICODE_STRING@@@Z; Pku2uGetLogonServerName(_UNICODE_STRING *)
0x180038fd6  mov     ebx, eax
0x180038fd8  test    eax, eax
0x180038fda  jns     short loc_180038FF1
0x180038fdc  mov     [rbp+2A0h+var_260], r15b
0x180038fe0  lea     rcx, [rbp+2A0h+var_2D0]
0x180038fe4  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180038fe9  nop
0x180038fea  mov     eax, ebx
0x180038fec  jmp     loc_1800394A1
0x180038ff1  lea     r9, [rbp+2A0h+var_320]
0x180038ff5  xor     r8d, r8d
0x180038ff8  lea     edx, [r8+2]
0x180038ffc  mov     rcx, rdi
0x180038fff  call    cs:__imp_LsaICopyToTokenInfoFromHandle
0x180039005  mov     ebx, eax
0x180039007  test    eax, eax
0x180039009  jns     short loc_18003901B
0x18003900b  mov     [rbp+2A0h+var_260], r15b
0x18003900f  lea     rcx, [rbp+2A0h+var_2D0]
0x180039013  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039018  nop
0x180039019  jmp     short loc_180038FEA
0x18003901b  lea     r8, [rbp+2A0h+arg_18]; unsigned int *
0x180039022  lea     rdx, [rbp+2A0h+var_318]; void **
0x180039026  mov     rcx, [rbp+2A0h+var_320]
0x18003902a  mov     rcx, [rcx+8]; Sid
0x18003902e  call    ?Pku2uComputeDomainRelativeSid@@YAJPEAXPEAPEAXPEAK@Z; Pku2uComputeDomainRelativeSid(void *,void * *,ulong *)
0x180039033  mov     ebx, eax
0x180039035  test    eax, eax
0x180039037  jns     short loc_180039049
0x180039039  mov     [rbp+2A0h+var_260], r15b
0x18003903d  lea     rcx, [rbp+2A0h+var_2D0]
0x180039041  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039046  nop
0x180039047  jmp     short loc_180038FEA
0x180039049  lea     r9, [rbp+2A0h+var_170]; struct _SAMPR_USER_ALL_INFORMATION *
0x180039050  mov     edx, dword ptr [rbp+2A0h+arg_18]; unsigned int
0x180039056  mov     r8d, edx; unsigned int
0x180039059  lea     rcx, ?Pku2uGlobalContainerUserName@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180039060  call    ?Pku2uComputeUserInfo@@YAJPEBU_UNICODE_STRING@@KKPEAU_SAMPR_USER_ALL_INFORMATION@@@Z; Pku2uComputeUserInfo(_UNICODE_STRING const *,ulong,ulong,_SAMPR_USER_ALL_INFORMATION *)
0x180039065  mov     ebx, eax
0x180039067  test    eax, eax
0x180039069  jns     short loc_1800390B0
0x18003906b  lea     rdx, WPP_GLOBAL_Control
0x180039072  mov     rcx, cs:WPP_GLOBAL_Control
0x180039079  cmp     rcx, rdx
0x18003907c  jz      short loc_18003909D
0x18003907e  test    byte ptr [rcx+1Ch], 1
0x180039082  jz      short loc_18003909D
0x180039084  mov     edx, 3Bh ; ';'
0x180039089  mov     r9d, eax
0x18003908c  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180039093  mov     rcx, [rcx+10h]
0x180039097  call    WPP_SF_d
0x18003909c  nop
0x18003909d  mov     [rbp+2A0h+var_260], r15b
0x1800390a1  lea     rcx, [rbp+2A0h+var_2D0]
0x1800390a5  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x1800390aa  nop
0x1800390ab  jmp     loc_180038FEA
0x1800390b0  mov     rax, [rbp+2A0h+var_320]
0x1800390b4  mov     rcx, [rax+18h]
0x1800390b8  test    rcx, rcx
0x1800390bb  jz      short loc_18003911A
0x1800390bd  mov     [rbp+2A0h+var_1DC], r15d
0x1800390c4  mov     eax, [rcx]
0x1800390c6  mov     [rbp+2A0h+var_1E0], eax
0x1800390cc  lea     rax, [rcx+8]
0x1800390d0  mov     [rbp+2A0h+var_1D8], rax
0x1800390d7  lea     rax, [rbp+2A0h+arg_18]
0x1800390de  mov     [rsp+3A0h+var_380], rax; unsigned int *
0x1800390e3  lea     r9, [rbp+2A0h+var_1C0]; struct _SID_AND_ATTRIBUTES_LIST *
0x1800390ea  lea     r8, [rbp+2A0h+var_1B0]; struct _SAMPR_GET_GROUPS_BUFFER *
0x1800390f1  mov     rdx, [rbp+2A0h+var_318]; void *
0x1800390f5  lea     rcx, [rbp+2A0h+var_1E0]; struct _SID_AND_ATTRIBUTES_LIST *
0x1800390fc  call    ?Pku2uFilterGroupMembership@@YAJPEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_SAMPR_GET_GROUPS_BUFFER@@0PEAK@Z; Pku2uFilterGroupMembership(_SID_AND_ATTRIBUTES_LIST *,void *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,ulong *)
0x180039101  mov     ebx, eax
0x180039103  test    eax, eax
0x180039105  jns     short loc_18003911A
0x180039107  mov     [rbp+2A0h+var_260], r15b
0x18003910b  lea     rcx, [rbp+2A0h+var_2D0]
0x18003910f  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039114  nop
0x180039115  jmp     loc_180038FEA
0x18003911a  lea     r8, [rbp+2A0h+var_2E0]; struct _PAC_INFO_BUFFER **
0x18003911e  lea     rdx, ?Pku2uGlobalContainerUserName@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180039125  mov     rcx, rsi; union _LARGE_INTEGER *
0x180039128  call    ?Pku2uBuildPacVerifier@@YAJPEAT_LARGE_INTEGER@@PEBU_UNICODE_STRING@@PEAPEAU_PAC_INFO_BUFFER@@@Z; Pku2uBuildPacVerifier(_LARGE_INTEGER *,_UNICODE_STRING const *,_PAC_INFO_BUFFER * *)
0x18003912d  mov     ebx, eax
0x18003912f  test    eax, eax
0x180039131  jns     short loc_180039146
0x180039133  mov     [rbp+2A0h+var_260], r15b
0x180039137  lea     rcx, [rbp+2A0h+var_2D0]
0x18003913b  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039140  nop
0x180039141  jmp     loc_180038FEA
0x180039146  lea     r9, [rsp+3A0h+var_330]
0x18003914b  lea     r8, [rbp+2A0h+var_2F8]
0x18003914f  mov     rcx, rdi; TokenHandle
0x180039152  call    ??$Pku2uQueryNtTokenBuffer@U_TOKEN_PRIVILEGES@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_PRIVILEGES@@PEAK@Z; Pku2uQueryNtTokenBuffer<_TOKEN_PRIVILEGES>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_PRIVILEGES * *,ulong *)
0x180039157  mov     ebx, eax
0x180039159  test    eax, eax
0x18003915b  jns     short loc_180039170
0x18003915d  mov     [rbp+2A0h+var_260], r15b
0x180039161  lea     rcx, [rbp+2A0h+var_2D0]
0x180039165  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x18003916a  nop
0x18003916b  jmp     loc_180038FEA
0x180039170  lea     r8, [rbp+2A0h+arg_18]; unsigned int *
0x180039177  lea     rdx, [rbp+2A0h+var_308]; struct _SECURITY_CAPABILITIES **
0x18003917b  mov     rcx, rdi; TokenHandle
0x18003917e  call    ?Pku2uBuildTokenSecurityCapabilitiesBuffer@@YAJPEAXPEAPEAU_SECURITY_CAPABILITIES@@PEAK@Z; Pku2uBuildTokenSecurityCapabilitiesBuffer(void *,_SECURITY_CAPABILITIES * *,ulong *)
0x180039183  mov     ebx, eax
0x180039185  test    eax, eax
0x180039187  jns     short loc_1800391CE
0x180039189  lea     rdx, WPP_GLOBAL_Control
0x180039190  mov     rcx, cs:WPP_GLOBAL_Control
0x180039197  cmp     rcx, rdx
0x18003919a  jz      short loc_1800391BB
0x18003919c  test    byte ptr [rcx+1Ch], 1
0x1800391a0  jz      short loc_1800391BB
0x1800391a2  mov     edx, 3Ch ; '<'
0x1800391a7  mov     r9d, eax
0x1800391aa  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x1800391b1  mov     rcx, [rcx+10h]
0x1800391b5  call    WPP_SF_d
0x1800391ba  nop
0x1800391bb  mov     [rbp+2A0h+var_260], r15b
0x1800391bf  lea     rcx, [rbp+2A0h+var_2D0]
0x1800391c3  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x1800391c8  nop
0x1800391c9  jmp     loc_180038FEA
0x1800391ce  lea     r8, [rsp+3A0h+var_32C]; unsigned int *
0x1800391d3  lea     rdx, [rbp+2A0h+var_2F0]; unsigned __int8 **
0x1800391d7  mov     rcx, [rbp+2A0h+var_308]; struct _SECURITY_CAPABILITIES *
0x1800391db  call    ?Pku2uMarshalTokenSecurityCapabilitiesBuffer@@YAJPEAU_SECURITY_CAPABILITIES@@PEAPEAEPEAK@Z; Pku2uMarshalTokenSecurityCapabilitiesBuffer(_SECURITY_CAPABILITIES *,uchar * *,ulong *)
0x1800391e0  mov     ebx, eax
0x1800391e2  test    eax, eax
0x1800391e4  jns     short loc_18003922B
0x1800391e6  lea     rdx, WPP_GLOBAL_Control
0x1800391ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391f4  cmp     rcx, rdx
0x1800391f7  jz      short loc_180039218
0x1800391f9  test    byte ptr [rcx+1Ch], 1
0x1800391fd  jz      short loc_180039218
0x1800391ff  mov     edx, 3Dh ; '='
0x180039204  mov     r9d, eax
0x180039207  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18003920e  mov     rcx, [rcx+10h]
0x180039212  call    WPP_SF_d
0x180039217  nop
0x180039218  mov     [rbp+2A0h+var_260], r15b
0x18003921c  lea     rcx, [rbp+2A0h+var_2D0]
0x180039220  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039225  nop
0x180039226  jmp     loc_180038FEA
0x18003922b  lea     r9, [rbp+2A0h+arg_18]
0x180039232  lea     r8, [rbp+2A0h+var_300]
0x180039236  mov     rcx, rdi; TokenHandle
0x180039239  call    ??$Pku2uQueryNtTokenBuffer@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAK@Z; Pku2uQueryNtTokenBuffer<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,ulong *)
0x18003923e  mov     ebx, eax
0x180039240  test    eax, eax
0x180039242  jns     short loc_180039257
0x180039244  mov     [rbp+2A0h+var_260], r15b
0x180039248  lea     rcx, [rbp+2A0h+var_2D0]
0x18003924c  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x180039251  nop
0x180039252  jmp     loc_180038FEA
0x180039257  lea     r9, [rsp+3A0h+var_328]; unsigned int *
0x18003925c  lea     r8, [rbp+2A0h+var_2E8]; unsigned __int8 **
0x180039260  mov     rcx, [rbp+2A0h+var_300]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *
0x180039264  call    ?Pku2uMarshalTokenSecurityAttributesBuffer@@YAJQEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@KPEAPEAEPEAK@Z; Pku2uMarshalTokenSecurityAttributesBuffer(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * const,ulong,uchar * *,ulong *)
0x180039269  mov     ebx, eax
0x18003926b  test    eax, eax
0x18003926d  jns     short loc_180039282
0x18003926f  mov     [rbp+2A0h+var_260], r15b
0x180039273  lea     rcx, [rbp+2A0h+var_2D0]
0x180039277  call    _lambda_ee1adbc28d2d49c8ce878ea6a6fbf97b___operator__
0x18003927c  nop
0x18003927d  jmp     loc_180038FEA
0x180039282  mov     rax, [rbp+2A0h+var_320]
0x180039286  mov     rcx, [rax+40h]
0x18003928a  test    rcx, rcx
0x18003928d  jz      short loc_18003929C
0x18003928f  mov     eax, [rcx]
0x180039291  mov     dword ptr [rbp+2A0h+var_250+4], eax
0x180039294  mov     rax, [rcx+8]
0x180039298  mov     qword ptr [rbp+2A0h+var_250+8], rax
0x18003929c  mov     dword ptr [rbp+2A0h+var_250], 0Dh
0x1800392a3  mov     eax, [rsp+3A0h+var_330]
0x1800392a7  mov     dword ptr [rbp+2A0h+var_240+4], eax
0x1800392aa  mov     rax, [rbp+2A0h+var_2F8]
0x1800392ae  mov     qword ptr [rbp+2A0h+var_240+8], rax
0x1800392b2  mov     dword ptr [rbp+2A0h+var_240], 100h
0x1800392b9  mov     eax, [rsp+3A0h+var_32C]
0x1800392bd  mov     dword ptr [rbp+2A0h+var_230+4], eax
0x1800392c0  mov     rax, [rbp+2A0h+var_2F0]
0x1800392c4  mov     qword ptr [rbp+2A0h+var_230+8], rax
0x1800392c8  mov     dword ptr [rbp+2A0h+var_230], 101h
0x1800392cf  mov     eax, [rsp+3A0h+var_328]
0x1800392d3  mov     dword ptr [rbp+2A0h+var_220+4], eax
0x1800392d9  mov     rax, [rbp+2A0h+var_2E8]
0x1800392dd  mov     qword ptr [rbp+2A0h+var_220+8], rax
0x1800392e4  mov     dword ptr [rbp+2A0h+var_220], 102h
0x1800392ee  mov     rax, [rbp+2A0h+var_2E0]
0x1800392f2  mov     [rbp+2A0h+var_1A0], rax
0x1800392f9  lea     rax, [rbp+2A0h+var_250]
0x1800392fd  mov     [rbp+2A0h+var_198], rax
0x180039304  lea     rax, [rbp+2A0h+var_240]
0x180039308  mov     [rbp+2A0h+var_190], rax
0x18003930f  lea     rax, [rbp+2A0h+var_230]
0x180039313  mov     [rbp+2A0h+var_188], rax
0x18003931a  lea     rax, [rbp+2A0h+var_220]
0x180039321  mov     [rbp+2A0h+var_180], rax
0x180039328  lea     rax, [rbp+2A0h+Src]
0x18003932c  mov     [rsp+3A0h+var_338], rax; struct _PACTYPE **
0x180039331  lea     rax, [rbp+2A0h+var_1A0]
0x180039338  mov     [rsp+3A0h+var_358], rax; struct _PAC_INFO_BUFFER **
0x18003933d  mov     [rsp+3A0h+var_360], 5; unsigned int
0x180039345  lea     rax, [rbp+2A0h+var_1D0]
0x18003934c  mov     [rsp+3A0h+var_378], rax; struct _UNICODE_STRING *
0x180039351  lea     rax, [rbp+2A0h+var_210]
0x180039358  mov     [rsp+3A0h+var_380], rax; struct _UNICODE_STRING *
0x18003935d  mov     r9, [rbp+2A0h+var_318]; void *
0x180039361  lea     r8, [rbp+2A0h+var_1C0]; struct _SID_AND_ATTRIBUTES_LIST *
  ... truncated ...
```
